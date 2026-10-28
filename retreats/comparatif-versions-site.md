# Une seule cible pour www.retreats-holidays.com — comparatif de décision (27/10/2026)

> **TRANCHÉ ET EXÉCUTÉ le 28/10/2026 : cible B.** Le propriétaire a fait poser les TXT `_vercel` chez Hostinger ; les deux domaines sont vérifiés sur le projet Vercel `retreats-holidays-live` et **www sert la nouvelle version** (vérifié indépendamment par les deux sessions le 28/10 ; contrôles Playwright de la session Pierre : Johanna présente, aucune mention « 5% fee », WhatsApp +230, aucune référence Stripe ; l'apex redirige en 308 vers www ; ni A ni NS touchés). L'ancien site kodekins n'est plus servi au public ; la branche `feat/johanna-embed-remove-stripe` est définitivement obsolète. **Le site public = `retreats-holidays-live`/`main` désormais.** Le comparatif ci-dessous est conservé pour mémoire.

*Demandé par le propriétaire (relais session Pierre, 27/10) : rapprocher les deux versions du site avant toute bascule, et choisir UNE cible. Consignes en vigueur : aucune seconde bascule avant ce choix, branche `feat/johanna-embed-remove-stripe` (kodekins) PARQUÉE, aucun changement DNS/domaine. Tout ce qui suit est vérifié sur pièces le 27/10 sauf mention contraire.*

## Version A — l'ancien site (dépôt `kodekins/retreat-holidays`), celui que le public voit

- **En ligne aujourd'hui** sur www.retreats-holidays.com (vérifié 27/10 : build anglaise « Wellness & Yoga Retreats from the Middle East » ; l'apex redirige vers www).
- **Chatbot** : l'ancien bot, branché sur une fonction Supabase `ai-chat` d'un projet inaccessible à nos sessions ; carte « Concierge fee (5 %) » + **parcours Stripe réel** — un chemin d'encaissement actif, chez un compte tiers, non conforme au verrou juridique. Phrase d'accueil « a small 5% fee » codée en dur dans le frontend.
- **Plan préparé puis parqué** : remplacer le seul chatbot par une iframe de la nouvelle Johanna + purge du parcours Stripe (branche `feat/johanna-embed-remove-stripe`, commit 9585671). Les droits collaborateur kodekins ne sont plus présentés comme préalable, mais rien ne bouge avant le choix de cible.
- Pour : le domaine public y est déjà rattaché (aucun DNS à toucher). Contre : code et déploiement chez un compte tiers (kodekins), site anglophone au contenu ancien, Stripe actif tant que rien n'est fait, deux bases de code à maintenir si on le garde.

## Version B — le nouveau site (`customerservice-dot/retreats-holidays-live`, PR #25 fusionnée le 27/10 à 01h56 UTC, merge a81732c)

- **Servi sur** retreats-holidays-live.vercel.app (+ aperçu AppDeploy) — **invisible du domaine public** tant que les domaines ne sont pas vérifiés sur ce projet Vercel.
- **Vérifié dans le code et par test réel du chat le 27/10** (réponse ok, provider hostinger, environnement complet — le point `OPENROUTER_MODEL` du 19/10 est réglé) :
  - Johanna **seule assistante**, portrait féminin ; **relais humain unique : Jo Hanna, WhatsApp +230 5846 1923** — l'ancienne route « demande exclusive » (+20 155 644 3550) devient un alias du même numéro, et **le +33 7 58 50 41 73 disparaît entièrement du site**.
  - **Frais de mise en relation 2,99 €** : annoncés par Johanna uniquement au moment de la mise en relation (et dans le formulaire) ; Terms désormais bilingues, **frais prestataires 5 % supprimés**, le « non remboursable après 48 h » ne porte plus que sur les 2,99 €. ⚠️ **Aucun chemin de paiement actif dans l'app** (le `BookingModal` à « Proceed to Payment » n'est importé nulle part — code mort à purger) : les 2,99 € sont annoncés mais pas encaissables en ligne ; leur encaissement futur reste suspendu à l'arbitrage juridique, et la clause « non remboursable après 48 h » reste à confronter à la règle du 15/10 (pas de non-remboursable automatique) — les deux points sont au brief.
  - Offres conformes à la référence du 15/10 (Dahab/Nil/Mamers, aucun prix de séjour, images locales présentes) ; **Maurice passe de « bientôt » à « signature, programme à préciser ensemble »** (toujours non réservable) — évolution à valider par le propriétaire si elle ne vient pas de lui.
- Pour : code chez customerservice-dot, trilingue FR/EN/AR, conforme aux règles Johanna (testé), e-mail de mise en relation opérationnel (Resend configuré). Contre : bascule de domaine à faire (vérification sur le projet Vercel), contenu/SEO de l'ancien site à rapprocher ou assumer de perdre.

## La décision à prendre

| Choix | Ce qu'il implique |
|---|---|
| **Cible B (recommandation)** | Vérifier les domaines sur le projet Vercel `retreats-holidays-live` → le public reçoit la nouvelle version d'un coup ; l'ancien site kodekins devient obsolète (l'iframe n'a plus d'objet) et son parcours Stripe disparaît avec lui. Une seule base de code, chez vous. |
| **Cible A** | Garder kodekins en vitrine et y débloquer l'iframe parquée (+ purge Stripe). Maintient un site anglais ancien, une dépendance au compte tiers, et deux bases de code. La PR #25 resterait invisible du public. |

Dans les deux cas : **une seule bascule**, pas de DNS avant la décision, et l'encaissement des 2,99 € attend l'arbitrage juridique. Avant une bascule B : re-test du chat et du formulaire sur la version servie par le domaine, et vérification de l'expéditeur Resend.
