# US-06 — Corriger la priorité d'un ticket à la prise en charge

En tant que technicien, je veux corriger d'un niveau au plus la priorité d'un ticket que je prends en charge
afin qu'elle reflète la gravité réelle du problème.

**Exigences liées :** REQ-F-03b, REQ-F-06c
**Règles métier liées :** RM-10, RM-12, RM-14 à RM-17, RM-23, RM-25 (RM-21 : voir QO-11)
**Sources client :** R6, R11, R13

## Décisions confirmées utilisées

- Le technicien corrige une priorité **d'un niveau au plus** (R11, RM-12, RM-23).
- La correction se fait **à la prise en charge** (R13, RM-12).
- L'échéance est alors **recalculée depuis l'ouverture** du ticket (R13, RM-12).
- **Personne ne modifie une échéance à la main** (R11, RM-25).

## Exemples

Situations : le ticket n° 107 est de priorité **normale**, ouvert le lundi à 8h00 (échéance : mardi 17h00) ; le ticket n° 113 est de priorité **basse**, sans hausse automatique, ouvert le lundi à 8h00 ; le ticket n° 114 est de priorité basse à l'ouverture, monté à normale par RM-19 (employé de la scolarité).

| # | Ticket et demande du technicien | Décision | Règle |
|----|---------------------------------|----------|-------|
| 1 | n° 107 : normale → urgente, prise en charge le lundi à 9h00 | Acceptée ; échéance recalculée depuis l'ouverture : **lundi 12h00** | RM-12, RM-14 |
| 2 | n° 113 : basse → normale (+1) | Acceptée ; échéance recalculée depuis l'ouverture | RM-12 |
| 3 | n° 113 : basse → urgente (+2) | Refusée : un niveau au plus | RM-12 |
| 4 | n° 107 : modifier directement l'échéance à la main | Refusée | RM-25 |
| 5 | n° 107 : normale → basse (−1) | **À confirmer** | QO-10 |
| 6 | n° 107 : seconde correction après une première | **À confirmer** | QO-10 |
| 7 | n° 114 : correction d'un niveau — à partir de basse (priorité initiale) ou de normale (après RM-19) ? | **À confirmer** | QO-10 |
| 8 | n° 114 : normale → urgente par le technicien, alors que RM-19 l'a déjà monté d'un niveau | **À confirmer** : la limite d'un niveau au total (RM-21) inclut-elle la correction ? | QO-11 |
| 9 | n° 107 : correction à urgente à la prise en charge le lundi à 14h00, alors que la nouvelle échéance (lundi 12h00) est déjà dépassée | **À confirmer** : que devient le ticket ? | NQ-06 |

## Critères d'acceptation

*Seuls les exemples tranchés par le client donnent lieu à un critère. Les exemples 5 à 9 n'en ont pas, tant que leur question reste ouverte.*

- [ ] Étant donné que le ticket n° 107 est de priorité normale et ouvert le lundi à 8h00, quand le Technicien T1 le prend en charge le lundi à 9h00 et passe sa priorité à urgente, alors l'échéance est recalculée depuis l'ouverture et devient le lundi à 12h00. *(exemple 1 ; RM-12)*
- [ ] Étant donné que le ticket n° 113 est de priorité basse, quand le technicien passe sa priorité à normale, alors la correction est acceptée et l'échéance est recalculée depuis l'ouverture. *(exemple 2 ; RM-12)*
- [ ] Étant donné que le ticket n° 113 est de priorité basse, quand le technicien tente de passer sa priorité à urgente, alors la correction est refusée. *(exemple 3 ; RM-12)*
- [ ] Étant donné un ticket, quand un technicien consulte les actions possibles, alors aucune ne permet de modifier l'échéance directement. *(exemple 4 ; RM-25)*

## Hypothèse provisoire (non confirmée)

- **H-US06** — Si l'échéance recalculée est déjà dépassée au moment de la correction (exemple 9), on pourrait en conclure que le ticket est aussitôt « en retard » (lecture littérale de R13 et RM-18). **Ce n'est pas une décision du client** ; aucun critère ne s'appuie dessus.

## Questions ouvertes (toutes restent ouvertes)

- **QO-10** — Le technicien peut-il corriger à la baisse comme à la hausse (exemple 5) ? Peut-il corriger une seconde fois (exemple 6) ? La correction part-elle de la priorité initiale ou de celle obtenue après les hausses automatiques (exemple 7) ? Aucune réponse du client.
- **QO-11** — La limite d'un niveau au total (RM-21) inclut-elle la correction du technicien (exemple 8) ? Aucune réponse du client.
- **NQ-06** — Si l'échéance recalculée est déjà dépassée (exemple 9), le ticket est-il aussitôt en retard ? (H-US06 n'est qu'une lecture littérale.)
- **Moment de la correction** — R13 la situe « à la prise en charge », R11 la donne comme un droit du technicien : la limite temporelle précise est liée à QO-10.
- **QO-13** — Jours fériés pour le recalcul de l'échéance.
