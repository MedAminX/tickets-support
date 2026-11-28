# US-04 — Commenter mon ticket

En tant qu'employé, je veux ajouter un commentaire à l'un de mes tickets
afin de donner une précision au technicien, notamment une fois le ticket pris en charge.

**Exigences liées :** REQ-F-10
**Règles métier liées :** RM-08, RM-22
**Sources client :** R3, R11

## Critères d'acceptation

- [ ] Étant donné que le ticket n° 102 de l'Employé A est pris en charge par un technicien, quand l'Employé A y ajoute un commentaire, alors le commentaire est enregistré sur le ticket. *(RM-08)*
- [ ] Étant donné que le ticket n° 104 appartient à l'Employé B, quand l'Employé A tente d'y ajouter un commentaire, alors l'ajout est refusé. *(RM-22 : « ses tickets »)*

## Questions ouvertes

- **Avant la prise en charge** — R11 dit que l'employé « commente ses tickets » sans condition : on suppose qu'il peut commenter aussi avant la prise en charge, mais R3 n'en parle que pour « ensuite ». *(hypothèse à valider ; aucun critère ne la fige)*
- **QO-09** — L'employé peut-il commenter un ticket résolu ou annulé ?
- **Nouvelle question NQ-05** — Qui voit les commentaires (technicien en charge, chef, tous les techniciens) ? Le client ne le dit pas.
- **QO-08** — Un commentaire peut-il contenir des pièces jointes ?
