# Requis - Projet MPOP

Dans ce document, on détaille les requis du projet MPOP.

Résumé: On pose des questions aux visiteurs au sujet du système carcéral, et on leur offre une visualisation des données des réponses.

Le système comporte trois composantes: (1) les bornes questionnaires; (2) la visualisation des données; et (3) le serveur pour la base de données.

## Bornes questionnaires

Les bornes à questionnaire sont des écrans tactiles offrant des questions. Un lecteur de cartes RFID permet d'associer les visiteurs à leurs réponses.

### Récits-utilisateurs - Questionnaires

#### Lire ma carte RFID

En tant que visteur, je dois pouvoir lire ma carte RFID pour associer ma profil à mes réponses.

Afficher le RFID de la carte lorsqu'on la lit. Cela va personnaliser l'expérience.

#### Répondre à une question à glissière

En tant que visiteur, je dois pouvoir répondre à une question à glissière simple.

#### Répondre à une question à choix multiples

#### Répondre à plusieurs questions à glissière dans une seule page

En tant que visiteur, je dois pouvoir répondre à une question à glissières multiples.

#### Passer à la page suivante

En tant qu'usager je dois pouvoir passer à la page suivante, une fois la ou les questions de la page actuelle ont été répondues, et ce afin de pouvoir répondre aux questions de la page suivante.

#### Revenir à une question précédente

En tant qu'usager je dois pouvoir revenir à une question précédente, afin de pouvoir changer la réponse que je lui donne.

Critères:

- Ma réponse précédente doit être encore affichée lorsque j'y revient.
- Je dois pouvoir changer ma réponse.

#### Choix de la langue

Options possibles:

- Français
- Anglais

Ce choix et persistent, mais l'usager peut changer d'avis en cours de route.

Détails techniques:

- Option 1: Utiliser un fichier de configuration avec toutes les questions dans les deux langues. Ce fichier de configuration sera partagé par toutes les instances. Il faudra s'assurer que toutes les instances ont les mêmes valeurs pour chaque question.
- Option 2: Utiliser une librairie d'i18n.

### Requis non-fonctionnels - questionnaires

#### Stocker les réponses dans une base de données centralisée

Mes réponses doivent être sauvegardées dans une base de données centralisée.

On veut pouvoir stocker chaque réponse, même lorsqu'une personne a changé de réponse.

#### Formulaire ayant l'apparence familière

En tant qu'usager, je veux répondre à un formulaire dont l'apparence m'est familière.

Détails techniques:

- Un formulaire HTML serait parfait.
- React semble être un excellent choix pour le frontend.

#### Affichage plein-écran

En tant que visiteur, je souhaite ne pas voir de fenêtre ni de bordure, afin que ça soit joli.

Détails techniques:

- Une application Electron peut être affichée en plein-écran.
- Peut-on cacher le curseur?

#### Chaque borne doit pouvoir avoir des questions différentes

Les "bornes centrales" ont la plupart des questions. Les "bornes périphériques" ont d'autres questions - souvent une seule.

Détails techniques:

- On peut utiliser des variables d'environnement pour que chaque borne charge la bonne page.

#### Transmettre les réponses à une base de donnée centralisée

Chaque borne doit pouvoir communiquer avec un serveur centralisé afin de communiquer les réponses de chaque participant.

Détails techniques:

- une clé d'API, chiffrée en TLS sera suffisante pour assurer la sécurité de cette connection.
- un service Web en REST (HTTP POST) ou websocket conviendra.

### Classer les questions en grandes familles

3 grandes catégories:
protéger réhabiliter punir


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
