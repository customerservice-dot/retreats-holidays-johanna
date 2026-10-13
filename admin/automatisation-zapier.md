# Automatisation Zapier — demandes clients (Pierre d'Égypte + Retreats Holidays)

*Vérifié le 13/10/2026 sur zapier.com, l'aide Zapier, la documentation d'Anthropic et d'OpenAI, et cnil.fr. Principe : **l'IA prépare, vous envoyez.** Aucune réponse ne part automatiquement.*

## 1. Ce qu'il faut savoir avant de commencer

- **Plan Zapier :** le plan gratuit ne permet que des Zaps à 2 étapes (100 tâches/mois) : insuffisant. Il faut **Professional**, à partir de 19,99 $/mois en annuel (29,99 $ en mensuel), avec **14 jours d'essai sans carte** ([tarifs](https://zapier.com/pricing)). Paths, Filter et Formatter sont inclus et ne consomment pas de tâches.
- **L'IA, deux options :**
  - **« AI by Zapier »** (le plus simple) : intégré à Zapier, **sans clé API**, avec des modèles Claude et ChatGPT au choix ; il consomme 1, 3 ou 5 tâches par exécution selon le niveau de modèle.
  - **Applis « ChatGPT (OpenAI) » et « Anthropic (Claude) »** : il faut une **clé API** et un crédit prépayé chez chacun, **facturés à part** des abonnements ChatGPT Plus ou Claude. Collez les clés uniquement dans la fenêtre de connexion de Zapier, jamais dans une conversation, et fixez un plafond de dépense mensuel dans chaque console.
  - Coût de l'IA : quelques centimes par mois pour quelques centaines de courts brouillons avec les petits modèles (par exemple Claude Haiku 5.5 : 0,10 $ / 0,50 $ par million de jetons en entrée / sortie).
- **Combien de demandes par mois ?** Le plan Professional inclut 750 tâches par mois. Avec « AI by Zapier » sur un modèle Claude (3 à 5 tâches par étape IA), une demande traitée par le Zap 1 (tri + brouillon + contrôle + brouillon Gmail + suivi) consomme environ 11 à 17 tâches : **environ 45 à 70 demandes par mois**. Avec vos propres clés API (1 tâche par étape IA), environ 5 tâches par demande : **environ 150 demandes par mois**. Le déclencheur, Paths, Filter et Formatter ne consomment pas de tâches.
- **Validation :** l'étape « Gmail → Create Draft Reply » crée un **brouillon** dans Gmail : vous relisez et cliquez sur Envoyer. C'est la validation la plus simple. (Zapier propose aussi « Human in the Loop » → « Request Approval », sur plan payant.)
- **Ce qui peut déclencher un Zap :**
  - **Gmail** « New Email Matching Search » (si votre adresse de vente n'est pas une boîte Gmail, transférez-la d'abord automatiquement vers la boîte Gmail principale) : e-mails reçus sur votre adresse de vente, **formulaire de contact Shopify** (il arrive par e-mail) et **notifications Leboncoin** (Leboncoin envoie un e-mail à chaque nouveau message ; un pro peut répondre par e-mail, l'adresse de l'acheteur reste masquée).
  - **WhatsApp :** seulement via l'**API WhatsApp Business** (compte Meta Business, appli premium). Un numéro WhatsApp ordinaire ne fonctionne pas. À laisser pour plus tard.
  - **Instagram :** pas de déclencheur pour les commentaires ni les messages privés. Non automatisable dans Zapier.
  - **Facebook Lead Ads** (« New Lead », premium) : seulement si vous lancez des publicités avec formulaire.

## 2. Zap 1 — Demandes entrantes (à créer en premier)

