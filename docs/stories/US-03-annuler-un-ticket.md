# US-03 — Annuler mon ticket

En tant qu'employé, je veux annuler un ticket que j'ai ouvert tant qu'il n'est pas pris en charge
afin de retirer une demande devenue inutile.

**Exigences liées :** REQ-F-09
**Règles métier liées :** RM-06, RM-07, RM-08, RM-09, RM-22
**Sources client :** R3, R11

## Critères d'acceptation

- [ ] Étant donné que le ticket n° 101 de l'Employé A n'est ni pris en charge ni attribué, quand l'Employé A l'annule, alors le ticket est annulé. *(RM-06)*
- [ ] Étant donné que le ticket n° 101 a été annulé, alors il n'est pas supprimé : il reste conservé dans le système. *(RM-09)*
- [ ] Étant donné que le ticket n° 102 de l'Employé A est pris en charge par un technicien, quand l'Employé A tente de l'annuler, alors l'annulation est refusée ; il peut seulement ajouter un commentaire (voir US-04). *(RM-06, RM-08)*
- [ ] Étant donné que le chef de service a attribué le ticket n° 103 de l'Employé A à un technicien, quand l'Employé A tente de l'annuler, alors l'annulation est refusée. *(RM-07)*
- [ ] Étant donné que le ticket n° 104 appartient à l'Employé B, quand l'Employé A tente de l'annuler, alors l'annulation est refusée. *(RM-22 : « ses tickets »)*

## Questions ouvertes

- **QO-07 / HYP-08** — « Pris en charge » désigne-t-il la prise en charge par un technicien, distincte de l'attribution par le chef ? (RM-07 bloque déjà l'annulation après attribution.)
- **QO-07** — Un ticket résolu peut-il être annulé ? Le client ne le dit pas : aucun critère ne le prévoit.
- **QO-22** — Que voit l'employé d'un ticket annulé ? (RM-09 impose la conservation, pas la visibilité.)
- **QO-17** — Les tickets annulés sont-ils comptés dans les statistiques ?
