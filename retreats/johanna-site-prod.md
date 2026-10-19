# Johanna — site de production (Vercel) : suivi des tests (ouvert le 19/10/2026)

*Statut relayé par la session Minyala le 19/10 au soir, présenté comme vérifié par le propriétaire — à reconfirmer sur pièces. L'application ne vit PAS dans ce dépôt (PR #20 et commit 8be85f7 introuvables ici) ; dépôt et URL de production demandés à la session Minyala.*

## État relayé (19/10, [À CONFIRMER sur la production])

- Production Vercel passée sur `main`, commit `8be85f7`, PR #20, statut READY (remplace la version PR #6).
- Dernier changement décrit : **Johanna vouvoie les visiteurs et ne présume plus leur genre.**
- Domaines `retreats-holidays.com` et `www` : **non vérifiés dans Vercel** (production donc sur une URL *.vercel.app).
- **Non retesté** dans ce contrôle : WhatsApp, frais de 2,99 €, envoi d'e-mails.
- Chantier Resend : **clôturé** (décision du propriétaire).

## Tests demandés par le propriétaire (priorité)

Sur CETTE version de production : les **trois orientations WhatsApp** et le **parcours de mise en relation**.

## Plan de test (selon les moyens de cette session — pas de navigateur)

1. [ ] Obtenir dépôt + URL de production (demandés le 19/10).
2. [ ] Vérification statique de la page de production (fetch) : vouvoiement, aucune présomption de genre, présence des trois orientations WhatsApp (liens `wa.me`, numéros et messages préremplis), mention des frais de 2,99 €, point d'entrée de la mise en relation.
3. [ ] Lecture du code (si dépôt accessible) : logique des trois orientations, du parcours de mise en relation, et conformité aux règles dures (Johanna ne confirme jamais une réservation, n'encaisse jamais, ne donne pas de date ; offres citables : Dahab/Nil/Mamers à 2 899 €, base 10, supplément sur devis ; Gizeh exclue).
4. [ ] Ce qui restera au propriétaire : test interactif réel du chatbot et du WhatsApp depuis son appareil.
5. Contrainte connue à intégrer aux conclusions : **canal Zapier/Gmail bloqué (« Task limits », 19/10)** — tout test d'envoi d'e-mail échouera ou restera silencieux tant que le quota n'est pas rétabli.

## Garde-fous applicables au site

Les règles du dépôt valent pour le chatbot de production comme pour le Zap : aucune confirmation de réservation, aucun encaissement (arbitrage juridique § 4 de `dahab-test.md` pendant — la question du statut des 2,99 € de frais au regard de ce verrou est à poser au juriste via `arbitrage-juridique-brief.md`), aucune date promise, B2C : on répond, on ne démarche pas.
