# Regrouper les comptes Google (Retreats Holidays / Exclusive Yoga Retreats / Pierre d'Égypte) et donner la chaîne YouTube à Johanna

*État au 13/10/2026. Pages d'aide officielles Google relues ce jour. Tout ce qui n'a pas pu être confirmé est marqué « à vérifier ». Les libellés français des menus Ads, GA4, Search Console, Merchant Center et suppression de compte sont traduits de l'anglais : à vérifier dans l'interface.*

## 0. CE QU'IL FAUT SAVOIR
- Il n'existe aucun outil pour fusionner deux comptes Google. L'ancien article « Merging accounts » (accounts/answer/63304) redirige désormais vers l'accueil de l'aide, mais c'est confirmé produit par produit :
  - « You can't merge or link separate YouTube channels » (youtube/answer/2404846) ;
  - « You can't merge contacts that are saved in different Google Accounts » (contacts/answer/7078226).
- Méthode officielle : on reste connecté à plusieurs comptes à la fois (photo de profil > « Ajouter un compte »), puis on déplace chaque produit séparément, et chaque accès pro vers le compte principal.

## 1. CHOISIR LE COMPTE PRINCIPAL
Ce choix est un raisonnement, pas une règle Google. Prenez le compte Google « standard » (pas un compte de marque) qui :
  - est déjà propriétaire principal du plus grand nombre d'actifs pro ;
  - sera lié à Shopify : l'appli Google & YouTube refuse les e-mails de compte de marque ;
  - peut avoir la 2SV.
Faites l'inventaire en vous connectant à chaque compte tour à tour :
  a) myaccount.google.com/brandaccounts : comptes de marque, dont la chaîne « Retreat Holidays ».
  b) myaccount.google.com/linkedapps, filtre « Sign in with Google » : repérez ChatGPT/OpenAI (compte « E »), Shopify, etc.
  c) Fiche d'établissement : Plus > Paramètres de la fiche d'établissement > Utilisateurs et accès.
  d) Google Ads : Admin > Accès et sécurité.
  e) GA4 : Admin > Gestion des accès.
  f) Search Console : Paramètres > Utilisateurs et autorisations. Notez qui est « propriétaire validé » et qui est « délégué ».
  g) Merchant Center : Accès et services > Personnes et accès. Business Manager : Personnes et accès.
  h) Shopify (Pierre d'Égypte) : Applis > Google & YouTube > Paramètres > « Google services ».
  i) Gmail : notez si vous utilisez « Consulter d'autres comptes », Gmailify ou « Envoyer en tant que » avec une adresse non Google (par exemple une adresse sur votre propre domaine, si ce domaine est hébergé ailleurs que chez Google ; hébergeur à vérifier).

## 2. SÉCURITÉ (avant tout transfert)
- Activez la validation en deux étapes (2SV) sur chaque compte conservé : Compte Google > Sécurité et connexion > « Comment vous connecter à Google » > Activer.
  - Préférez une clé d'accès (passkey) ou les invites Google au SMS.
  - Un nouveau numéro 2SV peut mettre jusqu'à 7 jours à être approuvé : faites-le en premier.
- La 2SV est obligatoire pour monétiser la chaîne (Programme Partenaire YouTube). Google Ads peut l'imposer à tous ses utilisateurs.
- Mettez à jour les informations de récupération de chaque compte.
- Johanna utilise son propre compte Google. Ne partagez jamais de mot de passe : Google le recommande pour la Fiche d'établissement et pour YouTube.

## 3. ACTIFS PROFESSIONNELS : ajouter d'abord, transférer ensuite, retirer en dernier
### 3a. Fiche d'établissement (si elle existe)
  1) Invitez le compte principal comme Propriétaire : Utilisateurs et accès > Ajouter > e-mail > Propriétaire > Inviter.
  2) Attendez 7 jours : avant, un nouvel utilisateur ne peut ni transférer la propriété principale, ni retirer d'autres utilisateurs, ni supprimer la fiche.
  3) L'actuel propriétaire principal (lui seul) transfère : utilisateur > Modifier > « Propriétaire principal » > Enregistrer. Le destinataire doit déjà être propriétaire ou administrateur.
  4) Seulement ensuite, l'ancien compte peut se retirer. Ses réponses aux avis restent visibles.