| Étape | Appli → action | Réglages |
|---|---|---|
| 1. Déclencheur | **Gmail → New Email Matching Search** | Compte : votre adresse de vente. Recherche, par exemple : `in:inbox -from:me newer_than:2d` (affinez ensuite). |
| 2. Tri | **AI by Zapier** (ou ChatGPT → Extract Structured Data) | Champs à extraire : `activite` (PIERRE / RETRAITE / AUTRE), `type_client` (PARTICULIER / PRO / INCONNU), `surface_m2`, `ville`, `usage`, `langue`. Ne rien extraire d'autre. |
| 3. Aiguillage | **Paths** | Chemin A : activite = PIERRE. Chemin B : activite = RETRAITE. Chemin C (par défaut) : rien, juste le suivi. |
| 4. Brouillon | **AI by Zapier** (ou ChatGPT) | Prompt 1 ci-dessous (version A ou B selon le chemin). |
| 5. Contrôle | **AI by Zapier** (modèle Claude) ou **Anthropic (Claude) → Send Message** | Prompt 2 ci-dessous. |
| 6. Brouillon Gmail | **Gmail → Create Draft Reply** | Corps : **uniquement le champ `texte`** renvoyé par l'étape 5, jamais le JSON entier (si l'étape IA sort le JSON brut, ajoutez une étape Formatter → Extract pour isoler `verdict` et `texte`). |
| 6 bis. Marquage « à revoir » | **Paths** puis **Gmail → Add Label to Email** | « Create Draft Reply » ne permet pas de modifier l'objet. Si `verdict = A_REVOIR` : appliquez un libellé Gmail « À REVOIR » au message reçu (créez le libellé une fois dans Gmail), et éventuellement une alerte (étape 8). |
| 7. Suivi | **Google Sheets → Create Spreadsheet Row** (ou Zapier Tables) | Date, source, activité, type de client, ville, m², usage, statut « brouillon prêt ». **Pas de nom, téléphone, e-mail ni adresse.** |
| 8. Alerte (facultatif) | Gmail → Send Email à vous-même, ou WhatsApp Notifications (premium) | « Nouveau brouillon à relire ». |

## 3. Zap 2 — Prospection des professionnels (une fois par semaine)

| Étape | Appli → action | Réglages |
|---|---|---|
| 1. Déclencheur | **Schedule by Zapier → Every Week** | Lundi, 9 h. |
| 2. Sélection | **Google Sheets → Lookup Spreadsheet Rows** | Feuille « Tous les clients » (`clients-potentiels.xlsx` importé dans Google Sheets) : Catégorie = Pro France, Statut = « À contacter », Priorité = 1. **10 lignes au maximum.** |
| 3. Une ligne à la fois | **Looping by Zapier** | Boucle sur les lignes trouvées (10 au maximum). |
| 4. Brouillon | **AI by Zapier** | Prompt 1, version C (e-mail aux pros), avec la colonne « Pourquoi les contacter ». |
| 5. Contrôle | **AI by Zapier** (Claude) | Prompt 2. |
| 6. Brouillon Gmail | **Gmail → Create Draft** | À l'adresse de contact **professionnelle** de l'entreprise. |
| 7. Mise à jour | **Google Sheets → Update Spreadsheet Row** | Statut = « Brouillon prêt », date. |

