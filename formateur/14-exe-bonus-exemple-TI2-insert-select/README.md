# Préparation TI2 - Insertion et sélection

## Avec Bonus

## Web C2 2025

### Fichiers

Dupliquez `config.dev.php` en `config.php`

### Importation de données

Importez le fichier `datas/pdo_c2_prepa_ti2.sql` via `phpMyAdmin` ou un autre outil de gestion de base de données vers `MySQL`.

### Chemin

Le dossier public de l'application est `public` et le fichier d'entrée est `index.php`.

### Navigation

Dans le fichier de configuration, il existe 2 constantes pour la pagination

```php
# pour la pagination
const PAGINATION_NB = 5;
const PAGINATION_GET = "pg";
```

L'objectif est d'avoir maximum 5 articles par page, puis une pagination se met en place


# Exercice Bonus TI2 - Insertion et Sélection avec Pagination

## Description

Cet exercice consiste à créer une application web permettant :
- L'insertion de messages via un formulaire.
- L'affichage des messages avec une pagination.
- La gestion des erreurs PDO pour garantir la robustesse de l'application.

## Fonctionnalités

1. **Insertion de messages** :
   - Les utilisateurs peuvent soumettre leur nom, email, numéro de téléphone et message via un formulaire.
   - Les données sont insérées dans une base de données sécurisée grâce à la fonction `addMessage()`.

2. **Affichage des messages** :
   - Les messages sont récupérés depuis la base de données et affichés par page.
   - La pagination est mise en place pour limiter le nombre de messages affichés par page.

3. **Gestion des erreurs** :
   - Les erreurs PDO sont capturées et affichées de manière sécurisée.

## Structure des fichiers

- `public/index.php` : Contrôleur frontal qui gère la logique principale, y compris la connexion à la base de données, l'insertion des messages et la pagination.
- `model/MessagesModel.php` : Contient les fonctions pour interagir avec la base de données, comme `addMessage()`, `countMessages()` et `getMessagesPagination()`.
- `view/homepage.view.php` : Vue principale pour afficher le formulaire et les messages paginés.
- `config.php` : Fichier de configuration contenant les constantes de connexion à la base de données.

## Configuration

1. Importez le fichier `datas/pdo_c2_prepa_ti2.sql` dans votre base de données MySQL.
2. Dupliquez le fichier `config.dev.php` en `config.php` et configurez les constantes pour votre environnement local.

## Pagination

La pagination est configurée via deux constantes dans `config.php` :
```php
const PAGINATION_NB = 5; // Nombre de messages par page
const PAGINATION_GET = "pg"; // Nom du paramètre GET pour la pagination