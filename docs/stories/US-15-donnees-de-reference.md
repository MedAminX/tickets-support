# US-15 — Disposer des employés et des équipements importés

En tant qu'employé qui ouvre un ticket, je veux que mon service et les équipements soient déjà connus du système (importés depuis l'annuaire et le registre d'inventaire)
afin de ne pas les ressaisir et que mon ticket soit rattaché au bon service et au bon équipement.

**Acteur de l'import : NON CONFIRMÉ.** R8 dit seulement que les employés, leur service et les équipements « seront importés » ; elle ne dit pas qui réalise l'import. Aucun rôle n'est désigné ici (QO-18). L'employé n'est que le bénéficiaire.

**Exigences liées :** REQ-F-11, REQ-F-12
**Règles métier liées :** RM-03, RM-19, RM-20
**Sources client :** R8

## Critères d'acceptation

- [ ] Étant donné que l'annuaire contient l'Employé S rattaché à la scolarité, quand l'import a eu lieu et que l'Employé S ouvre un ticket, alors le système connaît son service sans que S le saisisse. *(HYP-03 ; utile à RM-19)*
- [ ] Étant donné que le registre d'inventaire contient l'équipement INV-0123, quand l'import a eu lieu et qu'un employé saisit INV-0123 dans un ticket, alors le ticket est rattaché à cet équipement. *(RM-03)*

## Questions ouvertes

- **QO-18** — Qui réalise l'import (aucun rôle confirmé), par quel moyen et à quelle fréquence ? Aucune réponse du client.
- **QO-14 / HYP-03** — Comment reconnaît-on « scolarité » et « direction » dans l'annuaire ?
- **NQ-02** — Que fait le système si un numéro d'inventaire est inconnu ? Si l'employé a quitté l'université ?
- **QO-08** — Données de référence supplémentaires (catégories, lieux) : non décidé.
