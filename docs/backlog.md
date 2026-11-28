# Product Backlog

**Projet :** tickets-support — Support informatique : tickets d'incident (Sujet n° 12)
**Phase :** TP2 — partie 4 (priorités et état de préparation)
**Sources :** `docs/responses.md` (R1 à R14), `docs/exigences.md`, `docs/stories/US-01` à `US-16`.

Le tableau est trié par priorité, puis par ordre de numéro. Chaque User Story apparaît une seule fois.

| ID | Titre | Exigences liées | Priorité | Prêt ? |
|----|-------|-----------------|----------|--------|
| US-01 | Ouvrir un ticket et déterminer sa priorité | REQ-F-01a, REQ-F-01b, REQ-F-01c, REQ-F-01d, REQ-F-06a, REQ-F-06b, REQ-F-07, REQ-F-08 | Must | Oui |
| US-02 | Consulter l'état d'avancement de mon ticket | REQ-F-02 | Must | Non |
| US-05 | Prendre en charge un ticket | REQ-F-03a | Must | Non |
| US-08 | Marquer un ticket comme résolu | REQ-F-03d | Must | Oui |
| US-12 | Voir les tickets en retard | REQ-F-06d | Must | Non |
| US-15 | Disposer des employés et des équipements importés | REQ-F-11, REQ-F-12 | Must | Non |
| US-03 | Annuler mon ticket | REQ-F-09 | Should | Oui |
| US-04 | Commenter mon ticket | REQ-F-10 | Should | Non |
| US-06 | Corriger la priorité d'un ticket à la prise en charge | REQ-F-03b, REQ-F-06c | Should | Non |
| US-07 | Commenter un ticket (technicien) | REQ-F-03c | Should | Non |
| US-09 | Attribuer un ticket à un technicien | REQ-F-04a | Should | Oui |
| US-13 | Consulter les statistiques mensuelles par priorité | REQ-F-05a, REQ-F-05b, REQ-F-05c | Should | Non |
| US-10 | Réattribuer un ticket | REQ-F-04b | Could | Non |
| US-11 | Fixer la priorité d'un ticket (chef de service) | REQ-F-04c | Could | Non |
| US-14 | Voir le nombre de tickets résolus par technicien | REQ-F-05d | Could | Non |
| US-16 | Base de connaissances (solutions types) — reportée | Aucune (R14 : hors périmètre v1) | Won't | Non |

## Résumé

| Priorité | Nombre | Stories |
|----------|--------|---------|
| Must | 6 sur 16 (37,5 % : pas plus de la moitié) | US-01, US-02, US-05, US-08, US-12, US-15 |
| Should | 6 | US-03, US-04, US-06, US-07, US-09, US-13 |
| Could | 3 | US-10, US-11, US-14 |
| Won't | 1 | US-16 |
| **Total** | **16** | |

Prêt : **Oui 4** (US-01, US-03, US-08, US-09) · **Non 12**.

## Justification des priorités

**Must — sans elles, la première version n'a pas de sens.**
R8 donne l'essentiel : « ouvrir un ticket avec la bonne priorité et la bonne échéance, et savoir lesquels sont en retard ». Cela donne :
- **US-01** (ouvrir, priorité, échéance) et **US-12** (savoir lesquels sont en retard), directement citées par R8 ;
- **US-15** : les employés avec leur service et les équipements sont importés (R8), et les hausses de priorité de RM-19 et RM-20 en dépendent ;
- **US-05** et **US-08** : prendre en charge et résoudre un ticket, sans quoi aucun ticket n'est traité ni ne peut être en retard ou résolu (R6) ;
- **US-02** : suivre l'avancement de sa demande, le besoin de la demande initiale qui motive la plateforme (« voir où en est leur demande »).

**Should — importantes, mais la première version peut démarrer sans elles.**
- **US-03, US-04** : annulation et commentaire par l'employé (R3, R11) ;
- **US-06** : correction de la priorité par le technicien (R13) ; la priorité découle déjà de l'impact (US-01) ;
- **US-07** : commentaire du technicien (R6) ;
- **US-09** : attribution par le chef. R2 dit qu'un technicien prend en charge « ou » que le chef attribue, donc le travail peut démarrer par prise en charge directe ;
- **US-13** : statistiques mensuelles (R12), utiles au pilotage mais non citées dans « l'essentiel » de R8.

**Could — utiles, non indispensables au démarrage.**
- **US-10** : réattribution (R6), qui suppose l'attribution (US-09) ;
- **US-11** : priorité fixée par le chef, un cas d'exception (R11) ;
- **US-14** : nombre de tickets résolus par technicien (R12), qui dépend de US-08.

