# US-09 — Attribuer un ticket à un technicien

En tant que chef de service, je veux attribuer un ticket non pris en charge à un technicien
afin de répartir le travail dans mon équipe.

**Exigences liées :** REQ-F-04a
**Règles métier liées :** RM-05, RM-07, RM-24
**Sources client :** R2, R3, R6, R11

## Critères d'acceptation

- [ ] Étant donné que le ticket n° 110 n'est pris en charge par personne, quand le chef de service l'attribue au Technicien T1, alors le ticket est attribué à T1. *(RM-05, RM-24)*
- [ ] Étant donné que le ticket n° 110 vient d'être attribué à T1, quand l'employé qui l'a ouvert tente de l'annuler, alors l'annulation est refusée. *(RM-07)*
- [ ] Étant donné que le ticket n° 106 est déjà pris en charge par T1, quand le chef tente de l'attribuer à T2 avec la fonction « attribuer », alors cette fonction « attribuer » est refusée. *(Lecture littérale de R6 : « attribuer un ticket non pris en charge » ; le sort d'un ticket déjà pris en charge est en QO-15 et traité par US-10.)*
- [ ] Étant donné un technicien, quand il cherche à attribuer un ticket à un collègue, alors cette action n'existe pas pour lui. *(R6 et R11 : « traiter un ticket » n'inclut pas l'attribution ; la transmission d'un ticket à un collègue reste en QO-15)*

## Questions ouvertes

- **QO-15** — Des spécialités ou la charge de chaque technicien influencent-elles l'attribution ? Le chef voit-il la charge de chaque technicien (le client ne le décrit pas) ?
- **QO-07 / HYP-08** — Un ticket attribué est-il « pris en charge », ou le technicien doit-il encore accepter ?
- **QO-01** — Le technicien est-il prévenu de l'attribution ? (non décidé, R7)
