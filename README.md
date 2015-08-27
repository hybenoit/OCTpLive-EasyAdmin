
# OpenClassrooms TP Live
## Créer un Backoffice sécurisé avec Symfony, EasyAdmin et FOSUser

* **27 août 2015** :
 * Création d'une application Symfony
 * Création d'une entité "Page" pour gérer les pages de notre site
 * Installation et configuration d'[EasyAdminBundle](https://github.com/javiereguiluz/EasyAdminBundle) pour créer notre backoffice
 * Installation et configuration de [FOSUserBundle](https://github.com/FriendsOfSymfony/FOSUserBundle) pour gérer les utilisateurs de notre application, et sécuriser notre backoffice.


Comment installer cette application chez soi ?

1. Télécharger au format ZIP, ou cloner avec Git.
2. Utiliser [Composer](getcomposer.org) pour installer les bibliothèques en exécutant cette commande:

  ```bash
  composer install
  ```
3. Configurer une base de données en mettant à jour le fichier `app/config/parameters.yml` (qui sera automatiquement créé lorsque `composer` installera les dépendances.
4. Demander à [Doctrine](http://www.doctrine-project.org/) de créer notre base de données :

  ```bash
  php app/console doctrine:database:create
  ```
5. Demander à [Doctrine](http://www.doctrine-project.org/) de créer **le schéma** (les tables SQL) de notre base de données :

  ```bash
  php app/console doctrine:schema:create
  ```
6. À l'aide de [FOSUserBundle](https://github.com/FriendsOfSymfony/FOSUserBundle), créer un utilisateur administrateur pour accéder au backoffice :

  ```bash
  php app/console fos:user:create --super-admin
  # FOSUserBundle vous demandera un nom d'utilisateur, une adresse e-mail et un mot de passe
  ```
7. Accédez au backoffice à l'url `/admin/

  a. Avec votre serveur web habituel (Apache, Nginx), vous devez accéder à l'url `web/app_dev.php/admin` de votre application.

    > Rappel: le fichier `app_dev.php` active le mode développement/Debug de Symfony, qui nous permet donc d'avoir accès à beaucoup d'informations très utiles pour, justement, développer notre application.

  b. Si vous le souhaitez vous pouvez aussi utiliser le serveur intégré à Symfony avec la commande suivante, et vous pourrez utiliser l'url que Symfony va vous afficher pour accéder au serveur web :
    ```bash
    php app/console server:run
    ```
