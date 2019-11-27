# Requis - Projet MPOP

Dans ce document, on détaille les requis du projet MPOP.

Résumé: On pose des questions aux visiteurs au sujet du système carcéral, et on leur offre une visualisation des données des réponses.

Le système comporte trois composantes: (1) les bornes questionnaires; (2) la visualisation des données; et (3) le serveur pour la base de données.

## Bornes questionnaires

### Récits-utilisateurs - Questionnaires

#### Lire ma carte RFID

En tant qu'usager je dois pouvoir lire ma carte RFID pour associer ma profil à mes réponses.

#### Répondre à une question à glissière

#### Répondre à une question à choix multiples

#### Répondre à plusieurs questions à glissière dans une seule page

Poser des questions à réponse unique aux participants
Stocker les réponses des participants

#### Passer à la page suivante

En tant qu'usager je dois pouvoir passer à la page suivante, une fois la ou les questions de la page actuelle ont été répondues, et ce afin de pouvoir répondre aux questions de la page suivante.

### Requis non-fonctionnels - questionnaires

#### Chaque borne doit pouvoir avoir des questions différentes

Les "bornes centrales" ont la plupart des questions. Les "bornes périphériques" ont d'autres questions - souvent une seule.

Détails techniques:

- On peut utiliser des variables d'environnement pour que chaque borne charge la bonne page.

#### Transmettre les réponse à une base de donnée centralisée

















## Visualisation des données

Visualiser les données de manière interactive.

### Requis non-fonctionnels - visualisation

#### Sortie NDI

En tant qu'intégrateur vidéo, je peux avoir une sortie NDI pour pouvoir envoyer l'image à un logiciel de mapping vidéo, tel que Resolume Arena.

Détails:

- Cela peut être un utiliser de screencast, comme OBSBroadcaster (?)
- Il faudra passer par câble Ethernet, car la vidéo est non-compressée.

#### Utiliser une librairie de haut niveau pour la dataviz

Détails techniques:

- D3.js est excellente.
