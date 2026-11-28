# US-01 — Ouvrir un ticket et déterminer sa priorité (story principale)

En tant qu'employé du personnel de l'université, je veux ouvrir un ticket en indiquant l'impact de mon problème
afin que ma demande soit enregistrée tout de suite, avec la bonne priorité et la bonne échéance.

**Exigences liées :** REQ-F-01a, REQ-F-01b, REQ-F-01c, REQ-F-01d, REQ-F-06a, REQ-F-06b, REQ-F-07, REQ-F-08
(données utilisées : REQ-F-11, REQ-F-12)
**Règles métier appliquées :** RM-01, RM-02, RM-03, RM-04, RM-10, RM-11, RM-14, RM-15, RM-16, RM-17, RM-19, RM-20, RM-21
**Sources client :** R1, R2, R4, R5, R8, R9, R10, R13
**Règles traitées ailleurs :** RM-12 et RM-25 (correction par le technicien : US-06), RM-13 (chef : US-11), RM-18 (retard : US-12 et US-08), RM-06 à RM-09 (annulation : US-03).

## Enchaînement des règles (déduit des règles du client, aucune règle ajoutée)

1. **Impact → priorité de base** (RM-11) : tout un service bloqué → urgente ; un seul poste bloqué → normale ; gêne ou demande → basse.
2. **Hausses automatiques** (RM-19, RM-20, RM-21) : +1 niveau si l'employé est de la scolarité ou de la direction ; +1 niveau si un ticket a été résolu moins de 30 jours avant sur le même équipement. **Une seule hausse au total**, jamais au-dessus d'urgente.
3. **Délai** selon la priorité obtenue (RM-14) : urgente 4 h, normale 16 h, basse 40 h ouvrées. (R4 : « le délai de sa priorité ».)
4. **Échéance** (RM-15, RM-16, RM-17) : on compte uniquement les heures ouvrées (lundi–vendredi, 8h00–12h00 et 13h00–17h00) à partir de l'ouverture ; hors de ces heures, le délai commence à la prochaine heure ouvrée.

*Lecture de « moins de 30 jours » : par date calendaire, comme l'exemple de R10 (résolu le 2 mars → hausse jusqu'au 31 mars, plus à partir du 1er avril). Voir HYP-05.*

## Exemples

Situation : les employés « Employé A » (service quelconque), « Employé S » (scolarité) et « Employé D » (direction) existent dans l'annuaire importé. L'équipement INV-0123 a eu un ticket résolu le 2 mars. L'équipement INV-0456 n'a jamais eu de ticket. Les numéros d'inventaire et de ticket sont des valeurs fictives (format non précisé par le client).

### A. Enregistrement et priorité

