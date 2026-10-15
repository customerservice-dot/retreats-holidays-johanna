# Directives de prospection — à transmettre à ChatGPT (15/10/2026)

**Priorité n° 1 : le temps.** Chaque jour sans envoi est un jour de stock immobile. Les contrôles ci-dessous sont des vérifications de 2 minutes par lot, pas des chantiers — on vérifie, on envoie, on journalise, le jour même.

## Calendrier (démarrage immédiat)

| Jour | Action |
|---|---|
| **J0 — mer. 15/10** | Lot 1 : **premier contact des 10 prioritaires à e-mail vérifié** (liste ci-dessous), message A. Avant le lot : contrôle 2 min (voir « Avant chaque envoi »). En parallèle : finir le rapprochement de l'export Hotmail (tu l'as en main). |
| **J1 — jeu. 16/10** | Lot 2 : **relance unique des 10 premiers des 19 contactés le 12/10** (registre `registre-envois-2026-10-12.csv`), message B — après contrôle des réponses dans Hotmail. |
| **J2 — ven. 17/10** | Lot 3 : relance unique des 9 restants, message B. Statuer sur les 4 fiches « À rapprocher » et Le Monde de la Pierre avec l'export rapproché. |
| **J3–J5** | Trouver les e-mails des 12 prioritaires sans adresse (sites officiels uniquement), puis lots suivants de 10/jour, message A. |
| **En continu** | Toute réponse entrante : traitée sous 24 h (modèles dans `messages-courts.md`). « Non »/« STOP » → statut « Ne plus contacter », immédiat et définitif. |

## Règles non négociables

1. **Expéditeur : la boîte Gmail uniquement** (customerservice@, qui reçoit info@pierredegypte.online). **Plus jamais Hotmail** (rejets 5.7.520, réputation grillée).
2. **Maximum 10 envois par jour**, espacés dans la journée — pas de rafale.
3. **Objet unique par destinataire : « MINYALA — [Nom de l'entreprise] »**. Jamais de réponse dans les deux fils mélangés du 12/10.
4. **Jamais le tarif professionnel par écrit.** Il ne se donne que sur devis, après SIRET. C'est aussi ce qui rend le message court : la curiosité fait répondre.
5. Professionnels uniquement (le démarchage de particuliers est interdit) ; signature avec **SIREN 985 289 065** et ligne **STOP** à chaque envoi.
6. Interdits absolus dans les messages : « marbre », « liquidation », « soldes », « antidérapant », « résiste au gel », « spécial piscine », promesse ferme de livraison, offre de pose, lien de paiement. L'accroche pyramides uniquement sous la forme : « le même matériau que celui des pyramides ».
7. L'IA ne choisit jamais To/Cc/Bcc : un destinataire vérifié par message, pas de copie.

## Avant chaque envoi (contrôle de 2 minutes par lot)

Pour chaque adresse : **(a)** statut « À contacter » dans le classeur (tout autre statut bloque) ; **(b)** absente de `registre-envois-2026-10-12.csv` (sauf relance J1–J2, qui est l'unique relance autorisée) ; **(c)** si elle figure dans `registre-rejets-2026-10-12.csv` (rejets 5.7.520 : le message n'est jamais parti), confirmer dans l'export qu'aucun envoi abouti n'existe, puis traiter comme premier contact.

## Lot 1 (J0) — les 10 prioritaires à e-mail vérifié

| Entreprise | Ville | E-mail |
|---|---|---|
| Le Comptoir du Sol | Neuville-lès-Dieppe (76) | contact@lecomptoirdusol.com |
| Midi Carrelage | Sotteville-lès-Rouen (76) | contact.midicarrelage@midicarrelage.fr |
| Pillaud Matériaux (Caen) | Cormelles-le-Royal (14) | caen@pillaud.fr |
| Torchio | Ifs (14) | info@torchio.fr |
| Belles Piscines | Coignières (78) | accueil@belles-piscines.com |
| Décomarbre | Bry-sur-Marne (94) | decomarbre@decomarbre94.fr |
| La Halle aux Pierres | Gometz-le-Châtel (91) | lahalleauxpierres@orange.fr |
| Natou Pierre | Paris 17e | contact@natoupierre.fr |
| Paco | Courcouronnes (91) | sarlpaco@wanadoo.fr |
| Pierlux | Auvers-Saint-Georges (91) | pierluxfrance@orange.fr |

*(La plupart ont subi un rejet 5.7.520 côté Hotmail : rien ne leur est jamais parvenu — premier contact normal, depuis Gmail.)*

## Message A — premier contact (objet : « MINYALA — [Entreprise] »)

> Bonjour,
>
> Question rapide : reprenez-vous des lots de pierre naturelle ?
>
> Nous déstockons à Gennevilliers des dalles 30×60 en calcaire d'Égypte — le même matériau que celui des pyramides. Fin de stock : premier arrivé, premier servi.
>
> Je vous envoie le détail (formats, volumes, conditions professionnelles) ?
>
> Joseph Hanna
> Pierre d'Égypte — Pierre et retraites, SIREN 985 289 065
> Pas intéressé ? Répondez STOP et je ne vous recontacterai pas.

*Mécanique : question d'ouverture (micro-engagement), une seule accroche concrète (pyramides), rareté factuelle (fin de stock), et la « carotte » : le détail ne s'obtient qu'en répondant — aucun prix écrit.*

## Message B — relance unique des 19 du 12/10 (objet : « MINYALA — [Entreprise] »)

> Bonjour,
>
> Je reviens vers vous une seule fois : le lot de calcaire égyptien MINYALA (dalles 30×60, stock visible à Gennevilliers) est toujours disponible — premier arrivé, premier servi.
>
> Voulez-vous les conditions professionnelles par devis, ou un créneau cette semaine pour voir les dalles ?
>
> Sans réponse de votre part, je ne vous recontacterai pas.
>
> Joseph Hanna
> Pierre d'Égypte — Pierre et retraites, SIREN 985 289 065
> Pas intéressé ? Répondez STOP.

*Mécanique : relance « à prendre ou à laisser » (takeaway close, honnête : c'est bien la seule relance), choix binaire devis/visite au lieu d'un oui/non, et date butoir implicite (« cette semaine »).*

## Compte rendu attendu (après chaque lot, le jour même)

Une ligne par envoi : **date/heure · entreprise · adresse · objet exact · ID Gmail du message envoyé**. Ces lignes alimentent le registre anti-doublon — sans elles, la vague suivante est bloquée. Signaler immédiatement : toute réponse, tout échec de remise (mailer-daemon), tout STOP.
