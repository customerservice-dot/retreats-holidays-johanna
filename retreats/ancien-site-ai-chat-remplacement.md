# Ancien site (www.retreats-holidays.com) — remplacement du bot SEUL (décision du 24/10)

> **FICHIER ENTIÈREMENT OBSOLÈTE depuis le 28/10/2026** : la bascule de domaine a eu lieu — www sert désormais la nouvelle version (`retreats-holidays-live`/`main`, voir `comparatif-versions-site.md`). L'ancien site kodekins n'est plus servi au public ; ni l'iframe ni le proxy Supabase n'ont plus d'objet ; la branche `feat/johanna-embed-remove-stripe` ne doit pas être poussée. Conservé pour mémoire uniquement.

> **OBSOLÈTE (24/10, consigne propriétaire)** : NE PAS déployer ce relais Supabase. Le bon dépôt de l'ancien site est `kodekins/retreat-holidays` (projet Vercel kodekins-projects/retreat-holidays) ; la route `/api/chat` de retreats-holidays-live renvoie 404. Remplacement retenu : iframe Johanna (johanna-retreats-holidays-gxdv8a.v2.appdeploy.ai) dans Chatbot.tsx + purge du parcours Stripe — implémenté sur la branche `feat/johanna-embed-remove-stripe` de kodekins/retreat-holidays (commit 9585671).

**Décision propriétaire (24/10)** : garder l'ancien site public tel quel ; seul le chatbot bascule
sur la nouvelle Johanna. Ni DNS ni domaine ne bougent (TXT Hostinger : NE PAS ajouter).

## Architecture constatée (vérifiée le 24/10)
- Ancien site = commit initial `e5a3ca8` du dépôt retreats-holidays-live, déployé sur un AUTRE
  compte Vercel (hors équipe jodu93-8995) ; domaine vérifié là-bas.
- Son chat appelle la fonction Supabase **`ai-chat`** du projet **`jfwhkrmbmpegizcjuieg`**
  (invoke avec clé anon ; requête `{messages}` ; réponse `{content, retreats[]}`).
- La carte « Concierge fee (5%) » + Stripe (`PayForDetailsModal`, `stripe-create-checkout`)
  ne se déclenchent QUE depuis les `retreats` renvoyés par `ai-chat` (RetreatCard dans Chatbot.tsx).
- Nouvelle Johanna = `POST https://retreats-holidays-live.vercel.app/api/chat`
  avec `{lang, messages}` → `{reply}` (fallback: `{fallback:true,error}`).

## Stratégie : remplacer `ai-chat` par un proxy vers la nouvelle API
- `content` = `reply` de la nouvelle Johanna (lang **en** — site anglophone) ;
- `retreats: []` TOUJOURS → la carte de match et le paiement 5 %/$5 deviennent inatteignables ;
- échec API → message d'excuse court, status 200 (l'ancien front gère mal les non-200).

## BLOCAGE ACCÈS (action propriétaire)
Le connecteur Supabase de la session est connecté à « customerservice-dot's Org » : AUCUN projet.
Le projet `jfwhkrmbmpegizcjuieg` appartient à un autre compte Supabase (probablement celui de la
création Lovable). → Reconnecter le connecteur Supabase sur claude.ai/customize/connectors avec le
compte qui voit ce projet dans supabase.com/dashboard, puis nouvelle session ou signal ici.

## Limite connue (à dire au propriétaire — FAIT le 24/10)
La phrase d'accueil du chat est codée en dur dans l'ancien frontend et mentionne « a small 5% fee ».
Le PARCOURS de paiement disparaît, mais cette phrase d'intro restera tant que l'ancien frontend
n'est pas redéployé (accès à l'autre compte Vercel requis).

## Fonction prête à déployer (deploy_edge_function, name=ai-chat, project_id=jfwhkrmbmpegizcjuieg, verify_jwt=true)
```ts
// supabase/functions/ai-chat/index.ts — PROXY vers la nouvelle Johanna (24/10/2026)
const corsHeaders = {
  "Access-Control-Allow-Origin": "*",
  "Access-Control-Allow-Headers": "authorization, x-client-info, apikey, content-type",
};
const API = "https://retreats-holidays-live.vercel.app/api/chat";
const SORRY = "Sorry — I could not answer just now. Please try again in a moment.";

Deno.serve(async (req: Request) => {
  if (req.method === "OPTIONS") return new Response("ok", { headers: corsHeaders });
  let content = SORRY;
  try {
    const body = await req.json().catch(() => ({}));
    const messages = Array.isArray(body?.messages) ? body.messages : [];
    const r = await fetch(API, {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify({ lang: "en", messages }),
    });
    const data = await r.json().catch(() => null);
    if (data && typeof data.reply === "string" && data.reply.trim()) content = data.reply.trim();
  } catch (_e) { /* keep SORRY */ }
  return new Response(JSON.stringify({ content, retreats: [] }), {
    headers: { ...corsHeaders, "Content-Type": "application/json" },
  });
});
```

## Après déploiement — contrôles
1. POST de test sur la fonction (anon key du bundle) : réponse `{content, retreats: []}`.
2. Chat sur www.retreats-holidays.com (ordinateur + mobile) : ton nouvelle Johanna, EN, aucune carte 5 %.
3. Compte rendu au propriétaire + note à la session Johanna.
