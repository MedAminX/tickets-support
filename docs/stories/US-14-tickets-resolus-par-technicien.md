# US-14 — Voir le nombre de tickets résolus par technicien

En tant que chef de service, je veux voir le nombre de tickets résolus par chaque technicien
afin de suivre la charge réellement traitée.

**Exigences liées :** REQ-F-05d
**Règles métier liées :** RM-26, RM-27
**Sources client :** R12

## Critères d'acceptation

- [ ] Étant donné que le Technicien T1 a marqué résolus 5 tickets et le Technicien T2 en a marqué 3, quand le chef de service consulte ce suivi, alors il voit 5 pour T1 et 3 pour T2. *(RM-26)*
- [ ] Étant donné un technicien, quand il tente d'accéder à ce suivi, alors l'accès est refusé. *(RM-27)*

## Questions ouvertes

- **QO-17** — Ce nombre est-il aussi ventilé par mois et par priorité ? R12 le donne « par technicien » sans période. Quelle période affiche-t-on ?
- **QO-15** — Un ticket réattribué : est-il compté pour le technicien qui l'a résolu ou celui à qui il était attribué en dernier ?