### 3b. Chaîne YouTube « Retreat Holidays » (@RetreatHolidays-v9b) pour Johanna
  - **Si « Johanna » est un agent IA (automatisation)** : les autorisations de chaîne ne suffisent pas — les utilisateurs invités n'ont pas accès aux API YouTube (limite confirmée par l'aide Google). Gardez la propriété de la chaîne et connectez l'outil d'automatisation (OAuth/API) avec le compte propriétaire, en limitant ses droits aux tâches voulues. L'invitation « Gestionnaire » reste la bonne solution pour une personne humaine.
  - Option simple, recommandée par YouTube : YouTube Studio > Paramètres > Autorisations > INVITER > e-mail de Johanna > rôle (par exemple Gestionnaire) > OK.
    - L'invitation expire au bout de 30 jours.
    - Si la chaîne est sur un compte de marque, le propriétaire principal doit d'abord passer aux « autorisations au niveau de la chaîne ».
    - Limite : avec ces autorisations, même le rôle Propriétaire « ne peut pas transférer la propriété ».
  - Si Johanna doit devenir propriétaire, la chaîne doit être sur un compte de marque :
    1) Se désinscrire des autorisations dans YouTube Studio. YouTube conseille de le faire uniquement pour un transfert, et il faudra réinviter tout le monde.
    2) Compte de marque > « Gérer les autorisations » > inviter Johanna comme Propriétaire.
    3) Après 7 jours, Johanna se désigne « Propriétaire principal » > Transférer.
  - Si la chaîne est sur un compte Google personnel : YouTube dit qu'on peut changer les gestionnaires mais pas les propriétaires, et qu'il faut d'abord passer en compte de marque. La procédure exacte de conversion est à vérifier.
  - Déplacer une chaîne vers un autre compte de marque n'est possible qu'entre comptes liés au même compte Google. Si la destination a déjà une chaîne, celle-ci est supprimée définitivement.
  - Shopify : le compte lié doit être Propriétaire ou Gestionnaire de la chaîne, et ne doit pas être un e-mail de compte de marque.
### 3c. Google Ads
  - Admin > Accès et sécurité > + > e-mail > accès « Admin » (nécessaire pour la facturation mensuelle).
  - Gardez au moins 2 admins : avec un seul admin, Google signale un risque de perdre l'accès aux balises.
  - Option : lier le compte à un compte administrateur via l'ID client.
### 3d. GA4
  - Admin > Gestion des accès > + > Ajouter des utilisateurs : compte principal en Administrateur au niveau du compte.
  - Le dernier Administrateur ne peut pas se supprimer lui-même.
  - Shopify demande au minimum le rôle Éditeur.
### 3e. Search Console
  - Ajoutez le compte principal comme propriétaire. Idéalement, il devient propriétaire validé avec son propre jeton (fichier HTML, balise ou DNS).
  - Quand vous retirez l'ancien propriétaire validé, supprimez aussi ses jetons, sinon il peut se revalider.
  - Prudence : un même jeton peut aussi servir à Merchant Center ou à Workspace.
### 3f. Merchant Center et Business Manager (boutique Pierre d'Égypte)
  - Ajoutez le compte principal en admin dans Merchant Center : Accès et services > Personnes et accès > Ajouter une personne.
  - Ajoutez-le aussi en super admin dans Business Manager : Personnes et accès > Ajouter une personne. L'invitation n'est valable que 7 jours.
  - Ne retirez pas la personne liée à la validation du site : sinon la validation et la revendication sont perdues.
  - Un admin ne peut partir que s'il reste un autre admin.
### 3g. Shopify (en dernier, à un moment calme)
  - Le compte Google lié doit être admin Merchant Center ET super admin Business Manager.
  - Le changement se fait dans Shopify : Applis > Google & YouTube > Paramètres > « Google services » > Déconnecter.
  - Déconnecter Merchant Center déconnecte aussi Ads, la Fiche d'établissement et YouTube.
  - Un compte Merchant Center ne peut être lié qu'à une seule boutique.
  - L'effet sur le flux produits pendant la bascule est à vérifier.

## 4. DONNÉES DU OU DES COMPTES SECONDAIRES VERS LE COMPTE PRINCIPAL
### 4a. Sauvegarde d'abord, avec Google Takeout (takeout.google.com) sur chaque compte secondaire
  - Exporter ne supprime rien.
  - L'archive expire au bout d'environ 7 jours et ne se télécharge que 5 fois.
  - Pas de filtre par dates.
  - Si l'archive est livrée dans le Drive d'un compte qu'on va supprimer, déplacez-la avant.
  - Dans l'export Gmail, les libellés sont dans l'en-tête X-Gmail-Labels, qu'aucun client de messagerie ne lit nativement.
  - Réimporter un .mbox dans Gmail : aucune méthode officielle trouvée (à vérifier).
