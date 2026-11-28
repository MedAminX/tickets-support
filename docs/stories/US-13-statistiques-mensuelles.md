# US-13 — Consulter les statistiques mensuelles par priorité

En tant que chef de service, je veux voir, pour chaque mois et chaque priorité, les tickets ouverts, les tickets résolus et le taux de retard
afin de suivre l'activité du service.

**Exigences liées :** REQ-F-05a, REQ-F-05b, REQ-F-05c
**Règles métier liées :** RM-18, RM-26, RM-27
**Sources client :** R12

## Exemples

Situation : en avril, priorité urgente : 10 tickets ouverts en avril ; 8 tickets résolus en avril, dont 2 résolus après leur échéance et 1 résolu à l'heure exacte de son échéance. *(Le rattachement d'un ticket à un mois — ouverture pour les ouverts, résolution pour les résolus — est une hypothèse : QO-17.)*

| # | Donnée affichée | Valeur | Règle |
|----|----------------|--------|-------|
| 1 | Tickets ouverts (avril, urgente) | 10 | RM-26 |
| 2 | Tickets résolus (avril, urgente) | 8 | RM-26 |
| 3 | Taux de retard (avril, urgente) | 2 ÷ 8 (le ticket résolu à l'heure exacte ne compte pas comme en retard ; forme d'affichage : QO-21) | RM-26, RM-18 |

## Critères d'acceptation

- [ ] Étant donné la situation ci-dessus, quand le chef de service consulte avril pour la priorité urgente, alors il voit 10 tickets ouverts et 8 tickets résolus. *(RM-26)*
- [ ] Étant donné la même situation, alors le taux de retard affiché correspond à 2 ÷ 8 (fraction ou pourcentage : QO-21). *(RM-26, RM-18)*
- [ ] Étant donné un employé ou un technicien, quand il tente d'accéder aux statistiques, alors l'accès est refusé. *(RM-27)*

## Questions ouvertes

- **QO-17** — Statistiques : un ticket compte-t-il dans le mois de son ouverture ou de sa résolution ? *(hypothèse provisoire de l'exemple : ouvert → mois d'ouverture ; résolu → mois de résolution)* Les tickets annulés sont-ils comptés ? Que montre-t-on quand aucun ticket n'est résolu (taux de retard) ? Un export ou un historique est-il nécessaire (question 25) ?
- **QO-20** (nouvelle) — Les priorités comptées dans les statistiques sont-elles la priorité initiale ou la priorité finale (après correction du technicien ou fixation par le chef) ?
- **QO-21** (nouvelle) — Le taux de retard s'affiche-t-il en fraction ou en pourcentage ?
- **QO-13** — Jours fériés pour juger un retard.
