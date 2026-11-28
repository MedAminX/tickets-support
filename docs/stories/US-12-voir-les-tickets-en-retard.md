# US-12 — Voir les tickets en retard

En tant que chef de service, je veux savoir quels tickets sont en retard
afin de réagir en priorité sur ceux dont l'échéance est dépassée.

**Exigences liées :** REQ-F-06d
**Règles métier liées :** RM-16, RM-17, RM-18
**Sources client :** R4, R8
**Rôle : PROVISOIRE, non confirmé par le client (QO-16).**
*(R8 dit que l'essentiel est de « savoir lesquels sont en retard » sans dire qui. Le client écrivant en tant que chef du service, nous retenons le chef de service ; voir QO-16.)*

## Exemples

Situation : le ticket n° 108 est urgent, ouvert le lundi à 13h00 (échéance : lundi 17h00) ; non résolu.

| # | Instant de consultation | Le ticket n° 108 est… | Règle |
|----|------------------------|-----------------------|-------|
| 1 | Lundi 16h00 | pas en retard | RM-18 |
| 2 | Lundi 17h00 pile | pas en retard (l'échéance n'est pas dépassée) | RM-18 |
| 3 | Lundi 17h30 | en retard (non résolu après l'échéance) | RM-18 |
| 4 | Mardi 8h30, ticket résolu à 8h00 | **À confirmer** : il était en retard tant qu'il était non résolu ; reste-t-il affiché ? | QO-19 |

## Critères d'acceptation

- [ ] Étant donné que le ticket n° 108 est non résolu et a pour échéance le lundi à 17h00, quand le chef consulte les tickets en retard le lundi à 17h30, alors le ticket n° 108 y figure. *(RM-18)*
- [ ] Étant donné le même ticket, quand le chef consulte à 17h00 pile, alors il n'y figure pas. *(RM-18)*
- [ ] Étant donné que le ticket n° 108 est résolu le lundi à 16h00, quand le chef consulte les tickets en retard le lundi à 17h30, alors il n'y figure pas. *(RM-18)*

## Questions ouvertes

- **QO-16** — Qui voit les tickets en retard : seulement le chef, ou aussi les techniciens et les employés ?
- **QO-13** — Jours fériés : une échéance un jour férié ?
- **QO-19** (nouvelle) — La liste des tickets en retard inclut-elle les tickets annulés ? Un ticket résolu en retard y reste-t-il affiché après sa résolution ? (Aucune décision du client. Cette question ne concerne pas les statistiques, donc pas QO-17.)
- Alertes avant l'échéance : le client n'en parle pas, aucune exigence ne les prévoit ; elles ne font pas partie de cette story.
