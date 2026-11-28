# US-11 — Fixer la priorité d'un ticket (chef de service)

En tant que chef de service, je veux fixer n'importe quelle priorité pour un ticket
afin de corriger une priorité que je juge inadaptée.

**Exigences liées :** REQ-F-04c
**Règles métier liées :** RM-10, RM-13, RM-24, RM-25
**Sources client :** R11, R13

## Critères d'acceptation

- [ ] Étant donné que le ticket n° 111 est basse, quand le chef de service fixe sa priorité à urgente, alors la priorité du ticket est urgente (écart de deux niveaux accepté). *(RM-13)*
- [ ] Étant donné que le ticket n° 112 est urgente, quand le chef de service fixe sa priorité à basse, alors la priorité du ticket est basse. *(RM-13)*
- [ ] Étant donné un ticket, quand le chef de service consulte les actions possibles, alors aucune ne permet de modifier l'échéance directement. *(RM-25)*

## Questions ouvertes

- **QO-12** — L'échéance est-elle recalculée quand le chef fixe une priorité ? R13 ne le dit que pour la correction du technicien. *(Aucun critère ne fige ce point.)*
- **QO-11** — Comment la limite « un niveau au total » (RM-21) s'applique-t-elle à la priorité fixée par le chef ?
- **QO-10** — Le chef peut-il fixer la priorité d'un ticket résolu ou annulé ? À tout moment ?
