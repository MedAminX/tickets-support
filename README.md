# tickets-support

**Plateforme de tickets pour le support informatique d'une université**
Projet d'équipe — Génie Logiciel (Sujet n° 12)

---

## Contexte

Le service informatique d'une université (5 techniciens et un chef de service, pour environ 900 employés) reçoit trop de demandes par téléphone et par courriel, et en perd une partie. Il souhaite une plateforme de tickets d'incident.

Dans ce projet, l'enseignant joue le rôle du client. Nous ne définissons pas les règles à sa place : tout ce que la demande ne dit pas devient une question, qui lui est adressée.

## La demande du client

- Les employés signalent un problème et suivent l'avancement de leur demande.
- Les techniciens traitent les tickets.
- Le chef de service gère la répartition du travail et suit l'activité.
- Les problèmes urgents sont résolus rapidement ; certains services ne peuvent pas attendre.
- Les pannes qui reviennent sans cesse sur le même poste passent avant les autres.
- Les techniciens veulent fixer eux-mêmes la priorité ; les employés veulent indiquer l'urgence au moment du signalement (point à arbitrer par le client).
- La plateforme doit être disponible et réactive.

## Structure du dépôt

```text
tickets-support/
├── README.md
├── docs/
│   ├── questions-client.md      # Questions envoyées au client
│   └── stories/                 # Récits utilisateur (étapes suivantes)
└── tp/
    └── TP1.md                   # Réponses au TP1
```

## Avancement

| Étape | Livrable | Statut |
| --- | --- | --- |
| TP1 | Réponses au TP1 : problème, parties prenantes, objectifs, périmètre, premières exigences | Fait → [`tp/TP1.md`](tp/TP1.md) |
| TP1 | Questions pour le client (28 questions) | Envoyées par e-mail → [`docs/questions-client.md`](docs/questions-client.md) |
| TP2 | Intégration des réponses du client | À venir |

## Démarche

1. Partir de la demande du client, sans y ajouter de règles.
2. Distinguer ce qui est connu, supposé et inconnu.
3. Transformer chaque inconnue en question pour le client.
4. Écrire les exigences avec leur source, pour garder la traçabilité.
5. Contrôler les propositions de l'IA face à la demande avant de les retenir.
