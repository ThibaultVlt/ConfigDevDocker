# Projet

Configuration Docker pour Développement Web

Ce projet fournit une configuration Docker prête à l'emploi pour un environnement de développement web. Il inclut des conteneurs pour un serveur PHP, une base de données MySQL et une interface phpMyAdmin, afin de faciliter le développement et le test d'applications web.

## Description

- **Serveur PHP** : Utilise PHP 8.3 avec Apache.
- **Base de données MySQL** : MySQL 8.4.3 avec un volume persistant pour stocker les données.
- **phpMyAdmin** : Fournit une interface web pour gérer la base de données MySQL.

La configuration est idéale pour les développeurs web souhaitant travailler rapidement sur des projets PHP avec une base de données relationnelle.

---

## Structure des fichiers

- **`php/`** : Répertoire où placer les fichiers PHP de votre projet.
- **`docker-compose.yml`** : Fichier de configuration Docker Compose.
- **`DockerFile`** : Fichier de construction pour le conteneur PHP avec Apache.

---

## Prérequis

- [Docker Desktop](https://www.docker.com/products/docker-desktop) installé sur votre machine.
- [Visual Studio Code](https://code.visualstudio.com/) (facultatif mais recommandé).
- Docker Compose intégré.

---

## Installation et Utilisation

1. **Assurez-vous que Docker Desktop est lancé** et prêt à exécuter les conteneurs.
2. Ouvrez le projet dans VS Code ou un terminal.
3. Exécutez la commande suivante pour construire les images Docker :
   ```bash
   docker-compose build
Lancez les conteneurs avec la commande :
docker-compose up
Une fois les conteneurs démarrés :
Accédez au serveur PHP sur http://localhost:8000.
Accédez à phpMyAdmin sur http://localhost:8081.
Configuration des Conteneurs
Conteneur PHP
Image : php:8.3-apache
Port exposé : 8000
Dossier synchronisé : ./php vers /var/www/html dans le conteneur.
Modules installés : mysqli, pdo, pdo_mysql.
Conteneur MySQL
Image : mysql:8.4.3
Port exposé : 3307
Variables d'environnement :
MYSQL_ROOT_PASSWORD: root
MYSQL_DATABASE: test
MYSQL_USER: user
MYSQL_PASSWORD: password
Volume : dbdata pour persister les données de la base de données.
Conteneur phpMyAdmin
Image : phpmyadmin/phpmyadmin
Port exposé : 8081
Configuration :
Hôte MySQL : mysql
Mot de passe root : root
Volumes
dbdata : Stocke les données de MySQL de manière persistante.
Arrêter les Conteneurs
Pour arrêter les conteneurs, utilisez la commande suivante :

docker-compose down
Notes
Assurez-vous que les ports utilisés (8000, 8081, 3307) ne sont pas déjà occupés par d'autres services.
Si vous souhaitez modifier la configuration (comme les mots de passe ou les ports), mettez à jour le fichier docker-compose.yml avant de démarrer les conteneurs.
Auteur
Configuration rédigée par un développeur passionné de Docker et de développement web. 🚀


### Quelques points à retenir :
- Si tu veux ajouter ou personnaliser un autre point, fais-le-moi savoir !
- Si tu souhaites une section supplémentaire, comme des *FAQs* ou des *détails avancés*, je peux la rajouter facilement. 😊