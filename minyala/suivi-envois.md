# Suivi des envois de prospection — 12/10/2026

*Reconstitué le 13/10/2026 à partir des copies reçues dans la boîte Gmail (customerservice@, qui reçoit aussi les e-mails adressés à info@pierredegypte.online). Objet des envois : « MINYALA à 27 €/m² — stock en France » (fil 2 : « … 27 €/m² TTC … »).*

## Ce qui s'est passé

- **19 e-mails de prospection au tarif professionnel** ont été envoyés le 12/10/2026 (14h58–15h04, puis 17h56–17h57) **depuis la boîte Hotmail personnelle de Joseph** (joseph.h…@hotmail.fr), chacun **en copie (CC) à info@pierredegypte.online** — c'est cette copie qui apparaît dans Gmail.
- Tous les destinataires sont des **professionnels** (marbreries, négoces, showrooms, paysagistes) : le tarif pro leur est réservé, c'est conforme à la règle. Le corps du message identifie l'expéditeur et contient une ligne de désinscription (« Pas intéressé ? Répondez "non" pour ne plus être contacté »). Manque : le SIREN dans la signature (à ajouter aux prochains envois).
- **Gmail a regroupé les 16 premiers envois dans UNE seule conversation** (même objet), et les 3 suivants dans une autre. L'identifiant de conversation (threadId) ne doit donc **jamais** servir d'identifiant d'un prospect.
- **14 copies sur 19 sont arrivées en SPAM** dans notre propre boîte. Mauvais signe pour la délivrabilité chez les destinataires (expéditeur Hotmail personnel, envoi en rafale).
- **Sans Reply-To, les réponses et les avis d'échec de remise arrivent dans la boîte Hotmail**, pas dans Gmail. Aucune réponse ni aucun échec n'est visible côté Gmail au 13/10 (sauf si un destinataire fait « répondre à tous », auquel cas sa réponse arrivera aussi sur info@). **→ À vérifier à la main dans la boîte Hotmail.**

## Les 19 envois

| # | Destinataire | E-mail | Heure | Copie reçue | ID Gmail de la copie |
|---|---|---|---|---|---|
| 1 | PMC Marbrerie | contact@pmc-marbrerie.com | 14:58 | Boîte de réception | 1a1309f0f02bda8f |
| 2 | Sauvaje | contact@sauvaje.fr | 14:59 | **Spam** | 1a130a054e241ce2 |
| 3 | ABL Négoce | contact@ablnegoce.fr | 14:59 | Boîte de réception | 1a130a07fa10f16f |
| 4 | Nivault | info@nivault.com | 14:59 | **Spam** | 1a130a0862a5bb04 |
| 5 | Le Holloco (Herblay) | materiaux@leholloco.fr | 15:00 | **Spam** | 1a130a15994fe2c1 |
| 6 | Carrelages Dente | carrelagesdente@gmail.com | 15:00 | **Spam** | 1a130a165f8766ec |
| 7 | Tragin SAS | tragin-sa@wanadoo.fr | 15:00 | **Spam** | 1a130a17e1bab341 |
| 8 | MDY — Marbrerie des Yvelines | contact@mdy-france.com | 15:01 | **Spam** | 1a130a275502b1f4 |
| 9 | Parquet-Carrelage.com | contact@parquet-carrelage.com | 15:01 | Boîte de réception | 1a130a2869df463d |
| 10 | MCA Matériaux Cuisines Aménagements (Achères) | contact@mca-materiaux.net | 15:03 | Boîte de réception | 1a130a3e99411876 |
| 11 | Gedimat — Aux Docks de Clamart | expo@docksclamart.fr | 15:03 | **Spam** | 1a130a3f52a3ee9b |
| 12 | Gedimat Sefor Houilles | guillaume.lallet@gedimat.fr | 15:03 | **Spam** | 1a130a40c849eb38 |
| 13 | Batimantes (Colombes) | colombes.expo@batimantes.fr | 15:03 | **Spam** | 1a130a42bbf7cd72 |
| 14 | Kap Carrelage Domont | contact@kap-carrelage.store | 15:04 | **Spam** | 1a130a4f7ddfeddc |
| 15 | Qua Ceramic (Piscop) | qua.ceramic@gmail.com | 15:04 | **Spam** | 1a130a507eb3eec4 |
| 16 | FLIPO (Pantin) | flipo@flipo.fr | 15:04 | **Spam** | 1a130a51de806451 |
| 17 | ISL Carrelage * | isl.carrelage@gmail.com | 17:56 | Boîte de réception | 1a131423fb33a322 |
| 18 | David Paysage * | davidelagagepaysage@gmail.com | 17:57 | **Spam** | 1a13142fb5c3a1c0 |
| 19 | TerraConcept * | terraconceptservicecommercial@gmail.com | 17:57 | **Spam** | 1a1314310a7fe6cf |

