# Génie Logiciel — TP1 : Du besoin métier aux premières exigences

**Projet :** tickets-support — Support informatique : tickets d'incident
**Client :** Le service informatique d'une université (5 techniciens, un chef de service, environ 900 employés)

---

## 1. Référentiel de la demande client

Les éléments ci-dessous sont repris de la demande. Tout ce qui n'y figure pas est traité comme hypothèse, point ouvert ou proposition à rejeter.

- Le service informatique reçoit trop de demandes par téléphone et par courriel, et en perd une partie.
- Le service veut une plateforme de tickets.
- Les employés doivent pouvoir signaler un problème.
- Les employés doivent pouvoir voir où en est leur demande.
- Les techniciens doivent traiter les tickets.
- Le chef de service veut gérer la répartition du travail.
- Le chef de service veut suivre l'activité.
- Les problèmes urgents doivent être résolus rapidement.
- Certains services ne peuvent pas attendre.
- Les pannes qui reviennent sans cesse sur le même poste doivent passer avant les autres.
- Les techniciens souhaitent fixer eux-mêmes la priorité de chaque ticket.
- Les employés voudraient indiquer l'urgence de leur problème dès qu'ils le signalent.
- La plateforme doit être disponible et réactive.

---

## 2. Partie 1 — Problème, parties prenantes, objectifs

### Q1 — Problème métier

Les demandes d'assistance informatique arrivent par des canaux dispersés (téléphone, courriel), ce qui entraîne la perte de certaines demandes et empêche les employés comme le service de savoir où en est le traitement d'un problème.

*Source : « Le service informatique reçoit trop de demandes par téléphone et par courriel, et en perd une partie. »*

Remarque : « Il faut une plateforme de tickets » décrit déjà une solution, pas le problème.

### Q2 — Parties prenantes

| Partie prenante | Statut | Attente |
| --- | --- | --- |
| Employé | Explicite | Signaler un problème, suivre l'avancement de sa demande, indiquer l'urgence. |
| Technicien | Explicite | Traiter les tickets, fixer la priorité. |
| Chef de service | Explicite | Gérer la répartition du travail, suivre l'activité. |
| Responsables des « services qui ne peuvent pas attendre » | Potentielle | Concernés par l'urgence, mais on ne sait pas s'ils sont des utilisateurs distincts. À clarifier. |
| Direction de l'université | Potentielle | Peut s'intéresser au suivi de l'activité. Non mentionnée dans la demande. |
| Administrateur de la plateforme | Potentielle | Exploitation et maintenance. À confirmer. |

Aucun acteur supplémentaire (fournisseurs, prestataires externes, étudiants) n'est considéré comme confirmé.

### Q3 — Objectifs SMART (sans valeurs inventées)

- **OBJ-01 :** Réduire la proportion de demandes perdues de [valeur actuelle à mesurer] à [valeur cible à valider] dans les [délai à valider] suivant la mise en service.
- **OBJ-02 :** Centraliser [proportion à valider] des demandes d'assistance dans la plateforme dans un délai de [à valider].
- **OBJ-03 :** Réduire le délai moyen de résolution des problèmes urgents de [valeur actuelle à mesurer] à [valeur cible à valider] sur [période à valider].
- **OBJ-04 :** Permettre à [proportion à valider] des employés de consulter l'état de leur demande sans contacter le service, d'ici [délai à valider].

### Q4 — Objectif difficile à mesurer

