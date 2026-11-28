# US-10 — Réattribuer un ticket

En tant que chef de service, je veux réattribuer un ticket à un autre technicien
afin d'équilibrer la charge ou de remplacer un technicien indisponible.

**Exigences liées :** REQ-F-04b
**Règles métier liées :** RM-24
**Sources client :** R6, R11

## Décisions confirmées utilisées

- « Gérer la répartition » comprend : attribuer un ticket non pris en charge, **ou le réattribuer** (R6).
- Le chef de service attribue les tickets (R11, RM-24).

## Critères d'acceptation

- [ ] Étant donné que le ticket n° 106 est attribué au Technicien T1, quand le chef de service le réattribue au Technicien T2, alors le ticket est associé à T2 et plus à T1. *(RM-24)*
- [ ] Étant donné un employé, quand il cherche à réattribuer un ticket, alors cette action n'existe pas pour lui. *(R11 : l'employé ouvre, annule et commente ses tickets ; RM-22)*

## Hypothèses provisoires (non confirmées, sans critère)

- **H-US10-a** — La réattribution laisse la priorité et l'échéance du ticket inchangées. **Ce n'est pas une décision du client.** R11 et RM-25 interdisent seulement de modifier une échéance *à la main* ; R6 et R13 ne disent rien de l'effet d'une réattribution. Voir NQ-07.
- **H-US10-b** — Seul le chef réattribue (R6 confie la répartition au chef) ; la transmission d'un ticket par un technicien à un collègue est la question QO-15.

## Questions ouvertes

- **QO-15** — Le chef peut-il réattribuer un ticket déjà **pris en charge** par un technicien (et pas seulement attribué) ? Un technicien peut-il transmettre un ticket à un collègue ? Peut-on réattribuer un ticket résolu ou annulé ?
- **QO-07 / HYP-08** — Un ticket attribué est-il « pris en charge » ? Le nouveau technicien doit-il reprendre en charge ?
- **NQ-07** (nouvelle) — Quel est l'effet d'une réattribution sur la priorité et l'échéance (H-US10-a) ?
