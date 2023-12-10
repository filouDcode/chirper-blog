# CHIRPER blogging app

#### Application php avec le framework LARAVEL et une architecture de type MVC (MODEL-VIEW-CONTROLLEUR)

-   Mise en marche du serveur en utilisant la ligne de commande "php artisan serve".

-   on utilise SQLite comme base de donnés très légère.

-   on utilise le framework Tailwind comme sur-couche du CSS.

-   Breeze fait parti des "starter kits" de Laravel pour prendre en charge l'enregistrement, l'authentification, la mise à jour du mot de passe, la vérification de l'email, et la confirmation du mot de passe.
-   on a créer des MIGRATIONS et des MODELS pour interagir facilement avec les tables de la base de donnés grace à l'ORM éloquent.
-   on a aussi créer des CONTROLLEURS qui prennent en charge les requêtes HTTP de l'application CHIRPER à la base de donné SQLite et retournent des réponses.
-   ces CONTROLLEURS sont utilisés pour établir deux routes:
    -   INDEX pour l'affichage des formulaires et la liste des posts.
    -   STORE pour l'enregistrement des nouveaux posts.
-   Les routes sont placés derrière des MIDDLEWARES:
    -   le MIDDLEWARE AUTH garanti que seul les utilisateurs enregistrés et authentifiés peuvent accéder à ces routes.
    -   le MIDDLEWARE VERIFIED sera utilisé uniquement si on choisi une vérification de l'identité par email.

| VERB      | URI             | ACTION  | ROUTE NAME     |
| --------- | --------------- | ------- | -------------- |
| GET       | /chirps         | index   | chirps.index   |
| POST      | /chirps         | store   | chirps.store   |
| PUT/PATCH | /chirps/{chirp} | update  | chirps.update  |
| DELETE    | /chirps/{chirp} | destroy | chirps.destroy |