« La plateforme doit être disponible et réactive » est difficile à mesurer, car « réactive » et « disponible » ne sont ni définis ni chiffrés. Il faut définir des indicateurs (taux de disponibilité sur une plage horaire donnée, temps de réponse des pages, nombre d'utilisateurs simultanés) puis fixer les valeurs cibles avec le client.

---

## 3. Partie 2 — Ce que l'on sait et ce que l'on ne sait pas

### Q5 — Classification

| Élément | Catégorie | Justification |
| --- | --- | --- |
| Signaler un problème | Dans le périmètre | Explicite. |
| Suivre l'avancement d'une demande | Dans le périmètre | Explicite (« voir où en est leur demande »). |
| Traiter les tickets (technicien) | Dans le périmètre, à préciser | Les actions de traitement ne sont pas détaillées. |
| Gérer la répartition du travail (chef) | Dans le périmètre, à préciser | « Répartition » est ambigu (affectation manuelle ? automatique ?). |
| Suivre l'activité (chef) | Dans le périmètre, à préciser | Indicateurs non précisés. |
| Résoudre rapidement les problèmes urgents | Règle / exigence initiale | Explicite, mais « rapidement » et « urgent » ne sont pas définis. |
| Services qui ne peuvent pas attendre | Règle à préciser | Quels services ? Quel traitement spécial ? |
| Pannes récurrentes sur un même poste prioritaires | Règle à préciser | Seuil de récurrence et période non définis. |
| Priorité fixée par le technicien | Conflit de besoins | Contradiction avec l'urgence indiquée par l'employé. |
| Urgence indiquée par l'employé | Conflit de besoins | Idem. |
| Plateforme disponible et réactive | BNF à préciser | Non mesurable en l'état. |
| Accès depuis ordinateur / téléphone | Point ouvert | Non précisé. |
| Employés ont un compte universitaire | Hypothèse | Non indiqué. |
| Authentification obligatoire | Point ouvert | Non précisé. |
| Notifications (courriel, etc.) | Point ouvert | Non précisé. |
| Pièces jointes / captures d'écran | Point ouvert | Non précisé. |
| Catégories de problèmes | Point ouvert | Non précisé. |
| Gestion du parc de postes (identification d'un poste) | Point ouvert | Nécessaire pour détecter la récurrence, mais non décrite. |
| Délais de résolution (SLA) | Point ouvert | Non précisé. |
| Clôture / réouverture d'un ticket | Point ouvert | Non précisé. |
| Réaffectation entre techniciens | Point ouvert | Non précisé. |
| Reprise des courriels/appels existants dans la plateforme | Point ouvert | Non précisé. |
| Tickets créés par un technicien pour un appel téléphonique | Point ouvert | Non précisé. |

**Hypothèse** = ce que l'équipe suppose provisoirement. **Point ouvert** = ce qu'elle doit demander au client. Chaque hypothèse importante génère un point ouvert.

### Q6 — Hors périmètre

La demande ne permet pas de déclarer avec certitude une fonctionnalité « hors périmètre ». En cas de doute, l'élément devient un point ouvert (par exemple : assistance aux étudiants, gestion du parc matériel complet, base de connaissances). Aucune information ne justifie l'inclusion de la facturation ou de la gestion des achats de matériel.

---

## 4. Partie 3 — Premières exigences

### Q7 — Exigences initiales et traçabilité

| ID | Exigence | Type | Source | Appréciation |
| --- | --- | --- | --- | --- |
| REQ-F-01 | Le système doit permettre à un employé de signaler un problème. | F | « Les employés doivent pouvoir signaler un problème » | Acceptable. |
| REQ-F-02 | Le système doit permettre à un employé de consulter l'état d'avancement de sa demande. | F | « …et voir où en est leur demande » | Acceptable ; les états possibles sont à définir. |
| REQ-F-03 | Le système doit permettre à un technicien de traiter les tickets. | F | « Les techniciens doivent traiter les tickets » | Acceptable comme exigence initiale, trop large pour être finale. |
| REQ-F-04 | Le système doit permettre au chef de service de gérer la répartition du travail entre les techniciens. | F | « Le chef de service veut gérer la répartition du travail » | Ambiguïté sur « répartition ». |
| REQ-F-05 | Le système doit permettre au chef de service de suivre l'activité du service. | F | « …et suivre l'activité » | Indicateurs à définir. |
| REQ-F-06 | Le système doit permettre de traiter en priorité les problèmes urgents. | F | « Les problèmes urgents doivent être résolus rapidement » | « Urgent » et « rapidement » à définir. |
| REQ-F-07 | Le système doit traiter en priorité les pannes qui reviennent sur un même poste. | F | « Les pannes qui reviennent sans cesse sur le même poste doivent passer avant les autres » | Règle de récurrence à définir. |
| REQ-F-08 | Le système doit tenir compte des services qui ne peuvent pas attendre. | F | « certains services ne peuvent pas attendre » | Services concernés non identifiés. |
| REQ-NF-01 | La plateforme doit être disponible. | NF | « La plateforme doit être disponible et réactive. » | Non vérifiable en l'état. |
| REQ-NF-02 | La plateforme doit être réactive. | NF | idem | Non vérifiable en l'état. |

**Conflit à ne pas trancher soi-même :** les techniciens veulent fixer la priorité, les employés veulent indiquer l'urgence. Aucune exigence n'est écrite tant que le client n'a pas arbitré (voir questions au client).

Critères de qualité visés : claire, atomique, non ambiguë, cohérente, traçable, vérifiable, sans solution technique prématurée.

### Q8 — Critique d'une exigence ambiguë : « gérer la répartition du travail » (REQ-F-04)

Le terme « répartition » est ambigu : le chef affecte-t-il chaque ticket à un technicien ? La répartition est-elle automatique (par charge, par compétence) ? Peut-il réaffecter ? Voit-il la charge de chaque technicien ? Les opérations ne doivent pas être inventées : l'ambiguïté est transformée en question client (« Comment la répartition des tickets entre techniciens doit-elle fonctionner ? »).

### Q9 — « Disponible et réactive »

Ce n'est pas vérifiable : « réactive » et « disponible » sont subjectifs, sans indicateur ni valeur cible.

Questions acceptables à poser au client :

- Sur quelles plages horaires la plateforme doit-elle être accessible ?
- Quelle indisponibilité maximale est tolérable ?
- Quel temps de réponse est acceptable pour l'affichage d'une page ou la création d'un ticket ?
- Combien d'utilisateurs simultanés faut-il prévoir ?

Aucune valeur cible n'est inventée à ce stade.

---

## 5. Partie 4 — Analyse critique assistée par IA

L'IA n'est pas une autorité : la preuve reste la demande du client. Chaque proposition est confrontée au référentiel (section 1).

| Proposition IA | Décision | Justification |
| --- | --- | --- |
| 1. Définir précisément « urgent » et « rapidement » | Acceptée | Ambiguïté réelle du texte. |
| 2. Définir ce qu'est une panne « récurrente » (nombre, période) | Acceptée | Ambiguïté réelle du texte. |
| 3. Préciser « gérer la répartition du travail » | Acceptée | Ambiguïté présente dans le texte. |
| 4. Arbitrer priorité technicien / urgence employé | Acceptée | Conflit explicite dans la demande. |
| 5. Authentification via compte universitaire (SSO/LDAP) | À valider | Authentification non précisée ; ne pas imposer une technologie. |
| 6. Identifier les « services qui ne peuvent pas attendre » | Acceptée | Ambiguïté présente dans le texte. |
| 7. Catégories de problèmes (réseau, logiciel, matériel) | À valider | Plausible mais absent de la demande. |
| 8. Pièces jointes et captures d'écran | À valider | Plausible mais absent de la demande. |
| 9. Clôture et réouverture d'un ticket | À valider | Cycle de vie du ticket non décrit. |
| 10. Notifications automatiques par courriel / SMS | Rejetée comme exigence | Fonction et canal inventés ; peut devenir une question. |
| 11. SLA avec délais chiffrés (ex. 4 h pour un ticket urgent) | Rejetée comme exigence | Valeurs inventées ; question à poser. |
| 12. Application mobile native | Rejetée | Choix technique non demandé. |
| 13. Chatbot / assistant automatique de diagnostic | Rejetée | Aucun support dans la demande. |
| 14. Base de connaissances / FAQ | À valider | Pertinent mais non demandé. |
| 15. Enquête de satisfaction après clôture | Rejetée | Fonction inventée. |
| 16. « Disponible et réactive » non mesurable | Acceptée | Indicateurs et cibles à définir avec le client. |

### Q10 — Proposition plausible mais inventée

**Exemple :** SLA avec délais de résolution chiffrés par niveau de priorité (ex. « urgent : 4 h »).

Pourquoi elle est convaincante : standard dans les outils de ticketing, semble professionnelle, répond en apparence à « résolu rapidement ».

Pourquoi elle est dangereuse : les valeurs sont inventées, elles ajoutent des règles de calcul des délais, des alertes d'échéance et des tests, et risquent de contredire les pratiques réelles du service. Une proposition plausible n'est pas une exigence valide : elle devient une question au client.

### Q11 — Ambiguïté détectée grâce à l'IA

**Exemple :** le sens de « panne qui revient sans cesse sur le même poste ». À la première lecture, la phrase paraît claire, mais elle suppose un identifiant de poste, un seuil de récurrence et une période, et elle entre en concurrence avec l'urgence déclarée : quelle règle l'emporte ? Elle n'avait pas été détectée car le texte semble donner une règle évidente alors qu'il n'en définit aucun paramètre.

---

## 6. Traçabilité

Chaîne : BESOIN MÉTIER → OBJECTIF → EXIGENCE INITIALE → SOURCE

| Besoin métier | Objectif | Exigence | Source |
| --- | --- | --- | --- |
| Ne plus perdre de demandes | OBJ-01, OBJ-02 | REQ-F-01 | « Les employés doivent pouvoir signaler un problème. » |
| Savoir où en est une demande | OBJ-04 | REQ-F-02 | « …et voir où en est leur demande. » |
| Traiter les urgences rapidement | OBJ-03 | REQ-F-06 | « Les problèmes urgents doivent être résolus rapidement. » |
| Traiter les pannes récurrentes en premier | OBJ-03 | REQ-F-07 | « Les pannes qui reviennent sans cesse sur le même poste doivent passer avant les autres. » |
| Piloter le travail du service | — | REQ-F-04, REQ-F-05 | « Le chef de service veut gérer la répartition du travail et suivre l'activité. » |
| Service fiable | — | REQ-NF-01, REQ-NF-02 | « La plateforme doit être disponible et réactive. » |
