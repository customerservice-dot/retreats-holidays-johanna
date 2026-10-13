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
| 10 | MCA Matériaux (Achères) * | contact@mca-materiaux.net | 15:03 | Boîte de réception | 1a130a3e99411876 |
| 11 | Gedimat — Aux Docks de Clamart | expo@docksclamart.fr | 15:03 | **Spam** | 1a130a3f52a3ee9b |
| 12 | Gedimat Sefor Houilles | guillaume.lallet@gedimat.fr | 15:03 | **Spam** | 1a130a40c849eb38 |
| 13 | Batimantes (Colombes) | colombes.expo@batimantes.fr | 15:03 | **Spam** | 1a130a42bbf7cd72 |
| 14 | Kap Carrelage Domont | contact@kap-carrelage.store | 15:04 | **Spam** | 1a130a4f7ddfeddc |
| 15 | Qua Ceramic (Piscop) | qua.ceramic@gmail.com | 15:04 | **Spam** | 1a130a507eb3eec4 |
| 16 | FLIPO (Pantin) | flipo@flipo.fr | 15:04 | **Spam** | 1a130a51de806451 |
| 17 | ISL Carrelage * | isl.carrelage@gmail.com | 17:56 | Boîte de réception | 1a131423fb33a322 |
| 18 | David Paysage * | davidelagagepaysage@gmail.com | 17:57 | **Spam** | 1a13142fb5c3a1c0 |
| 19 | TerraConcept * | terraconceptservicecommercial@gmail.com | 17:57 | **Spam** | 1a1314310a7fe6cf |

\* Absent de la liste de prospection d'origine : ajouté aux classeurs le 13/10 (fiche à compléter).

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
7. **Une seule relance** par prospect (vers le 19/10 pour cette vague), et seulement après avoir vérifié dans la boîte Hotmail qu'il n'a pas déjà répondu.
8. Aux prochains envois : **ajouter le SIREN 985 289 065 dans la signature**, garder la ligne de désinscription, et envoyer par petits lots espacés (pas 16 en 6 minutes).