Règles ([CNIL](https://www.cnil.fr/fr/la-prospection-commerciale-par-courrier-electronique-sms-mms-et-automate-dappel)) : un e-mail de prospection à un professionnel est permis s'il concerne son métier, s'il identifie l'expéditeur et s'il permet de refuser simplement les prochains messages. **Jamais de prospection par e-mail vers des particuliers sans leur accord préalable**, ni d'appel à un particulier sans son consentement (depuis le 11/08/2026).

## 4. Prompt 1 — Rédaction (à coller dans l'étape « brouillon »)

```
Tu rédiges des BROUILLONS de réponse en français pour une petite entreprise
française. Un humain relit et envoie chaque brouillon : tu ne promets rien
qui n'est pas écrit ci-dessous.

Ton : poli, simple, court (8 à 12 lignes), vouvoiement. Signe « Pierre d'Égypte »
pour la pierre et « Retreats Holidays » pour les retraites. Réponds dans la
langue du message reçu si ce n'est pas le français.

Message reçu :
{{texte du message}}
Données extraites : activité={{activite}}, client={{type_client}},
surface={{surface_m2}}, ville={{ville}}, usage={{usage}}

=== A. PIERRE (MINYALA) ===
Faits autorisés :
- MINYALA : calcaire naturel d'Égypte, dalles 30 × 60 × 2 cm, en stock.
- Prix public : 35 € TTC le m², pierre seule. Minimum 25 m², soit 875 €.
- Environ 5,6 dalles au m² ; environ 50 kg/m² (estimation).
- Retrait sur rendez-vous à Gennevilliers (92), du lundi au vendredi,
  9h30-12h et 13h-15h. Le client peut venir voir les dalles. La vente se
  conclut au dépôt.
- Livraison sur devis à partir de 100 m².
- Nous vendons la pierre ; nous n'assurons pas la pose.
- Usages : sol intérieur ; en extérieur, TOUJOURS « selon la finition,
  le support et la pose ».
Demande au client ce qui manque : surface en m², ville, usage.
Si le client est (ou se dit) professionnel : ne donne AUCUN prix professionnel ;
demande le nom de l'entreprise, son SIRET et la surface, et écris qu'un devis
écrit suivra.

=== B. RETRAITES (Retreats Holidays) ===
Faits autorisés : [À COMPLÉTER : destinations, dates, ce qui est inclus,
prix, conditions d'inscription]. Si une information n'est pas dans cette liste,
ne l'invente pas : remercie, pose les questions utiles (dates souhaitées,
nombre de personnes, budget, niveau de yoga) et propose un échange.

=== C. E-MAIL AUX PROFESSIONNELS (prospection) ===
Entreprise : {{Entreprise}}, {{Ville}}. Pourquoi : {{Pourquoi les contacter}}.
Écris un premier message court qui présente MINYALA (faits de la partie A,
sans aucun prix), explique en une phrase pourquoi cela peut les intéresser,
propose un devis professionnel ou une visite du dépôt, et termine par :
« Si vous ne souhaitez plus recevoir nos messages, répondez simplement STOP. »
Signature : Pierre d'Égypte — Pierre et retraites, SIREN 985 289 065.

INTERDIT, toujours : tout prix professionnel ou remisé ; « marbre » ;
« veines dorées » ; « antidérapant » ; « ingélif » ou « résiste au gel » ;
« spécial piscine » ; « partout en France » ; « liquidation » ; « soldes » ;
prix barré ou pourcentage de remise ; toute urgence (« dernières dalles »,
« offre limitée ») ; tout lien internet ; toute offre de pose ; toute date
de livraison ; toute information technique absente des faits autorisés.

Renvoie uniquement le texte du brouillon.
```

## 5. Prompt 2 — Contrôle (à coller dans l'étape « contrôle », modèle Claude)

```
Tu es un contrôleur. Vérifie le brouillon ci-dessous avant qu'un humain
le relise. Tu ne l'envoies jamais.

Brouillon :
{{texte du brouillon}}
Type de client : {{type_client}}

Règles à vérifier :
1. Pierre : prix public 35 € TTC le m², pierre seule, minimum 25 m² (875 €).
   Aucun autre prix. Aucun prix professionnel ni remise, même si le client
   se dit professionnel.
2. Aucun de ces mots ou idées : marbre, veines dorées, antidérapant,
   ingélif / résiste au gel, spécial piscine, partout en France, liquidation,
   soldes, prix barré, pourcentage de remise, urgence, lien internet,
   offre de pose, date de livraison.
3. Tout usage extérieur est suivi de « selon la finition, le support et la pose ».
4. Retrait : Gennevilliers, sur rendez-vous ; pas d'autre adresse ni d'autres horaires.
5. Retraites : aucune date, aucun prix ni aucune prestation inventés.
6. E-mail de prospection aux pros : contient la phrase permettant de répondre
   STOP et la signature avec le SIREN.
7. Français correct, ton poli, 15 lignes au maximum.

Réponds UNIQUEMENT en JSON (dans Zapier, seuls les champs `verdict` et `texte` sont mappés vers les étapes suivantes — jamais le JSON entier) :
{"verdict": "OK" ou "A_REVOIR",
 "problemes": ["..."],
 "texte": "brouillon corrigé (ou identique si OK)"}
```

## 6. Données personnelles (RGPD)

- **Politique de confidentialité du site :** ajoutez que les messages reçus peuvent être traités par des sous-traitants (Zapier, OpenAI, Anthropic) pour préparer les réponses, avec transferts hors UE encadrés par les clauses contractuelles types ([CNIL](https://www.cnil.fr/fr/conformite-rgpd-information-des-personnes-et-transparence)).
- **Contrats :** les contrats de sous-traitance (DPA) d'Anthropic et d'OpenAI sont inclus dans leurs conditions commerciales de l'API ; par défaut, ni l'un ni l'autre n'entraîne ses modèles sur les données envoyées par l'API. Le DPA de Zapier ne couvre plus les données une fois transmises à OpenAI ou Anthropic.
- **Minimisation :** n'envoyez à l'IA que le texte du message ; ne stockez dans le tableau aucun nom, téléphone, e-mail ni adresse.
- **Pas de décision automatique :** l'humain relit et envoie chaque réponse.

## 7. Sécurité

- Connectez-vous à Zapier **vous-même**, sur votre appareil, avec le compte principal ; activez la double authentification dans Zapier (Settings → Security).
- Ne tapez jamais un mot de passe ou un code dans un navigateur partagé avec un assistant.
- Clés API : uniquement dans la fenêtre de connexion de Zapier ; plafond de dépense dans la console OpenAI et dans la console Claude ; supprimez une clé dès qu'elle a été partagée par erreur.

## 8. Fiabiliser le suivi Gmail avant toute relance (ajout du 13/10)

Le 12/10, 19 e-mails de prospection sont partis depuis une boîte Hotmail personnelle, en copie vers info@pierredegypte.online (qui arrive dans la boîte Gmail connectée). Constats et règles détaillés dans `minyala/suivi-envois.md`. L'essentiel pour les Zaps :

- **Jamais le threadId comme identifiant d'un prospect** : Gmail regroupe les envois au même objet dans une seule conversation (16 messages = 1 fil). L'identifiant fiable = **l'adresse e-mail du destinataire** + l'ID individuel de chaque message.
- **Anti-doublon obligatoire** : avant chaque envoi, chercher l'adresse dans la colonne « E-mail (contact) » du fichier de suivi ; tout statut autre que « À contacter » bloque l'envoi.
- **Objet unique par destinataire** (« MINYALA — [Entreprise] ») pour éviter le regroupement.
- **Un seul expéditeur : la boîte Gmail connectée.** Les envois Hotmail rendent réponses et échecs invisibles (pas de Reply-To) et finissent en spam (14 copies sur 19).
- **Classement entrant** : réponse réelle = expéditeur chez le prospect + In-Reply-To ; écho de nos envois = expéditeur interne ; échec = mailer-daemon/postmaster. Réponse « non »/« STOP » → « Ne plus contacter », sans relance.
- **Une seule relance par prospect**, après vérification manuelle de la boîte Hotmail pour la vague du 12/10.

## 9. Étape « Request Approval » du circuit Johanna (ajout du 13/10, après vérification)

- **Champ à envoyer à Gmail : le brouillon approuvé, avec repli.** « Edited Content Brouillon » n'existe que si le relecteur a modifié le texte. Ajoutez une étape **Formatter → Text → Default value** : valeur = « Edited Content Brouillon », défaut = le champ `texte` d'origine. C'est la sortie de cette étape qui va dans Gmail — ainsi l'envoi marche aussi bien pour une approbation sans correction qu'avec correction.
- **Filtre après l'approbation :** continuer seulement si `Decision = approved` ; « Action if reviewer declines » = Stop run ; **délai d'expiration** (72 h conseillé) avec action « End run » — une expiration arrête l'envoi, elle ne répond pas au client : prévoir la **notification immédiate** à l'arrivée de la demande et un **rappel à 12 h** (réglage « reminders » de l'étape) pour tenir l'objectif de réponse sous 24 h.
- **Test final avant publication, sur une adresse de test, 4 cas :** approbation sans modification, approbation avec modification, refus, expiration. Vérifier à chaque fois ce que Gmail reçoit (ou ne reçoit pas).
- Le Zap Johanna reste en **Draft** avec un déclencheur limité à l'objet `RH_TEST_JOHANNA` tant que ces tests ne sont pas passés ; ensuite, élargir le déclencheur aux vraies demandes puis publier.
- **Dépassé le 13/10 au soir** : le propriétaire a demandé « Direct full automatisation » et l'étape d'approbation a été retirée — voir § 11. Cette section reste la référence si l'on revient au circuit avec approbation.

## 10. Registre et classement des messages (spécification adoptée le 13/10, après l'audit croisé Gmail + Hotmail)

**Boîte de production.** Les connexions du serveur MCP Zapier et celles de l'éditeur de Zaps sont distinctes : dans l'éditeur, connecter la boîte **customerservice@exclusiveyogaretreats.com** (elle reçoit déjà info@pierredegypte.online) comme compte Gmail de production ; la boîte botpress ne sert qu'aux tests. Ne pas élargir le déclencheur de test : créer le déclencheur de production sur la boîte de production.

**Plus aucun envoi depuis Hotmail** (rejets 5.7.520 en sortie — voir `minyala/suivi-envois.md`). Un 5.7.520 se diagnostique (contenu, volume, réputation), il ne se « réessaie » pas en boucle.

**Classes de classement** (décision recalculée sur les en-têtes du message précis, jamais sur le fil ; les libellés Gmail sont des aides visuelles) :
SORTANT · COPIE_SORTANTE (expéditeur propre + destinataire externe, rattachée par Message-ID RFC + destinataire) · ÉCHEC (notification de transport : rattacher par Message-ID original et Final-Recipient, jamais par le simple champ To) · AUTOMATIQUE (Auto-Submitted, absence, challenge antispam : jamais compté comme réponse humaine) · RÉPONSE_COMMERCIALE (In-Reply-To/References vers un Message-ID connu + expéditeur cohérent ; un « Re: » ou une offre citée ne suffit pas) · OPPOSITION (STOP/« non » : blocage immédiat, alias compris) · REVUE_MANUELLE (en-têtes incomplets, Reply-To inconnu, plusieurs prospects possibles : aucun destinataire automatique).

**Amorce du registre** : les identifiants des 19 envois du 12/10 (Gmail ID, Thread ID, **Message-ID RFC d'origine**, heures UTC et Le Caire, dossier de la copie) sont consignés dans `minyala/registre-envois-2026-10-12.csv` — delivery_key prête pour rapprocher réponses et échecs.

**Clés d'identité** : event_key = fournisseur+compte+message_id ; delivery_key = Message-ID RFC original + adresse destinataire (valeur brute, jamais reconstruite) ; contact_id interne avec table d'alias validés ; account_id = entreprise (SIREN/SIRET) distincte des contacts (ne pas fusionner tous les Gedimat) ; case_id = activité+contact+demande ; action_key = activité+campagne+contact+type+n° de relance. **Réservation atomique** avant toute rédaction (un Lookup puis un Create séparés ne sont pas un verrou) ; registre technique à accès restreint, séparé du classeur commercial.

**Règle corrigée sur les brouillons** : « Create Draft Reply » avec Thread ID ne vaut que pour un fil à UN SEUL client (une vraie demande entrante). Pour les deux fils de prospection multi-destinataires du 12/10 : brouillon indépendant, un seul destinataire vérifié, pas de Cc/Bcc, pas de Thread ID hérité, pas de « répondre à tous » — et l'IA ne choisit jamais To/Cc/Bcc.

**Avant chaque envoi** : revérifier réponses, oppositions, échecs et actions intervenues depuis la préparation ; distinguer brouillon / tentative / accepté par le fournisseur / remis / réponse / vente. Un envoi accepté n'est pas une remise ; un délai dépassé n'est pas un échec.

## 11. État déployé le 13/10 au soir — envoi automatique sans approbation (décision du propriétaire)

Le propriétaire a demandé **« Direct full automatisation »** : l'étape d'approbation humaine (§ 9) a été retirée du circuit Johanna, qui envoie désormais seul.

**Ce qui tourne :**
- **Zap « Johanna » — id 383400721, version 1, PUBLIÉ et ACTIF.** Déclencheur : boîte retreatsholidaysbotpress@gmail.com (`in:inbox` + borne de date), « Never replay » activé. Étapes : rédaction IA → contrôle IA → filtre (décision SEND + contrôle OK + texte non vide) → Gmail « Reply to Email ». Test envoyé et reçu (messages 1a136c1c7f4380fa / 1a136c1dd1d3f9c6).
- **Zap « Pierre d'Égypte » — id 383400957, BROUILLON.** Ne pas publier tant que : 1) l'expéditeur **info@pierredegypte.online n'est pas vérifié pour l'ENVOI** dans Gmail (« Send mail as » — la redirection en réception ne suffit pas) ; 2) la boîte de production (customerservice@) n'est pas connectée **dans l'éditeur** de Zaps (§ 10).

**Règle de non-simultanéité (impérative).** La variante « brouillons + approbation » (§ 2–§ 9) et la variante « envoi automatique » ne doivent **jamais être actives en même temps sur la même boîte** : même message traité deux fois = double réponse au client. Un seul Zap actif par boîte.

**Garde-fous encore absents en mode auto** (la spécification du 13/10 les liste elle-même comme « à réaliser ») : registre partagé, verrou atomique, vérification des réponses humaines, rapprochement inter-boîtes — donc **aucune garantie d'envoi unique entre plusieurs workflows**. Tant qu'ils manquent :
- un seul Zap actif par boîte (voir ci-dessus) ;
- le filtre ne protège pas contre les expéditeurs automatiques : exclure dans le déclencheur ou en filtre `mailer-daemon@`, `postmaster@`, `no-reply`/`noreply`, nos propres adresses, et tout message avec en-tête Auto-Submitted — sinon le Zap répond aux notifications et newsletters ;
- toute réponse entrante contenant « STOP »/« non » doit interrompre le circuit (classe OPPOSITION, § 10) — à vérifier dans la v1, qui ne semble pas la traiter ;
- le prompt Retreats reste sans catalogue vérifié (partie B « À COMPLÉTER ») : les réponses doivent rester des questions de qualification — jamais de prix, de disponibilité ou d'engagement inventés ;
- **revue quotidienne la première semaine** : relire chaque envoi automatique (libellé/dossier des messages envoyés) et couper le Zap au premier envoi incorrect ;
- les **11 tests locaux du 13/10** portaient sur la correspondance des messages et les doublons : ils ne valident **ni** l'étape d'approbation retirée, **ni** le comportement du Zap publié en conditions réelles — la revue quotidienne ci-dessus n'est donc pas optionnelle.

**Échéance** : essai Zapier de 14 jours ouvert le 13/10 → décision avant ~27/10 (abonnement Professional ou retour aux brouillons § 9, sans quoi le Zap multi-étapes s'arrête). Périmètre couvert aujourd'hui : uniquement la boîte botpress (tests Retreats Holidays) ; **aucune demande Pierre d'Égypte n'est traitée automatiquement**.
