![work status](https://img.shields.io/badge/work-on%20progress-red.svg)
![Medy Lord ](https://img.shields.io/badge/Medy%20Lord-Java-green)
![PHP](https://img.shields.io/badge/Medy%20Lord-SpringBoot-yellowgreen)

# Prérequis
* Java 17
* Docker
* Maven

# Configuration de Docker Compose

- Voici un aperçu du fichier de config Service MySQL (mysql-admin-db)

![Service_MySQL](https://github.com/Medy2468/admin-app-main/assets/95325770/befbd4f8-2bb5-4d1e-bcf4-881ba7314e02)

Cette configuration utilise l'image `mysql:8.0` avec le nom du conteneur défini comme `container_mysql-admin-db`. Ainsi, la création de la base de données peut être effectuée en utilisant les identifiants suivants :

* Base de donnee : adminapp-db
* l'utilisateur : user
* Mot de passe : user

Le conteneur utilise la connexion via le port `3306`. Les données MySQL seront stockées dans le volume défini par la variable `mysql_data`. De plus, une vérification de santé est effectuée à l'aide de la commande `mysqladmin ping` pour garantir la disponibilité de MySQL.

- Voici un aperçu du fichier de config Service PHPMYADMIN (phpmyadmin-admin-db)

  ![Service_PHPMyAdmin](https://github.com/Medy2468/admin-app-main/assets/95325770/dd262dbf-3b8d-41bf-beca-3bea4855c0cc)

Ce service est basé sur la dernière image Docker de `PhpMyAdmin`, dépendant du service `MySQL` et est configuré pour établir une connexion au serveur MySQL. Il est configuré pour utiliser le port `8085` pour les communications.

- Le volume

  ![Volume](https://github.com/Medy2468/admin-app-main/assets/95325770/6713c90e-f339-414a-87a7-a9fc606c1faa)

  Les volumes Docker offrent une solution pour garantir la persistance des données au-delà du cycle de vie des conteneurs. Dans ce projet, le volume `mysql_data` est employé pour stocker de manière persistante les données de MySQL. Cette approche assure que les données demeurent intactes même lorsque le conteneur est arrêté, évitant ainsi la perte d'informations.
  
* Generer la base de donnée

![Generer_BaseDonnee](https://github.com/Medy2468/admin-app-main/assets/95325770/97e39d6a-a330-49ac-9ffb-0419f2d08e90)

Dans phpMyAdmin

![BaseDonnee](https://github.com/Medy2468/admin-app-main/assets/95325770/d9555270-91f8-441e-9117-ba0c7a57bee3)

# Comment faire la configuration de Docker Compose
- Il faut d'abord cloner le projet dans la machine local
- Puis se rassurer que notre environnement Docker et Docker Compose est bien installé
- Ensuite exécuter la commande `docker compose up -d`.
  
![compose_up](https://github.com/Medy2468/admin-app-main/assets/95325770/21e6f9c9-e82f-4b5f-9b72-878f1e82cf50)

- Le volume créé dans Docker Desktop

  ![Volume_Docker](https://github.com/Medy2468/admin-app-main/assets/95325770/161f0cd7-879e-4f6e-a8bc-9e7e7a92256d)



  
