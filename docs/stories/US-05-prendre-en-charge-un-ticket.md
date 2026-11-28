# US-05 — Prendre en charge un ticket

En tant que technicien, je veux prendre en charge un ticket non pris en charge
afin de commencer à le traiter.

**Exigences liées :** REQ-F-03a
**Règles métier liées :** RM-05, RM-06, RM-23
**Sources client :** R2, R6, R11

## Critères d'acceptation

- [ ] Étant donné que le ticket n° 105 n'est pris en charge par personne, quand le Technicien T1 le prend en charge, alors le ticket est pris en charge par T1. *(RM-05)*
- [ ] Étant donné que le ticket n° 105 vient d'être pris en charge par T1, quand l'employé qui l'a ouvert tente de l'annuler, alors l'annulation est refusée. *(RM-06)*

## Hypothèse provisoire (non confirmée, sans critère)

- **H-US05** — Un ticket déjà pris en charge par un technicien ne peut pas être pris en charge par un autre. Rien dans R2, R6 ou R11 ne le dit : voir QO-15.

## Questions ouvertes

- **QO-15** — Un technicien peut-il prendre en charge un ticket déjà attribué à un autre technicien par le chef ? Et un ticket déjà pris en charge par un collègue (H-US05) ?
- **QO-07 / HYP-08** — Un ticket attribué par le chef est-il déjà « pris en charge », ou le technicien doit-il encore le prendre en charge ?
- **QO-15** — Des spécialités influencent-elles qui peut prendre quoi ? Y a-t-il une limite de tickets par technicien ?
- **QO-01** — L'employé est-il prévenu par courriel de la prise en charge ? (non décidé, R7)