\* Absent de la liste de prospection d'origine : ajouté aux classeurs le 13/10 (fiche à compléter). MCA Matériaux figurait déjà dans la liste (France Matériaux, Achères) : ligne fusionnée le 13/10.

« Copie reçue » décrit **notre copie de suivi**, pas la boîte du destinataire : un envoi peut très bien avoir été remis chez lui alors que notre copie est en spam, et inversement. Seule la boîte Hotmail (réponses, avis d'échec) permet d'en savoir plus.

## Ce qui a été mis à jour le 13/10

- `prospects-minyala.xlsx` (onglet Prospects) et `clients-potentiels.xlsx` (onglet Tous les clients) : les 19 lignes passent en **Statut « Contacté », date 12/10/2026**, avec l'adresse e-mail dans la nouvelle colonne **« E-mail (contact) »** et la localisation de la copie en Notes. Les 4 destinataires hors liste ont été ajoutés.
- **Ne plus régénérer ces classeurs avec les anciens scripts de construction** : cela effacerait le journal des contacts.

## Règles pour les automatisations (Zapier) — à respecter avant toute relance

1. **Identifiant d'un prospect = son adresse e-mail (en minuscules)**, jamais le threadId : Gmail regroupe par objet identique (16 envois = 1 conversation). Chaque message garde son propre ID : c'est lui qu'on journalise.
2. **Avant tout envoi, chercher l'adresse dans la colonne « E-mail (contact) »** : statut « Contacté », « Relancé », « Pas intéressé » ou « Ne plus contacter » → ne pas envoyer. C'est la protection anti-doublon.
3. **Un objet unique par destinataire** (par exemple « MINYALA — [nom de l'entreprise] ») pour empêcher le regroupement en une seule conversation.
4. **Un seul expéditeur : la boîte Gmail connectée** (info@pierredegypte.online y arrive déjà). Plus d'envois depuis Hotmail : réponses et échecs y restent invisibles pour l'automatisation, et la délivrabilité est mauvaise.
5. **Classer les messages entrants** :
   - vraie réponse commerciale : expéditeur = l'adresse (ou le domaine) d'un prospect, en-tête In-Reply-To présent ;
   - écho de nos envois : expéditeur = nos propres adresses (Hotmail ou Gmail) → à étiqueter « PROSPECTION/ENVOYÉ », jamais traité comme une réponse ;
   - échec de remise : expéditeur mailer-daemon@ / postmaster@, objet « Delivery Status Notification » / « Undelivered » → statut « E-mail invalide ».
6. **Toute réponse « non » ou « STOP » → statut « Ne plus contacter »** immédiatement, et aucune relance.
7. **Une seule relance** par prospect (vers le 19/10 pour cette vague — *avancée au 16–17/10 par les directives du 15/10, `directives-chatgpt-prospection.md` ; la règle d'unicité et le contrôle Hotmail préalable restent*), et seulement après avoir vérifié dans la boîte Hotmail qu'il n'a pas déjà répondu.
8. Aux prochains envois : **ajouter le SIREN 985 289 065 dans la signature**, garder la ligne de désinscription, et envoyer par petits lots espacés (pas 16 en 6 minutes).

---

# Complément d'audit du 13/10/2026 (croisement Gmail + Hotmail)

**Fait principal : Hotmail bloque les envois EN SORTIE.** 18 notifications d'échec reçues entre le 12/10 00h09 et le 13/10 07h45 (UTC), dont **17 avec le code 5.7.520 « contenu identifié comme spam »** — c'est Microsoft qui refuse d'acheminer, pas le destinataire — et 1 avec 5.4.310 (domaine hmt.fr inexistant). Conséquences :
- **Arrêt définitif des envois depuis la boîte Hotmail.** La réputation d'envoi est grillée ; continuer expose la boîte personnelle à une suspension, et aucun message ne part réellement.
- Un rejet 5.7.520 **ne signifie pas que l'adresse du prospect est mauvaise** : le prochain contact se fait depuis la boîte Gmail, avec un nouveau texte, par petits lots espacés.
- La campagne réelle est **plus large que les 19 copies du 12/10** : des tentatives rejetées visaient aussi, entre autres, Palatino, Le Monde des Jardins, Carrelage Design 95, Carrelage Roger (adresse nominative broger@), Décomarbre, Midi Carrelage, Le Comptoir des Pierres, MasterPierre, France Pierre, Al Maha Marbles, DPA94, SFZ Global, HMT. Celles qui figurent dans la liste de prospection ont été annotées dans les classeurs ; les autres restent consignées ici en attendant le registre technique.

**Adresses visées par un rejet 5.7.520 (12–13/10)** : lecomptoirdusol.com, natoupierre.fr, sarlpaco@wanadoo.fr, lahalleauxpierres@orange.fr, sfzglobal.com, almahamarbles@gmail.com (×2), lecomptoirdespierres.com, dpa94.com (david@, florian@), masterpierre.com (dirparisouest@), francepierre.fr, decomarbre94.fr, roger-carrelage.com (broger@), midicarrelage.fr, lemondedesjardins.com, palatino.fr, carrelage-design-95.fr. Et 5.4.310 : hmt.fr (domaine inexistant).

**Statut exact des 19 envois du 12/10** : original retrouvé dans Hotmail + copie reçue dans Gmail ; **remise chez le prospect non confirmée** — ne jamais convertir en « livré » ou « lu ». Aucune réponse humaine identifiée au 13/10 ; les 19 copies Gmail portent désormais les libellés PDE/Copie sortante et PDE/Revue manuelle.

**Mailinblack (Le Comptoir des Pierres, 13/10 07h45)** : demande de validation antispam adressée à l'expéditeur — pas une réponse. La valider ferait délivrer le message ; décision du propriétaire, à faire depuis la boîte Hotmail s'il le souhaite.

**Correctif du 13/10 au soir (second passage sur l'export Hotmail)** : les prospects « prioritaires jamais contactés » du matin ne le sont pas tous.
- **Le Monde de la Pierre** (contact@lemondedelapierre.fr) : un envoi est recensé dans l'export Hotmail (ni rejet, ni copie Gmail retrouvés) — fiche passée en **« Contacté »**, remise non confirmée, pas de relance avant le rapprochement.
- **Carrelage Design 95, Palatino, Le Monde des Jardins, Carrelage Roger** : au-delà des rejets 5.7.520 du 12–13/10, l'export recense des **tentatives ultérieures** (issue non confirmée) — fiches passées en **« À rapprocher (export Hotmail) »**, ce qui bloque tout envoi (la règle anti-doublon n'autorise que « À contacter »).
- Le statut définitif de ces 5 fiches sera arrêté au **rapprochement de l'export complet annoncé (~180 messages, 95 destinataires)**, pas avant.

**Second contrôle du 13/10 au soir (journal vérifié, reconstruit indépendamment depuis Gmail)** — croisé ligne à ligne avec la table ci-dessus : **19/19 identiques** (adresses, dossiers 5 INBOX / 14 SPAM, heures — les heures de la table ci-dessus sont en UTC ; le journal vérifié les donne en heure du Caire, UTC+3, à la seconde près). Apports nouveaux :
- Les **Message-ID RFC d'origine des 19 envois** sont désormais consignés dans `registre-envois-2026-10-12.csv` (une ligne par destinataire : c'est la clé `delivery_key` du § 10 du guide Zapier, prête pour le rapprochement des réponses et des échecs).
- Aucune réponse de prospect, **aucune vente ni aucun encaissement** établis par ces messages au 13/10. Deux messages entrants lus sont des offres de prestataires (marketing, Reel à 50 €), pas des acheteurs.
- **Périmètres à ne pas confondre** : les 19 copies auditées dans Gmail et l'export historique annoncé (~180 messages, 95 destinataires) sont deux ensembles différents — ne pas les additionner, et aucun des deux ne vaut remise confirmée.
- **L'absence d'une adresse dans l'export ne prouve pas qu'elle n'a jamais été contactée** (export non exhaustif). Règle pour la prochaine vague : avant chaque envoi, vérifier l'adresse cible dans les éléments envoyés de la boîte Hotmail — y compris pour les six autres « prioritaires » absents du journal.

**Classement et anti-doublons** : la spécification complète (classes SORTANT / COPIE_SORTANTE / ÉCHEC / AUTOMATIQUE / RÉPONSE_COMMERCIALE / OPPOSITION / REVUE_MANUELLE, clés event_key / delivery_key / contact_id / account_id / action_key, réservation atomique) est reprise dans `admin/automatisation-zapier.md`, § 10. Les 19 adresses du 12/10 sont initialisées « déjà contacté, relance automatique bloquée » tant que le raccordement n'est pas validé.
