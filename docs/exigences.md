# Exigences — Version 2

**Projet :** tickets-support — Support informatique : tickets d'incident (Sujet n° 12)
**Client :** Le service informatique d'une université (5 techniciens, un chef de service, environ 900 employés)
**Équipe :** Ghrairi Med Amin, Noumi Raed, Aidi Yassmine, Guesmi Farah
**Phase :** TP2 — Des exigences au Product Backlog (partie 1 : mise à jour des exigences)

---

## 1. Contexte et objectif du document

Le service informatique de l'université reçoit trop de demandes par téléphone et par courriel, et en perd une partie. Il souhaite une plateforme de tickets d'incident : les employés signalent un problème et suivent sa résolution, les techniciens traitent les tickets, et le chef de service répartit le travail et suit l'activité.

Ce document est la **version 2** des exigences. Il met à jour les exigences initiales du TP1 (`tp/TP1.md`) à partir des réponses du client (`docs/responses.md`), reçues après l'envoi de nos 28 questions (`docs/questions-client.md`).

**Sources, par ordre de priorité :**

1. la demande initiale du client (sujet 12) ;
2. les réponses du client, numérotées **R1 à R14** dans ce document, dans l'ordre de leur courriel ;
3. les exigences initiales et leur traçabilité (TP1) ;
4. les consignes du TP2.

**Principes de rédaction :**

- Chaque ligne porte une marque : *(inchangée)*, *(modifiée — R…)* ou *(nouvelle — R…)*.
- Une décision n'est écrite comme règle ou exigence que si le client l'a prise. Le reste figure en section 6 (informations inconnues ou hypothèses).
- Les valeurs chiffrées du client (délais, horaires, seuil de 30 jours) sont devenues des règles métier `RM-xx`.

### Vocabulaire : ne pas confondre

| Terme | Sens dans ce document | Source |
| --- | --- | --- |
| **Impact** | Choix de l'employé à l'ouverture : tout un service bloqué, un seul poste bloqué, ou gêne / demande. | R13 |
| **Priorité** | Niveau du ticket : urgente, normale ou basse. Elle découle de l'impact, puis peut être relevée ou corrigée. Elle détermine le délai. | R5, R13 |
| **Échéance** | Instant où le délai de la priorité est épuisé, en heures ouvrées depuis l'ouverture. | R4 |
| **Retard** | État d'un ticket non résolu dont l'échéance est dépassée. | R4 |
| **Taux de retard** | Statistique : tickets résolus après leur échéance ÷ tickets résolus. | R12 |

---

## 2. Exigences fonctionnelles — version 2

### 2.1 Ouverture d'un ticket (employé)

- **REQ-F-01a** — Le système doit permettre à un employé du personnel de l'université d'ouvrir un ticket. *(modifiée — R1, remplace REQ-F-01)*
- **REQ-F-01b** — Le système doit demander à l'employé de choisir, à l'ouverture, l'impact du problème parmi : tout un service bloqué, un seul poste bloqué, gêne ou demande. *(nouvelle — R2, R13)*
- **REQ-F-01c** — Le système doit permettre à l'employé d'indiquer, à l'ouverture, l'équipement concerné par son numéro d'inventaire, lorsqu'il y en a un. *(nouvelle — R2)*
- **REQ-F-01d** — Le système doit enregistrer le ticket dès son ouverture et lui attribuer un numéro (voir RM-01 à RM-03). *(nouvelle — R2)*

### 2.2 Suivi et annulation (employé)

- **REQ-F-02** — Le système doit permettre à un employé de consulter l'état d'avancement de sa demande. *(inchangée)*
- **REQ-F-09** — Le système doit permettre à un employé d'annuler son ticket dans les conditions de RM-06 et RM-07. *(nouvelle — R3)*
- **REQ-F-10** — Le système doit permettre à un employé d'ajouter un commentaire à l'un de ses tickets. *(nouvelle — R3, R11)*

### 2.3 Traitement des tickets (technicien)

*REQ-F-03 (« traiter les tickets ») est décomposée selon la définition du client en R6.*