### 4b. Gmail
  - Nouveaux messages : transfert automatique, toujours pris en charge.
    - Dans le compte secondaire : Paramètres > Voir tous les paramètres > Transfert et POP/IMAP > Ajouter une adresse de transfert.
    - Validez le lien reçu, puis cochez « Transférer une copie des messages reçus à » et « Conserver la copie originale Gmail dans la boîte de réception ».
    - Le spam n'est pas transféré.
  - Anciens messages : « Importer le courrier et les contacts ».
    - Dans le compte secondaire : Transfert et POP/IMAP > « Activer le protocole POP pour tous les messages ».
    - Dans le compte principal : Comptes et importation > Importer le courrier et les contacts > Lancer l'importation.
    - L'import est ponctuel : il copie les messages, pas les dossiers ni les libellés. Gmail transfère ensuite les nouveaux messages pendant 30 jours.
  - CHANGEMENTS 2026 : Google retire Gmailify et « Consulter d'autres comptes de messagerie » (relève POP).
    - Plus de nouveaux utilisateurs après le 1er trimestre 2026 (page 16604719).
    - « Gmail peut limiter les nouvelles configurations » en T3–T4 2026 (page 17101213).
    - Suppression totale en janvier 2027.
    - Les messages déjà importés restent dans Gmail.
    - À vérifier dans l'interface : Gmail accepte-t-il encore une NOUVELLE configuration avec une source @gmail.com ? Si non : transfert automatique + archive Takeout.
  - Continuer à écrire avec l'ancienne adresse Gmail : Comptes et importation > « Envoyer des e-mails en tant que » > Ajouter une autre adresse e-mail. Pour une adresse Gmail, ce n'est pas concerné par l'arrêt de 2027.
  - ALERTE : « Envoyer en tant que » avec une adresse non Google s'arrête en janvier 2027 (par exemple l'adresse du domaine si elle est hébergée ailleurs que chez Google). Alternatives citées par Google : un client de messagerie IMAP/SMTP, l'interface du fournisseur, ou Google Workspace pour un domaine personnalisé. Profitez de la période de transition actuelle pour migrer.
### 4c. Contacts
  - Dans le compte secondaire : contacts.google.com > tout sélectionner > Exporter > Google CSV.
  - Dans le compte principal : Importer > Sélectionner un fichier > Importer.
  - Limites : au-delà de 3 000 contacts, découpez en plusieurs fichiers ; le plafond est de 25 000 contacts.
  - Ensuite, « Fusionner et corriger » dans le compte principal pour les doublons.
### 4d. Agenda (sur ordinateur uniquement)
  - Dans le compte secondaire : Paramètres > Importer et exporter > Exporter. Vous obtenez un .zip.
  - Décompressez-le, puis importez chaque fichier .ics dans le compte principal : Paramètres > Importer et exporter > Sélectionner un fichier > choisir l'agenda > Importer.
  - Les invités et les visioconférences ne sont pas importés, et rien ne se synchronise.
  - Pour garder une synchronisation, partagez plutôt l'agenda avec le compte principal : Paramètres et partage > Partagé avec > « Modifier et gérer le partage ».
### 4e. Drive (entre comptes personnels)
  1) Partagez les éléments avec le compte principal.
  2) Partager > flèche à côté du nom > « Transférer la propriété ».
  3) Dans le compte principal, recherchez pendingowner:me > Partager > Accepter.
  - Transférer un dossier ne transfère pas les fichiers qu'il contient : sélectionnez les fichiers eux-mêmes.
  - Le stockage passe au nouveau propriétaire : vérifiez l'espace disponible.
  - Impossible d'annuler une fois le transfert accepté.
  - Impossible de transférer vers un compte professionnel (Workspace).
### 4f. Photos
  - Dans l'appli Android du compte secondaire : Paramètres Photos > Partage > Partage avec un partenaire > « Toutes les photos », depuis toujours.
  - Dans le compte principal : « Enregistrer dans votre compte » > Toutes les photos.
  - Un seul partenaire à la fois.
  - Les photos enregistrées ne comptent pas dans le stockage tant que le partenaire partage. Ce qui se passe si le compte source arrête de partager ou est supprimé est à vérifier : prévoyez l'espace.
### 4g. Achats YouTube et Play : ils sont perdus si le compte est supprimé. Leur transfert n'est pas documenté (à vérifier).

