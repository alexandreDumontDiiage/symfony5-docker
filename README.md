# Environnement de développement Symfony5 
Docker pour faire tourner des applications Symfony 5 / PHP 8

### Prérequis
* [Docker](https://www.docker.com/)

### Container
 - [nginx](https://hub.docker.com/_/nginx) 1.19.+
 - [php-fpm](https://hub.docker.com/_/php) 8.+
    - [composer](https://getcomposer.org/) 
    - [yarn](https://yarnpkg.com/lang/en/) et [node.js](https://nodejs.org/en/) (au besoin [Encore](https://symfony.com/doc/current/frontend/encore/installation.html) pour gérer JS & CSS)
- [mysql](https://hub.docker.com/_/mysql/) 5.7.+

### Explications
L'installation va créer un dossier contenant le projet Symfony à la racine de ce dossier.
Il faut modifier la variable ROOT_FOLDER dans le fichier .env pour qu'il corresponde au nom du porjet Symfony

### Installation

Lancer docker et se connecter au container:
```
 docker-compose up --build
```
```
 docker-compose exec php sh
```

Installer la dernière version de [Symfony](http://symfony.com/doc/current/setup.html) via composer:
```
# application standard: 
composer create-project symfony/website-skeleton {nom-du-projet}
```
ou 
```
# microservice, console application ou API:
composer create-project symfony/skeleton {nom-du-projet}
```
Modifier le DATABASE_URL config dans le fichier .env de symfony 
```
DATABASE_URL=mysql://root:root@mysql:3306/{nom-du-projet}?serverVersion=5.7
```

Dans le fichier .env de ce docker, modifier project-folder par le nom du projet:
```
ROOT_FOLDER={nom-du-projet}
```


### C'est prêt
[localhost](http://localhost/) 

### Thanks
[colosso](https://github.com/coloso/symfony-docker/tree/php8)