- **REQ-F-03a** — Le système doit permettre à un technicien de prendre en charge un ticket non pris en charge. *(modifiée — R2, R6, remplace REQ-F-03)*
- **REQ-F-03b** — Le système doit permettre à un technicien de corriger la priorité d'un ticket d'un niveau au plus (voir RM-12). *(modifiée — R6, R11, R13)*
- **REQ-F-03c** — Le système doit permettre à un technicien d'ajouter un commentaire à un ticket. *(modifiée — R6)*
- **REQ-F-03d** — Le système doit permettre à un technicien de marquer un ticket comme résolu. *(modifiée — R6)*

### 2.4 Répartition du travail (chef de service)

*REQ-F-04 (« gérer la répartition du travail ») est précisée par R2 et R6.*

- **REQ-F-04a** — Le système doit permettre au chef de service d'attribuer un ticket non pris en charge à un technicien. *(modifiée — R2, R6, remplace REQ-F-04)*
- **REQ-F-04b** — Le système doit permettre au chef de service de réattribuer un ticket. *(modifiée — R6)*
- **REQ-F-04c** — Le système doit permettre au chef de service de fixer, pour un ticket, n'importe quelle priorité. *(nouvelle — R11)*

### 2.5 Suivi de l'activité (chef de service uniquement)

