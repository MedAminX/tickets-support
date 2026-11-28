# US-08 — Marquer un ticket comme résolu

En tant que technicien, je veux marquer un ticket comme résolu
afin d'indiquer à l'employé et au service que le problème est traité.

**Exigences liées :** REQ-F-03d
**Règles métier liées :** RM-18, RM-23 ; (RM-20 : effet sur les tickets futurs du même équipement)
**Sources client :** R4, R6, R10, R11

## Exemples

Situation : le ticket n° 108 est urgent, ouvert le lundi à 13h00 (échéance : lundi 17h00).

| # | Résolution | Décision | Règle |
|----|-----------|----------|-------|
| 1 | Lundi 16h00 | Résolu, pas en retard | RM-18 |
| 2 | Lundi 17h00 (à l'heure exacte) | Résolu, **pas** en retard | RM-18 |
| 3 | Mardi 8h30 | Résolu, **en retard** (échéance dépassée) | RM-18 |

## Critères d'acceptation

- [ ] Étant donné que le ticket n° 108 a pour échéance le lundi à 17h00, quand le technicien le marque résolu le lundi à 17h00, alors le ticket est résolu et n'est pas en retard. *(exemple 2 ; RM-18)*
- [ ] Étant donné que le ticket n° 108 a pour échéance le lundi à 17h00, quand le technicien le marque résolu le mardi à 8h30, alors le ticket est résolu et compte comme résolu après son échéance. *(exemple 3 ; RM-18, RM-26)*
- [ ] Étant donné que le ticket n° 109 sur l'équipement INV-0123 est marqué résolu le 2 mars, alors un ticket ouvert sur INV-0123 le 31 mars reçoit une hausse d'un niveau (voir US-01). *(RM-20)*

## Questions ouvertes

- **QO-07** — Un ticket résolu peut-il être rouvert ou clos par l'employé ? Que se passe-t-il si le problème revient ?
- **QO-15** — Seul le technicien en charge peut-il marquer résolu, ou n'importe quel technicien ? Le chef peut-il le faire ? (R11 ne donne ce droit qu'au technicien.)
- **HYP-07** — Seuls les tickets résolus, pas annulés, déclenchent RM-20.
- **QO-13** — Jours fériés pour juger un retard.
- **QO-01** — L'employé est-il prévenu par courriel de la résolution ? (non décidé, R7)
