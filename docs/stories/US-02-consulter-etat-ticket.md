# US-02 — Consulter l'état d'avancement de mon ticket

En tant qu'employé, je veux consulter l'état d'avancement de mes tickets
afin de savoir où en est ma demande sans contacter le service informatique.

**Exigences liées :** REQ-F-02
**Règles métier liées :** aucune règle métier confirmée ne décrit la consultation (RM-22 ne parle que d'ouvrir, annuler et commenter)
**Sources client :** demande initiale (« voir où en est leur demande ») ; R3 (prise en charge, annulation) et R6 pour les changements d'état

## Critères d'acceptation

- [ ] Étant donné que l'Employé A a ouvert le ticket n° 101, quand il consulte ses tickets, alors il voit le ticket n° 101 avec son état d'avancement actuel.
- [ ] Étant donné que le ticket n° 101 de l'Employé A est ensuite pris en charge par un technicien, quand l'Employé A le consulte à nouveau, alors l'état affiché reflète cette prise en charge.
- [ ] Étant donné que le technicien marque le ticket n° 101 comme résolu, quand l'Employé A le consulte, alors l'état affiché indique qu'il est résolu.

## Questions ouvertes

- **QO-07** — La liste exacte des statuts n'est pas définie : on ne peut pas dire quels libellés l'employé voit (ni si « attribué » et « pris en charge » sont deux états distincts, HYP-08).
- **QO-04** — Un employé ne voit-il que ses propres tickets ? *(hypothèse provisoire : oui ; non décidé par le client)*
- **QO-22** — Un ticket annulé reste-t-il visible pour l'employé ? (RM-09 : jamais supprimé, mais la visibilité n'est pas précisée.)
- **QO-08** — Quelles informations accompagnent un ticket à l'écran (commentaires, technicien, échéance) ? L'employé voit-il l'échéance ?
- **QO-01** — Pas de notification par courriel à chaque changement : non décidé (R7).