| # | Demande | Décision | Règle |
|----|---------|----------|-------|
| 1 | Employé A, impact « tout un service bloqué », sans équipement | Acceptée — enregistré immédiatement, avec un numéro ; l'impact choisi est enregistré dans le ticket ; priorité **urgente** | RM-01, RM-02, RM-03 (impact enregistré), RM-11 |
| 2 | Employé A, impact « un seul poste bloqué », équipement INV-0456 | Acceptée — l'impact et le numéro d'inventaire INV-0456 sont enregistrés dans le ticket ; priorité **normale** | RM-03 (impact et équipement enregistrés), RM-11 |
| 3 | Employé A, impact « gêne ou demande », sans équipement | Acceptée — priorité **basse** ; impact enregistré, aucun équipement (*HYP-06 : pas de RM-20 sans équipement — hypothèse*) | RM-03, RM-11 |
| 4 | Employé S, impact « un seul poste bloqué » | Acceptée — normale + 1 = **urgente** | RM-19 |
| 5 | Employé S, impact « gêne ou demande » | Acceptée — basse + 1 = **normale** | RM-19 |
| 6 | Employé D, impact « tout un service bloqué » | Acceptée — urgente reste **urgente** | RM-19, RM-10 |
| 7 | Employé A, « gêne », équipement INV-0123, ouverture le 31 mars | Acceptée — basse + 1 = **normale** (cas donné par R10 : résolu le 2 mars, hausse jusqu'au 31 mars) | RM-20 |
| 8 | Employé A, « gêne », équipement INV-0123, ouverture le 1er avril | Acceptée — pas de hausse, **basse** (cas donné par R10 : plus de hausse à partir du 1er avril) | RM-20 |
| 9 | Employé S, « gêne », équipement INV-0123, ouverture le 31 mars | Acceptée — **normale**, pas urgente : une seule hausse au total | RM-21 |
| 10 | Employé A, « tout un service bloqué », équipement INV-0123, ouverture le 31 mars | Acceptée — reste **urgente** : jamais au-dessus d'urgente | RM-21, RM-10 |
| 11 | Une personne hors personnel (un étudiant) tente d'ouvrir un ticket | Refusée — les étudiants passent par le secrétariat de leur département | RM-04 (R1) |
| 12 | Employé A, aucun impact choisi | **À confirmer** | Question ouverte NQ-01 |
| 13 | Employé A, numéro d'inventaire INV-9999 absent du registre | **À confirmer** | Question ouverte NQ-02 |
| 14 | Un technicien ouvre un ticket pour un employé qui l'a appelé | **À confirmer** | QO-06 |

### B. Échéance (aucun jour férié dans ces exemples, voir QO-13)

| # | Ouverture | Priorité finale | Échéance | Règle |
|----|-----------|-----------------|----------|-------|
| 15 | Lundi 15h00 | urgente (4 h) | **Mardi 10h00** (2 h lundi + 2 h mardi) — exemple du client | RM-14, RM-15, RM-16 |
| 16 | Lundi 13h00 | urgente | **Lundi 17h00**, pas mardi 8h00 — exemple du client | RM-16 |
| 17 | Vendredi 16h00 | urgente | **Lundi 11h00** (1 h vendredi + 3 h lundi) | RM-15, RM-16 |
| 18 | Samedi 10h00 | urgente | **Lundi 12h00** (le délai commence lundi 8h00) | RM-17 |
| 19 | Mardi 12h30 (pause) | urgente | **Mardi 17h00** (le délai commence à 13h00) | RM-17 |
| 20 | Lundi 19h00 (soir) | urgente | **Mardi 12h00** (le délai commence mardi 8h00) | RM-17 |
| 21 | Lundi 8h00 | normale (16 h) | **Mardi 17h00**, pas mercredi 8h00 | RM-14, RM-16 |
| 22 | Mercredi 10h00 | normale | **Vendredi 10h00** (6 h mercredi + 8 h jeudi + 2 h vendredi) | RM-14 |
| 23 | Jeudi 14h00 | basse (40 h) | **Jeudi suivant 14h00** (5 jours ouvrés) | RM-14, RM-15 |
| 24 | Lundi 8h00, Employé S, « gêne » | basse + 1 = normale (16 h) | **Mardi 17h00**, et non vendredi 17h00 (40 h) | RM-19 puis RM-14 |
| 25 | Vendredi 8h00, Employé A, « un seul poste bloqué », équipement INV-0123 (ouverture le 31 mars) | normale + 1 = urgente (4 h) | **Vendredi 12h00** | RM-20 puis RM-14 |

### C. Couverture des règles par les exemples

| Règle | Exemples |
|-------|----------|
| RM-01, RM-02 | 1 (vaut pour tous les cas acceptés) |
| RM-03 | 1 (impact enregistré), 2 (impact et équipement), 3 (impact ; pas d'équipement : « s'il y en a un ») |
| RM-04 | 11 |
| RM-10 | 6, 10 |
| RM-11 | 1, 2, 3 |
| RM-14 | 15, 21, 22, 23, 24, 25 |
| RM-15 | 15, 17, 23 |
| RM-16 | 15, 16, 17, 21 |
| RM-17 | 18, 19, 20 |
| RM-19 | 4, 5, 6, 9, 24 |
| RM-20 | 7, 8, 9, 10, 25 |
| RM-21 | 9, 10 |

## Critères d'acceptation

- [ ] Étant donné que l'Employé A est du personnel de l'université, quand il ouvre un ticket avec l'impact « tout un service bloqué » et sans équipement, alors le ticket est enregistré immédiatement avec un numéro, l'impact choisi, et la priorité urgente. *(exemple 1 ; RM-01, RM-02, RM-03, RM-11)*
- [ ] Étant donné que l'équipement INV-0456 n'a jamais eu de ticket, quand l'Employé A ouvre un ticket « un seul poste bloqué » avec le numéro INV-0456, alors le ticket enregistre ce numéro d'inventaire et sa priorité est normale. *(exemple 2 ; RM-03, RM-11)*
- [ ] Étant donné l'Employé A, quand il ouvre un ticket avec l'impact « gêne ou demande » et sans équipement, alors la priorité est basse. *(exemple 3 ; RM-11)*
- [ ] Étant donné que l'Employé S est de la scolarité, quand il ouvre un ticket « un seul poste bloqué », alors la priorité est urgente. *(exemple 4 ; RM-19)*
- [ ] Étant donné que l'Employé D est de la direction, quand il ouvre un ticket « tout un service bloqué », alors la priorité reste urgente. *(exemple 6 ; RM-19, RM-10)*
- [ ] Étant donné qu'un ticket a été résolu le 2 mars sur INV-0123, quand l'Employé A ouvre le 31 mars un ticket « gêne ou demande » sur INV-0123, alors la priorité est normale ; et s'il l'ouvre le 1er avril, alors la priorité est basse. *(exemples 7 et 8 ; RM-20)*
- [ ] Étant donné qu'un ticket a été résolu le 2 mars sur INV-0123, quand l'Employé S ouvre le 31 mars un ticket « gêne ou demande » sur INV-0123, alors la priorité est normale (une seule hausse) et non urgente. *(exemple 9 ; RM-21)*
- [ ] Étant donné qu'un ticket urgent est ouvert le lundi à 15h00, alors son échéance est le mardi à 10h00 ; et s'il est ouvert le lundi à 13h00, alors son échéance est le lundi à 17h00. *(exemples 15 et 16 ; RM-14 à RM-16)*
- [ ] Étant donné qu'un ticket urgent est ouvert le samedi à 10h00, quand l'échéance est calculée, alors elle est le lundi à 12h00. *(exemple 18 ; RM-17)*
- [ ] Étant donné qu'un ticket urgent est ouvert le mardi à 12h30, quand l'échéance est calculée, alors elle est le mardi à 17h00. *(exemple 19 ; RM-17)*
- [ ] Étant donné qu'un ticket de priorité normale est ouvert le mercredi à 10h00, alors son échéance est le vendredi à 10h00 ; et qu'un ticket de priorité basse est ouvert le jeudi à 14h00, alors son échéance est le jeudi suivant à 14h00. *(exemples 22 et 23 ; RM-14)*
- [ ] Étant donné que l'Employé S ouvre le lundi à 8h00 un ticket « gêne ou demande », quand l'échéance est calculée, alors la priorité utilisée est normale et l'échéance est le mardi à 17h00. *(exemple 24 ; RM-19 puis RM-14)*
- [ ] Étant donné qu'une personne qui n'est pas du personnel (un étudiant) tente d'ouvrir un ticket, alors l'ouverture est refusée. *(exemple 11 ; RM-04 — mécanisme d'identification : voir QO-04)*

## Décisions confirmées utilisées par cette story

Ce sont des décisions du client (réponses R1 à R13), pas des hypothèses : RM-01 à RM-04, RM-10, RM-11, RM-14 à RM-17, RM-19, RM-20 et RM-21. En particulier, R10 confirme qu'un ticket « ne monte jamais de plus d'un niveau au total, ni au-dessus d'urgente » : les exemples 9 et 10 appliquent ce texte aux deux hausses RM-19 et RM-20.

## Hypothèses provisoires (non confirmées par le client)

- **HYP-02, HYP-03** (exigences.md) : la hausse de R9 correspond à « certains services ne peuvent pas attendre » ; le service de l'employé vient de l'annuaire importé.
- **HYP-04** : les hausses RM-19 et RM-20 sont évaluées à l'ouverture du ticket.
- **HYP-05** : « moins de 30 jours » se compte par date calendaire ; les exemples 7 et 8 reprennent seulement les dates de R10, les cas intermédiaires (heure d'ouverture) en dépendent.
- **HYP-06** : un ticket sans équipement n'est pas concerné par RM-20 (exemple 3).
- **HYP-07** : seuls les tickets résolus (pas annulés) déclenchent RM-20.
- **HYP-01** : le numéro de ticket est unique.
- **H-US01-a** : l'instant d'ouverture est l'instant de l'enregistrement (RM-01) ; le calcul d'échéance part de cet instant.
- **H-US01-b** : la limite « un seul niveau au total » ne s'étend pas à la correction du technicien ni à la priorité fixée par le chef (c'est la question QO-11, non tranchée).
- **H-US01-c** : un ticket encore ouvert (non résolu) sur un équipement ne déclenche pas RM-20 (lecture littérale de R10).

## Questions ouvertes

Reprises de `docs/exigences.md` (non résolues) :
- **QO-03** — Accès depuis ordinateur, téléphone, ou les deux ?
- **QO-04** — Comment l'employé s'authentifie-t-il ? Comment le système refuse-t-il une personne hors personnel (exemple 11) ?
- **QO-05** — Rôle exact du secrétariat de département pour les étudiants (ouvre-t-il un ticket à leur place, avec quel statut ?).
- **QO-06** — Un technicien peut-il ouvrir un ticket pour un employé qui appelle (exemple 14) ?
- **QO-07** — Liste des statuts : quel est l'état initial d'un ticket enregistré ?
- **QO-08** — Autres informations d'un ticket (description, lieu, catégorie, pièces jointes) ?
- **QO-11** — La limite d'un niveau au total inclut-elle la correction du technicien et la priorité fixée par le chef ?
- **QO-13** — Jours fériés et fermetures exclus des heures ouvrées ?
- **QO-14** — Les « services qui ne peuvent pas attendre » sont-ils exactement la scolarité et la direction ?
- **QO-18** — Comment et à quelle fréquence l'annuaire et le registre d'inventaire sont-ils importés ?
- **QO-01** — Un courriel de confirmation est-il envoyé à l'ouverture ? (pas décidé, R7 : aucun critère ne l'exige)
- **QO-02** — Cibles de disponibilité et de réactivité : toujours non chiffrées.

Nouvelles questions soulevées par les exemples (absentes de exigences.md) :
- **NQ-01** — L'impact est-il obligatoire ? Que fait le système si l'employé n'en choisit aucun (exemple 12) ? REQ-F-01b dit que le système « demande » de choisir, mais ne dit pas qu'il bloque.
- **NQ-02** — Que fait le système si le numéro d'inventaire saisi n'existe pas dans le registre importé (exemple 13) ?
- **NQ-03** — Format du numéro de ticket (HYP-01 : unicité supposée).
- **NQ-04** — Précision de l'heure d'ouverture et de l'échéance (à la minute ? à la seconde ?) pour les calculs aux limites (par ex. ouverture à 16h59).
