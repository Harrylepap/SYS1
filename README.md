# Installation d'un environnement pour le cours SYS1
Voici un fichier _docker-compose_ qui peut être utilisé pour créer un conteneur Debian Jessie (version 8) pour l'enseignement de GNU/Linux

## Exigences:
* [Docker](https://www.docker.com/products/docker-desktop/) doit être installé sur votre machine
* [docker-compose](https://docs.docker.com/compose/install/) version 3.8 ou ultérieure doit être installé sur votre machine


## Démarrage de l'activité
1. Créez un nouveau répertoire sur votre machine et naviguez jusqu'à lui dans le terminal.
2. Créez un nouveau fichier appelé docker-compose.yml dans ce répertoire, et copiez-y le contenu suivant :

```bash
version: '3.8'
services:
  server_debian:
    image: debian:8
    container_name: debian_jessie
    tty: true
    platform: linux/x86_64 #for M1 user only
```
3. Démarrez le conteneur en exécutant la commande suivante dans le terminal :

```sh
$ docker-compose up -d
```
Cette commande démarre le conteneur en mode détaché, afin qu'il fonctionne en arrière-plan.

4. Pour arreter le conteneur :

```sh
$ docker-compose down 
```

## Explication
* Le champ **version** spécifie la version du format de fichier docker-compose qui est utilisée.
* Le champ **services** définit le conteneur qui sera créé.
* Le champ **image** spécifie l'image de base pour le conteneur. Dans ce cas, il est défini sur debian:8, ce qui indique à Docker d'utiliser l'image Debian Jessie.
* Le champ **container_name** indique le nom du conteneur.
* Le champ **tty** est défini sur true, ce qui permet au conteneur de fonctionner en mode interactif avec un TTY.
* Le champ **platform** est défini à linux/x86_64 est spécifique à l'utilisateur des puces M1 uniquement et ce champ est utilisé pour spécifier l'architecture du conteneur.

Veuillez noter que Debian 8 n'est plus maintenue, il est donc recommandé d'utiliser la dernière version pour des raisons de sécurité.