**Won't — US-16 (base de connaissances).**
R14, réponse officielle du client : « La base de connaissances (solutions types) : pas dans la première version. » C'est une exclusion explicite de la version 1, reprise dans « Hors périmètre v1 » de `docs/exigences.md`. Conformément au TP2 (partie 4, Q7), la demande reportée reste dans le backlog pour ne pas être oubliée. US-16 est **reportée à une version ultérieure en raison de R14**. Son rôle, son fonctionnement et ses critères restent à définir ; aucun n'est inventé. Won't n'a été donné à aucune autre story : une question ouverte ne suffit pas.

**Dépendances :** US-15 → US-01 ; US-01 → US-05 → US-08 ; US-08 → US-13, US-14 ; US-09 → US-10 ; US-01 → US-12 ; US-05 → US-06. US-16 : aucune dépendance définie (fonctionnalité non décrite).

## Justification de « Prêt ? »

| Story | Prêt ? | Raison |
|-------|--------|--------|
| US-01 | Oui | 13 critères et 25 exemples. Les cas limites 12 à 14 (NQ-01, NQ-02, QO-06) sont marqués « À confirmer » et ne bloquent pas le calcul de la priorité et de l'échéance. Les hypothèses sont explicites. |
| US-02 | Non | QO-07 : la liste des statuts n'est pas définie ; QO-04 : visibilité des tickets. |
| US-03 | Oui | 5 critères tirés de R3. Les cas résolu et annulé (QO-07, QO-22) sont notés ouverts, sans critère. |
| US-04 | Non | Réexamen : l'enregistrement d'un commentaire sur son propre ticket est vérifiable (2 critères, R3, R11, RM-08). Mais le but de la story est de renseigner le technicien, et NQ-05 (qui voit les commentaires) n'est pas tranchée : on ne peut pas définir ni vérifier le comportement attendu côté lecture, ni dire si le bénéfice est atteint. QO-09 (ticket résolu ou annulé) reste aussi ouverte. Jugement limite : elle passerait à Oui si le client confirme au moins que le technicien en charge voit les commentaires. |
| US-05 | Non | QO-07 / HYP-08 et QO-15 : on ne sait pas si un ticket attribué doit encore être pris en charge, ni si un technicien peut prendre un ticket attribué à un autre. |
| US-06 | Non | QO-10, QO-11 et NQ-06 ouvertes : sens de la correction, point de départ, limite RM-21, échéance déjà dépassée. |
| US-07 | Non | Un seul critère ; NQ-05 (qui voit les commentaires) reste ouverte. |
| US-08 | Oui | 3 critères concrets (RM-18). QO-07 (réouverture) et QO-15 (qui peut résoudre) sont ouvertes mais ne bloquent pas le comportement essentiel. |
| US-09 | Oui | 4 critères tirés de R2, R3 et R6. L'annulation refusée après attribution est confirmée (R3, RM-07). Restent ouvertes, sans critère : QO-07 / HYP-08 (un ticket « attribué » est-il « pris en charge » ? conséquence sur les droits de commentaire de RM-08) et QO-15 (limites, reprise en charge). |
| US-10 | Non | QO-15, QO-07 et NQ-07 : tickets réattribuables et effet sur priorité et échéance non décidés. |
| US-11 | Non | QO-12 : on ne sait pas si l'échéance est recalculée quand le chef fixe la priorité ; QO-11. |
| US-12 | Non | Le rôle autorisé à voir les tickets en retard n'est pas confirmé (QO-16) ; le rôle écrit dans la story est provisoire. QO-19 (tickets annulés ou résolus dans la liste) est aussi ouverte. |
| US-13 | Non | QO-17 : mois de rattachement, tickets annulés, taux sans ticket résolu, export ; QO-20 : priorité initiale ou finale ; QO-21 : forme d'affichage du taux. |
| US-14 | Non | QO-17 (période) et QO-15 (ticket réattribué). |
| US-15 | Non | QO-18 : qui réalise l'import, comment et à quelle fréquence ; aucun rôle confirmé. |
| US-16 | Non | Rôle, fonctionnement et critères non définis ; aucun critère d'acceptation ; exclue de la version 1 (R14). |

## Exigences fonctionnelles non couvertes

**Aucune exigence fonctionnelle de `docs/exigences.md` n'est entièrement non couverte** : chaque REQ-F-01a à REQ-F-12 est liée à au moins une story qui décrit la fonctionnalité correspondante.

Couverture **partielle** à noter :
- **REQ-F-11 et REQ-F-12** (import des employés et des équipements) : US-15 décrit le résultat (les données sont connues du système) mais **pas la fonction d'import** elle-même, car R8 n'en dit ni l'acteur ni le mécanisme. Clarification nécessaire (QO-18).

US-16 n'est liée à aucune exigence fonctionnelle : `docs/exigences.md` n'en contient aucune sur la base de connaissances (exclue, R14). Ce n'est pas un manque.

Les exigences non fonctionnelles REQ-NF-01 et REQ-NF-02 ne sont pas listées ici : elles s'appliquent à toutes les stories (valeurs cibles inconnues, QO-02).
