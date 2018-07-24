# dockerizeDrupal
Docker containers around drupal projects

Fork from Docker4drupal to initiate containers around Drupal stack

Pré-requis:
===========
 > Docker with linux-containers enabled
 > Git

Utilisation:
============
Récupérer le code source
  > git clone https://github.com/Sim0/dockerizeDrupal.git
  > cd dockerizeDrupal/

Créer le fichier .env qui va définir vos choix d'environment (Version, Outils, port)
  > cp .env.dist .env

Renseigner les variables d'environnement propre à votre projet:

SOUS ## projects_setting
>PROJECT_NAME=Nom_Projet
>PROJECT_BASE_URL=Nom_Projet.localhost

>DB_NAME=Nom_BD
>DB_USER=UTILISATEUR_BD
>DB_PASSWORD=PASSWORD_BD
>DB_ROOT_PASSWORD=ROOT_PASSWORD
>DB_HOST=DB_HOST
>DB_DRIVER=mysql

Décommenter les versions des outils que vous souhaitez installer sous les sections :
>### --- MARIADB ----
>### --- VANILLA DRUPAL ----
>### --- PHP ----
>### --- NGINX ----
>### --- SOLR ---
>### --- ELASTICSEARCH ---
>### --- KIBANA ---
>### --- REDIS ---
>### --- NODE ---
>### --- POSTGRESQL ----
>### OTHERS

le fichier docker-compose.yml se base sur les variables d'environnement que vous avez intié. Si vous souhaitez rajouter une configuration docker c'est directement dans ce fichier.
Pour un fonctionnement optimal ne touchez pas à cette configuration.

Sous windows, pour éviter un problème de chemin exécuter la commande :
>set COMPOSE_CONVERT_WINDOWS_PATHS=1
(ref https://github.com/docker/compose/issues/4240)

installer et charger vos containers :
> docker-compose up -d
