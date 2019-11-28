# Architecture logicielle

## RFID

Nous utilisons des tags RFID pour identifier les participants.

Voici quelques tags RFID que nous avons:

```TEXT

2900AA840700
2900AD838186
2900AD8D040D
2900ADB6083A
2900ADF77A09
2900AE190799
2900AE269130
2900AE5CA873
2900E953EA79
2900EC7D2890
6400DAB81F19
6400DC39BA3B
```

À la fin du parcours, les visiteurs doivent déposer leur carte RFID dans un contenant où se trouve le lecteur ultime.
Ce lecteur va réinitialiser la carte, et la rendre disponible pour un nouvel usager.

Comme lecteur RFID, nous utilisons celui du Sparkfun RFID Starter Kit, via USB, grâce à la puce FTDI. This kit includes our USB RFID Reader, ID-12LA RFID module, and two 125kHz RFID cards. Open a terminal program of your choice at 9600bps 8N1. (eight (8) data bits, no (N) parity bit, and one (1) stop bit.)

Le protocole sériel ce kit utilise inclut un espace avant le texte du numéro de série, un espace après, puis un charactère newline. Comme ceci:

```TEXT
 2900E953EA79 
```

Nous prévoyons créer une librairie JavaScript pour ce faire.

- Détecter les contrôlleurs USB FTDI branchés.
- Se connecter au premier.
- Se reconnecter en cas de déconnexion
- Recevoir les numéros de puces RFID détectées.
- Envoyer ces informations au clients qui l'observent.

## Base de données

Comme base de données, nous préférons les systèmes de base de données SQL plutôt que noSQL, car la maintenance sera plus facile.

On peut prendre Flyway pour gérer les migrations de base de données. Le tout dans des conteneurs Docker.

### Schema

Voici le schéma prévu pour notre base de données:

![Database schema](images/database.png)


## Service pour stocker les réponses

Voici la signature des méthodes de notre API:

![Facade](images/facade.png)

Une interface JSON-RPC 2.0 va imiter fournir des méthodes semblables aux clients.
