# Finalisation expéditeur info@pierredegypte.online — état au 26/10/2026

## Diagnostic (vérifié en direct le 26/10)

- DNS du domaine hébergé chez **Network Solutions** (ns45/ns46.worldnic.com) ✓
- **La boîte info@ existe réellement** : MX = messagerie Network Solutions
  (mx001–004.netsol.xion.oxcs.net), SPF racine en place
  (`include:spf.registeredsite.com include:spf.cloudus.oxcs.net`) ✓
- **Resend : domaine pierredegypte.online en statut FAILED** depuis sa création
  le 29/09 — les 3 enregistrements demandés n'ont jamais été posés. C'est le
  « DNS à corriger ».
- Aucun DMARC publié (recommandé pour la délivrabilité).

## Les 3 enregistrements à ajouter chez Network Solutions (copier-coller)

Gestion : networksolutions.com → Account Manager → My Domain Names →
pierredegypte.online → Manage → **Advanced DNS** (Edit DNS Records).

| Type | Host (Name) | Valeur | TTL |
|---|---|---|---|
| TXT | `resend._domainkey` | `p=MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQC2iXgI/sQSG2Jw7+/TKBvHWsJ98h6RwMg19GI/ub6JPuSuqq8IfewQycRkJVOyTyH6+7Uq6tzwMNaz6yeu8l22XmIO0uDwWerXk9ToOTcYDThq4UrrjMwvPPiqlHphG9jFvscK2mIbf+GS7OlctVhNUzEUrMYh1PKrghIIAL013wIDAQAB` | Auto/défaut |
| CNAME | `send` | `send.forge.rmta.net` | Auto/défaut |
| CNAME | `rsend` | `rsend-euw1.forge.rmta.net` | Auto/défaut |

Recommandé en plus (délivrabilité, sans impact sur la boîte existante) :

| Type | Host | Valeur |
|---|---|---|
| TXT | `_dmarc` | `v=DMARC1; p=none;` |

**Sans risque** : ces enregistrements ne touchent que des sous-domaines
(`send.`, `rsend.`, `resend._domainkey.`) — ils ne modifient ni le site, ni le
MX, ni le SPF racine. La boîte Network Solutions continue de recevoir
normalement. (Rien à voir avec les TXT Vercel de retreats-holidays.com, qui
restent interdits.)

## Ce qui se passe ensuite (automatisé côté Claude)

1. Dès que les enregistrements sont en ligne → relance de la vérification
   Resend (`verify-domain`).
2. Puis **e-mail de test** : From `info@pierredegypte.online` →
   customerservice@exclusiveyogaretreats.com ; contrôle dans Gmail du From
   affiché + SPF/DKIM = pass.
3. Seulement après ce test réussi : le verrou d'envoi peut être levé par le
   propriétaire (les 5 brouillons « Revendeurs à 35 € » attendent validation).

## Point important — les RÉPONSES

Les réponses des prospects iront à la boîte **info@pierredegypte.online chez
Network Solutions** (webmail OX), pas dans Gmail. Deux options :
- consulter le webmail Network Solutions régulièrement, ou
- configurer dans ce webmail une redirection vers
  customerservice@exclusiveyogaretreats.com (le suivi Gmail redevient complet).

## Alternative immédiate (sans DNS)

La boîte info@ existe déjà : un envoi **manuel depuis le webmail Network
Solutions** satisfait la règle « From réel » dès aujourd'hui, pour les 5
messages du Top 5 (copier-coller des brouillons). Le circuit Resend reste le
bon pour l'échelle (vagues de 15–45).