## 5. CONNEXIONS « SE CONNECTER AVEC GOOGLE » (ChatGPT avec le compte « E », Shopify…)
- Le compte Google et le compte de l'application restent distincts. Changer d'identité se fait chez l'éditeur (OpenAI, Shopify) : procédure à vérifier chez eux.
- Si le compte Google est supprimé, ses identifiants « Se connecter avec Google » sont supprimés et le bouton ne marche plus.
- Donc : d'abord ajoutez une autre méthode de connexion dans l'appli (mot de passe, autre compte ; à vérifier chez OpenAI). Ensuite seulement, retirez le lien : Applications associées > Se connecter avec Google > Voir les détails > Arrêter d'utiliser > Confirmer.
- Retirer le lien ne supprime pas vos données dans l'appli.

## 6. CE QU'IL NE FAUT PAS SUPPRIMER, ET L'ORDRE
Ne supprimez aucun compte tant qu'il est encore :
  - propriétaire principal de la chaîne YouTube : la chaîne serait supprimée avec lui ;
  - propriétaire principal d'une Fiche d'établissement ;
  - dernier Administrateur GA4 ou seul admin Google Ads ;
  - propriétaire validé Search Console, ou personne liée à la validation Merchant Center ;
  - super admin Business Manager, ou compte lié à Shopify ;
  - utilisé pour « Se connecter avec Google » ;
  - sans archive Takeout téléchargée hors de ce compte.
Rappels :
  - Une adresse Gmail supprimée ne pourra jamais être réutilisée.
  - Supprimer un compte ne supprime pas les autres.
  - La récupération n'est possible que peu de temps après (délai non publié).
Option prudente : gardez les comptes secondaires vidés, sécurisés et avec transfert automatique plutôt que de les supprimer. Connectez-vous-y de temps en temps : Google peut supprimer un compte inactif depuis 2 ans.
Ordre conseillé :
  1) Inventaire.
  2) 2SV et informations de récupération.
  3) Inviter le compte principal (et Johanna pour YouTube) partout, en gardant 2 admins.
  4) Attendre 7 jours.
  5) Transférer la propriété principale (Fiche d'établissement, compte de marque YouTube).
  6) Merchant Center, Business Manager, puis Shopify.
  7) Déplacer les données : Drive, Contacts, Agenda, Photos, Gmail.
  8) Basculer les connexions tierces (ChatGPT…).
  9) Faire un Takeout final.
  10) Retirer les anciens comptes des outils.
  11) Éventuellement seulement : supprimer un compte (Données et confidentialité > « Vos options de données et de confidentialité » > Plus d'options > Supprimer votre compte Google).

## 7. OPTION GOOGLE WORKSPACE (adresse pro sur votre domaine : exclusiveyogaretreats.com, retreats-holidays.com ou pierredegypte.online)
- Tarifs standards par utilisateur et par mois (page mise à jour le 09/10/2026) :
  - Business Starter : 6,80 € en annuel, 8,10 € en flexible ;
  - Business Standard : 13,60 € / 16,20 € ;
  - Business Plus : 21,10 € / 25,30 €.
  Prix exact pour la France et TVA : à vérifier. Essai de 14 jours.
- L'abonnement annuel engage pour toute la durée (pas de remboursement en cas de résiliation anticipée). Le flexible se résilie sans pénalité.
- L'outil d'importation de données (console d'administration > Données > Importation et exportation > Importation, super admin) importe un compte Gmail personnel : e-mails, libellés, suivis.
  - Le titulaire du compte doit autoriser la demande sous 24 h.
  - Il faut une licence Workspace pour le compte de destination.
  - L'agenda et les contacts se déplacent à la main (.ics, CSV/vCard).
- Attention :
  - La propriété Drive ne se transfère pas d'un compte personnel vers Workspace.
  - Si un compte Google personnel existe déjà sur une adresse de ce domaine, il devient un « compte non géré » en conflit, à régler dans la console.
  - Un admin Workspace peut bloquer « Se connecter avec Google » (erreur 400 admin_policy_enforced).
  - La 2SV devient obligatoire pour les administrateurs Workspace.
  - YouTube géré depuis un compte Workspace : à vérifier.

## Sources principales (aide Google, 13/10/2026)

- Gmail, fin de Gmailify et de la relève POP : https://support.google.com/mail/answer/16604719
- Gmail, fin de « Envoyer en tant que » pour les adresses non Google (janvier 2027) : https://support.google.com/mail/answer/17101213
- Gmail, importer des e-mails d'un autre compte : https://support.google.com/mail/answer/21289
- Plusieurs comptes connectés : https://support.google.com/accounts/answer/1721977
- YouTube, chaînes non fusionnables : https://support.google.com/youtube/answer/2404846
- YouTube, autorisations de chaîne : https://support.google.com/youtube/answer/9481328
- Contacts, non fusionnables entre comptes : https://support.google.com/contacts/answer/7078226