*REQ-F-05 (« suivre l'activité ») est précisée par R12. Ces statistiques ne sont consultables que par le chef de service (RM-27).*

- **REQ-F-05a** — Le système doit permettre au chef de service de consulter, pour chaque mois et chaque priorité, le nombre de tickets ouverts. *(modifiée — R12, remplace REQ-F-05)*
- **REQ-F-05b** — Le système doit permettre au chef de service de consulter, pour chaque mois et chaque priorité, le nombre de tickets résolus. *(modifiée — R12)*
- **REQ-F-05c** — Le système doit permettre au chef de service de consulter, pour chaque mois et chaque priorité, le taux de retard (tickets résolus après leur échéance ÷ tickets résolus). *(modifiée — R12)*
- **REQ-F-05d** — Le système doit permettre au chef de service de consulter le nombre de tickets résolus par technicien. *(modifiée — R12)*

### 2.6 Priorité, échéance et retard

- **REQ-F-06a** — Le système doit déterminer la priorité initiale d'un ticket à partir de l'impact choisi par l'employé (RM-11). *(modifiée — R13, remplace REQ-F-06)*
- **REQ-F-06b** — Le système doit calculer l'échéance d'un ticket à son ouverture, selon la priorité, les délais et les heures ouvrées (RM-14 à RM-17). *(nouvelle — R4, R5)*
- **REQ-F-06c** — Le système doit recalculer l'échéance, depuis l'ouverture du ticket, lorsque le technicien corrige la priorité à la prise en charge. *(nouvelle — R13)*
- **REQ-F-06d** — Le système doit permettre de savoir quels tickets sont en retard (RM-18). *(nouvelle — R4, R8)*
- **REQ-F-07** — Le système doit relever d'un niveau la priorité d'un ticket portant sur un équipement dont un ticket a été résolu moins de 30 jours avant (RM-20). *(modifiée — R10)*
- **REQ-F-08** — Le système doit relever d'un niveau la priorité d'un ticket ouvert par un employé de la scolarité ou de la direction (RM-19). *(modifiée — R9 ; le lien avec « certains services ne peuvent pas attendre » est une hypothèse, voir HYP-02)*

### 2.7 Données de référence

- **REQ-F-11** — Le système doit disposer des employés et de leur service, importés depuis l'annuaire de l'université. *(nouvelle — R8)*
- **REQ-F-12** — Le système doit disposer des équipements, importés depuis le registre d'inventaire. *(nouvelle — R8)*

---

## 3. Règles métier

### 3.1 Enregistrement et cycle de vie du ticket

- **RM-01** — Un ticket est enregistré tout de suite, à son ouverture. *(nouvelle — R2)*
- **RM-02** — Chaque ticket enregistré reçoit un numéro. *(nouvelle — R2)*
- **RM-03** — Un ticket enregistre son numéro, l'impact choisi par l'employé et, s'il y en a un, l'équipement concerné (numéro d'inventaire). *(nouvelle — R2)*
- **RM-04** — Seul le personnel de l'université ouvre des tickets. *(nouvelle — R1)*
- **RM-05** — Un ticket est pris en charge soit par un technicien, soit attribué à un technicien par le chef de service. *(nouvelle — R2)*
- **RM-06** — L'employé peut annuler son ticket tant qu'il n'est pas pris en charge. *(nouvelle — R3)*
- **RM-07** — Un ticket attribué à un technicien par le chef de service ne peut plus être annulé par l'employé. *(nouvelle — R3)*
- **RM-08** — Une fois le ticket pris en charge, l'employé ne peut plus qu'ajouter un commentaire. *(nouvelle — R3)*
- **RM-09** — Un ticket n'est jamais supprimé. *(nouvelle — R3)*

### 3.2 Niveaux et détermination de la priorité

- **RM-10** — Il existe trois niveaux de priorité, du plus faible au plus élevé : basse, normale, urgente. *(nouvelle — R5, R9)*
- **RM-11** — La priorité initiale découle de l'impact choisi par l'employé : tout un service bloqué → urgente ; un seul poste bloqué → normale ; gêne ou demande → basse. *(nouvelle — R13)*
- **RM-12** — À la prise en charge, le technicien peut corriger la priorité d'un niveau au plus. L'échéance est alors recalculée depuis l'ouverture du ticket. *(nouvelle — R11, R13)*
- **RM-13** — Le chef de service peut fixer n'importe quelle priorité. *(nouvelle — R11)*

### 3.3 Délais, heures ouvrées et échéance

- **RM-14** — Le délai de résolution dépend de la priorité : urgente = 4 heures ouvrées ; normale = 16 heures ouvrées ; basse = 40 heures ouvrées. *(nouvelle — R5)*
- **RM-15** — Les heures ouvrées sont : du lundi au vendredi, de 8h00 à 12h00 et de 13h00 à 17h00. *(nouvelle — R5)*
- **RM-16** — L'échéance d'un ticket est l'instant où le délai de sa priorité est épuisé, en ne comptant que les heures ouvrées écoulées depuis l'ouverture du ticket. *(nouvelle — R4)*
- **RM-17** — Hors des heures ouvrées, le délai ne court pas : un ticket ouvert le soir, pendant la pause ou le week-end commence à compter à la prochaine heure ouvrée. *(nouvelle — R4)*

**Exemples fournis par le client (R5), pour une priorité urgente (4 heures ouvrées) :**

| Ouverture | Échéance | Remarque du client |
| --- | --- | --- |
| Lundi 15h00 | Mardi 10h00 | — |
| Lundi 13h00 | Lundi 17h00 | « pas le mardi à 8h00 » |

### 3.4 Retard

- **RM-18** — Un ticket non résolu dont l'échéance est dépassée est « en retard ». Un ticket résolu à l'heure exacte de son échéance n'est pas en retard. *(nouvelle — R4)*

### 3.5 Hausses de priorité

- **RM-19** — Un ticket ouvert par un employé de la scolarité ou de la direction monte d'un niveau : basse → normale ; normale → urgente ; urgente reste urgente. *(nouvelle — R9)*
- **RM-20** — Un ticket sur un équipement dont un ticket a été résolu moins de 30 jours avant monte d'un niveau. Exemple du client : ticket résolu le 2 mars ; une panne ouverte jusqu'au 31 mars monte, plus à partir du 1er avril. *(nouvelle — R10)*
- **RM-21** — Un ticket ne monte jamais de plus d'un niveau au total, ni au-dessus d'urgente. *(nouvelle — R10)*

### 3.6 Droits par rôle

- **RM-22** — L'employé ouvre, annule et commente ses tickets (annulation dans les limites de RM-06 à RM-08). *(nouvelle — R3, R11)*
- **RM-23** — Le technicien traite les tickets : il les prend en charge, corrige une priorité d'un niveau au plus, ajoute un commentaire et les marque résolus. *(nouvelle — R6, R11)*
- **RM-24** — Le chef de service attribue les tickets (attribution d'un ticket non pris en charge, ou réattribution) et peut fixer n'importe quelle priorité. *(nouvelle — R6, R11)*
- **RM-25** — Personne ne modifie une échéance à la main. Seul le recalcul prévu par RM-12 (correction de priorité par le technicien) peut la faire changer. *(nouvelle — R11, R13)*

### 3.7 Statistiques

- **RM-26** — Le suivi de l'activité porte sur, pour chaque mois et chaque priorité : les tickets ouverts, les tickets résolus et le taux de retard (tickets résolus après leur échéance ÷ tickets résolus) ; et sur le nombre de tickets résolus par technicien. *(nouvelle — R12)*
- **RM-27** — Seul le chef de service voit ces statistiques. *(nouvelle — R12)*

---

## 4. Exigences non fonctionnelles

- **REQ-NF-01** — La plateforme doit être disponible. *(inchangée — demande initiale)*
- **REQ-NF-02** — La plateforme doit être réactive. *(inchangée — demande initiale)*

Ces deux exigences restent **non vérifiables en l'état** : le client n'a fourni ni indicateur ni valeur cible. Aucune valeur n'est proposée ici (voir QO-02).

---

## 5. Hors périmètre de la version 1

Seuls figurent ici les éléments que le client a explicitement exclus ou reportés.

| Élément | Nature | Source exacte |
| --- | --- | --- |
| Base de connaissances (solutions types) | Reportée (hors première version) | R14 : « La base de connaissances (solutions types) : pas dans la première version. » |
| Ouverture de tickets par les étudiants | Exclue | R1 : « Seul le personnel de l'université ouvre des tickets ; les étudiants passent par le secrétariat de leur département. » |

**Remarque :** les restrictions concernant la suppression d'un ticket, l'annulation par l'employé après prise en charge ou attribution, et la modification manuelle d'une échéance sont définies dans les règles métier de la section 3 (RM-07, RM-08, RM-09 et RM-25). Ce sont des règles de fonctionnement, et non des fonctionnalités exclues du périmètre.

**Ne sont pas hors périmètre** (aucune décision du client) : les notifications par courriel (R7 : « nous n'avons pas encore décidé »), ainsi que tout élément listé en section 6.

---

## 6. Questions ouvertes

### 6.1 Décisions confirmées par le client

| Décision | Source |
| --- | --- |
| Seul le personnel ouvre des tickets ; les étudiants passent par le secrétariat de leur département. | R1 |
| Enregistrement immédiat avec numéro, impact et équipement éventuel ; prise en charge par un technicien ou attribution par le chef. | R2 |
| Annulation par l'employé tant que le ticket n'est pas pris en charge ; ensuite, commentaire seul ; ticket attribué par le chef non annulable ; aucune suppression. | R3 |
| Définition de l'échéance et du retard ; le délai ne court qu'en heures ouvrées. | R4 |
| Délais de 4, 16 et 40 heures ouvrées ; heures ouvrées du lundi au vendredi, 8h00–12h00 et 13h00–17h00. | R5 |
| Définition de « traiter un ticket » et de « gérer la répartition ». | R6 |
| Hausse d'un niveau pour la scolarité et la direction. | R9 |
| Hausse d'un niveau si un ticket a été résolu sur le même équipement moins de 30 jours avant ; une seule hausse au total ; plafond urgente. | R10 |
| Droits de l'employé, du technicien, du chef de service ; échéance non modifiable à la main. | R11 |
| Contenu et restriction d'accès des statistiques. | R12 |
| Conflit technicien / employé tranché : la priorité découle de l'impact choisi par l'employé ; correction possible par le technicien à la prise en charge, avec recalcul de l'échéance. | R13 |
| Base de connaissances exclue de la version 1. | R14 |
| Import des employés (annuaire) et des équipements (registre d'inventaire) ; priorité du client : ouvrir un ticket avec la bonne priorité et la bonne échéance, et savoir lesquels sont en retard. | R8 |

### 6.2 Informations encore inconnues (à demander au client)

**Notifications et qualités**

- **QO-01** — Faut-il envoyer un courriel à l'employé à chaque changement de statut ? Le client n'a pas décidé (R7). Un autre canal est-il envisagé ?
- **QO-02** — Qualités non chiffrées : plages horaires de disponibilité, indisponibilité maximale tolérable, temps de réponse acceptable, nombre d'utilisateurs simultanés (questions 26 à 28 sans réponse). Quand le client les fournira, REQ-NF-01 et REQ-NF-02 pourront être rendues vérifiables.
- **QO-03** — La plateforme doit-elle être accessible depuis un ordinateur, un téléphone, ou les deux (question 4 sans réponse) ?

**Utilisateurs et accès**

- **QO-04** — Comment l'employé s'authentifie-t-il (question 1 sans réponse) ? Un employé ne voit-il que ses propres tickets ?
- **QO-05** — Quel est le rôle exact du secrétariat de département pour les étudiants (R1) : ouvre-t-il un ticket à leur place, avec quel statut ?
- **QO-06** — Un technicien peut-il ouvrir un ticket pour un employé qui appelle (question 10) ? Les anciennes demandes reçues par courriel ou par téléphone doivent-elles être reprises (question 11) ?

**Contenu et états du ticket**

- **QO-07** — Quelle est la liste complète des statuts d'un ticket (question 7) ? R3 et R7 évoquent des « statuts » sans les lister. Un ticket résolu peut-il être rouvert ou clos (question 8) ?
- **QO-08** — Quelles autres informations accompagnent un ticket (description, lieu, catégorie, pièces jointes) (questions 5 et 6) ? R2 ne cite que le numéro, l'impact et l'équipement.
- **QO-09** — L'employé peut-il commenter un ticket résolu ou annulé (R3, R11) ?
- **QO-22** — Un ticket annulé par son employé reste-t-il visible pour lui, et que voit-il alors ? (RM-09 : un ticket n'est jamais supprimé, mais la visibilité n'est pas précisée.)

**Priorité et échéance**

- **QO-10** — Le technicien peut-il corriger la priorité une nouvelle fois après la prise en charge initiale ? « D'un niveau au plus » vaut-il dans les deux sens (hausse et baisse) ? La correction part-elle de la priorité initiale ou de la priorité après les hausses automatiques ?
- **QO-11** — La limite d'une seule hausse de priorité au total (RM-21) concerne-t-elle uniquement les hausses automatiques prévues par RM-19 et RM-20, ou inclut-elle également la correction du technicien (RM-12) ? Comment cette limite s'applique-t-elle lorsqu'une priorité est fixée par le chef de service (RM-13) ?
- **QO-12** — L'échéance est-elle aussi recalculée quand le chef de service fixe une priorité ? R13 ne le précise que pour la correction du technicien.
- **QO-13** — Y a-t-il des jours fériés ou des fermetures exceptionnelles à exclure des heures ouvrées ? R5 ne définit que les jours de semaine ordinaires.
- **QO-14** — Les « services qui ne peuvent pas attendre » (demande initiale) sont-ils exactement la scolarité et la direction (R9) ? D'autres services sont-ils concernés (question 2) ?

**Répartition**

- **QO-15** — Un technicien peut-il prendre en charge un ticket déjà attribué à un autre technicien ? Le chef peut-il réattribuer un ticket déjà pris en charge par un technicien ? Un technicien peut-il transmettre un ticket à un collègue (question 22) ? Des spécialités influencent-elles l'attribution (question 21) ?

**Retard et statistiques**

- **QO-16** — Qui voit les tickets en retard (R8 : « savoir lesquels sont en retard ») : le chef de service, les techniciens, les employés ?
- **QO-17** — Statistiques : un ticket compte-t-il dans le mois de son ouverture ou de sa résolution ? Le nombre de tickets résolus par technicien est-il aussi ventilé par mois et par priorité ? Les tickets annulés sont-ils comptés ? Quelle valeur afficher quand aucun ticket n'est résolu (taux de retard) ? Un export ou un historique est-il nécessaire (question 25) ?
- **QO-18** — Comment l'import depuis l'annuaire et le registre d'inventaire est-il réalisé et à quelle fréquence (R8) ?
- **QO-19** — La liste des tickets en retard inclut-elle les tickets annulés ? Un ticket résolu en retard y reste-t-il affiché après sa résolution (R4, R8) ?
- **QO-20** — Statistiques : la priorité retenue pour compter un ticket est-elle la priorité initiale ou la priorité finale (après correction du technicien ou fixation par le chef) (R12, R13) ?
- **QO-21** — Statistiques : le taux de retard s'affiche-t-il en fraction ou en pourcentage (R12) ?

### 6.3 Nouvelles questions issues du raffinement des User Stories

Ces questions sont apparues en rédigeant les User Stories (exemples et critères). Le client n'y a pas répondu : ce ne sont pas des décisions du client.

- **NQ-01** — L'impact est-il obligatoire ? Que fait le système si l'employé n'en choisit aucun ? REQ-F-01b dit que le système « demande » de choisir, mais ne dit pas qu'il bloque. *(US-01, exemple 12)*
- **NQ-02** — Que fait le système si le numéro d'inventaire saisi n'existe pas dans le registre importé ? Si l'employé a quitté l'université ? *(US-01, exemple 13 ; US-15)*
- **NQ-03** — Format du numéro de ticket (HYP-01 : unicité supposée). *(US-01)*
- **NQ-04** — Précision de l'heure d'ouverture et de l'échéance (à la minute ? à la seconde ?) pour les calculs aux limites (par ex. ouverture à 16h59). *(US-01)*
- **NQ-05** — Qui voit les commentaires d'un ticket : pour les commentaires de l'employé, le technicien en charge, le chef, tous les techniciens ? Pour les commentaires du technicien, l'employé du ticket ? *(US-04, US-07)*
- **NQ-06** — Si l'échéance recalculée est déjà dépassée (correction de priorité à la prise en charge), le ticket est-il aussitôt en retard ? *(US-06, exemple 9)*
- **NQ-07** — Quel est l'effet d'une réattribution sur la priorité et l'échéance ? *(US-10, H-US10-a)*

### 6.4 Hypothèses à valider

Ces hypothèses ne sont pas des décisions du client.

| ID | Hypothèse | À valider via |
| --- | --- | --- |
| HYP-01 | Le numéro attribué à un ticket (R2) est unique. | — |
| HYP-02 | La hausse de R9 (scolarité, direction) correspond à la demande initiale « certains services ne peuvent pas attendre ». | QO-14 |
| HYP-03 | L'appartenance d'un employé à la scolarité ou à la direction est connue par son service, importé de l'annuaire (R8). | QO-14 |
| HYP-04 | Les hausses RM-19 et RM-20 sont évaluées à l'ouverture du ticket (R10 : « une panne ouverte jusqu'au 31 mars »). | QO-11, QO-12 |
| HYP-05 | La comparaison « moins de 30 jours » se fait par date calendaire, comme l'exemple de R10 le suggère (2 mars → monte jusqu'au 31 mars, plus à partir du 1er avril). | QO-11 |
| HYP-06 | Un ticket sans équipement renseigné n'est pas concerné par la hausse RM-20. | QO-08 |
| HYP-07 | Seuls les tickets résolus (et non annulés) comptent pour RM-20. | QO-17 |
| HYP-08 | Dans R3, « pris en charge » désigne la prise en charge par un technicien, distincte de l'attribution par le chef (qui bloque déjà l'annulation, RM-07). | QO-07 |

---

## 7. Traçabilité

### 7.1 Exigences et règles métier → sources

| ID | Réponse du client | Demande initiale / TP1 |
| --- | --- | --- |
| REQ-F-01a | R1, R2 | « Les employés doivent pouvoir signaler un problème » ; TP1 : REQ-F-01 |
| REQ-F-01b | R2, R13 | « Les employés voudraient indiquer l'urgence de leur problème dès qu'ils le signalent » ; conflit tranché par R13 |
| REQ-F-01c | R2 | — (réponse client) |
| REQ-F-01d | R2 | « en perd une partie » (problème métier) |
| REQ-F-02 | — | « et voir où en est leur demande » ; TP1 : REQ-F-02 |
| REQ-F-03a à 03d | R2, R6, R11, R13 | « Les techniciens doivent traiter les tickets » ; TP1 : REQ-F-03 |
| REQ-F-04a, 04b | R2, R6 | « Le chef de service veut gérer la répartition du travail » ; TP1 : REQ-F-04 |
| REQ-F-04c | R11 | — |
| REQ-F-05a à 05d | R12 | « Le chef de service veut… suivre l'activité » ; TP1 : REQ-F-05 |
| REQ-F-06a | R13 | « Les problèmes urgents doivent être résolus rapidement » ; TP1 : REQ-F-06 |
| REQ-F-06b, 06c | R4, R5, R13 | idem |
| REQ-F-06d | R4, R8 | idem |
| REQ-F-07 | R10 | « Les pannes qui reviennent sans cesse sur le même poste doivent passer avant les autres » ; TP1 : REQ-F-07 |
| REQ-F-08 | R9 | « certains services ne peuvent pas attendre » ; TP1 : REQ-F-08 (hypothèse HYP-02) |
| REQ-F-09 | R3 | — |
| REQ-F-10 | R3, R11 | — |
| REQ-F-11, 12 | R8 | — |
| REQ-NF-01, 02 | — | « La plateforme doit être disponible et réactive » ; TP1 : REQ-NF-01, REQ-NF-02 |
| RM-01 à RM-03 | R2 | — |
| RM-04 | R1 | — |
| RM-05 | R2 | — |
| RM-06 à RM-09 | R3 | — |
| RM-10 | R5, R9 | — |
| RM-11 | R13 | conflit technicien / employé du TP1 |
| RM-12 | R11, R13 | idem |
| RM-13 | R11 | — |
| RM-14, RM-15 | R5 | « résolus rapidement » (TP1 : question sur les délais) |
| RM-16, RM-17 | R4, R5 | idem |
| RM-18 | R4 | — |
| RM-19 | R9 | « certains services ne peuvent pas attendre » |
| RM-20, RM-21 | R10 | « Les pannes qui reviennent sans cesse sur le même poste » |
| RM-22 à RM-24 | R3, R6, R11 | — |
| RM-25 | R11, R13 | — |
| RM-26, RM-27 | R12 | « suivre l'activité » |

### 7.2 Réponses du client → exigences et règles métier

| Réponse | Sujet | Couverte par |
| --- | --- | --- |
| R1 | Seul le personnel ouvre des tickets | REQ-F-01a, RM-04, hors périmètre |
| R2 | Enregistrement, contenu, prise en charge / attribution | REQ-F-01b à 01d, REQ-F-03a, REQ-F-04a, RM-01 à RM-03, RM-05 |
| R3 | Annulation, commentaire, pas de suppression | REQ-F-09, REQ-F-10, RM-06 à RM-09 |
| R4 | Échéance et retard | REQ-F-06b, 06d, RM-16 à RM-18 |
| R5 | Délais et heures ouvrées | REQ-F-06b, RM-14, RM-15, RM-17 |
| R6 | « Traiter » et « gérer la répartition » | REQ-F-03a à 03d, REQ-F-04a, 04b, RM-23, RM-24 |
| R7 | Courriels de changement de statut | QO-01 (non décidé) |
| R8 | Priorité du client, import annuaire et inventaire | REQ-F-06d, REQ-F-11, REQ-F-12, QO-16, QO-18 |
| R9 | Hausse scolarité / direction | REQ-F-08, RM-19 |
| R10 | Hausse sur équipement, limite d'un niveau | REQ-F-07, RM-20, RM-21 |
| R11 | Droits par rôle, échéance non modifiable | REQ-F-03b, 04c, RM-13, RM-22 à RM-25 |
| R12 | Statistiques réservées au chef | REQ-F-05a à 05d, RM-26, RM-27 |
| R13 | Priorité découlant de l'impact | REQ-F-01b, 06a, 06c, RM-11, RM-12 |
| R14 | Base de connaissances | Hors périmètre v1 |

### 7.3 Synthèse des changements par rapport au TP1

| Exigence TP1 | Devenue en v2 | Origine du changement |
| --- | --- | --- |
| REQ-F-01 | REQ-F-01a à 01d | R1, R2, R13 |
| REQ-F-02 | REQ-F-02 | inchangée |
| REQ-F-03 | REQ-F-03a à 03d | R2, R6, R11, R13 |
| REQ-F-04 | REQ-F-04a, 04b (+ 04c nouvelle) | R2, R6, R11 |
| REQ-F-05 | REQ-F-05a à 05d | R12 |
| REQ-F-06 | REQ-F-06a à 06d | R4, R5, R8, R13 |
| REQ-F-07 | REQ-F-07 | R10 |
| REQ-F-08 | REQ-F-08 | R9 (hypothèse HYP-02) |
| REQ-NF-01, REQ-NF-02 | inchangées | valeurs cibles toujours inconnues (QO-02) |
| — | REQ-F-09 à REQ-F-12 (nouvelles) | R3, R8, R11 |