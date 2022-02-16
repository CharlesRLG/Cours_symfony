# Prise en mains de Symfony

## Création d'un premier projet

- `symfony new my_project --webapp --version=lts`
- `cd my_project`
- `symfony local:server:ca:install`
- `symfony check:security`
- `symfony local:server:start`

## Obtenir de l'aide

- `symfony help`
- `php bin/console list`
- `php bin/console help`

## Vérifier les routes

`php bin/console debug:router`

## Vérifier la connexion à la baes de données

`php bin/console dbal:run-sql "use symfony;"`

## Arborescence projet symfony

    my_project/
        bin/                <= les fichiers exécutables
        config/             <= fichiers de config YAML
        fixtures/           <= vos fichiers de données de test
        migrations/         <= vos fichiers de migration de BDD
        node_modules/       <= paquets gérés par npm
        public/             <= document root
            .htaccess       <= config pour apache
            index.php       <= le point d'entrée de votre application
        src/                <= vos fichiers PHP
        templates/          <= vos templates Twig
        tests/              <= vos tests unitaires et fonctionnels
        translations        <= vos fichiers de traduction
        var/
            cache/          <= stockage du cache
            logs/           <= stockage des logs
        vendor/             <= paquets gérés par composer
        .env                <= les codes d'accès aux services (BDD, serveur de mail, etc)
        .gitignore          <= liste des fichiers que git doit ignorer
        composer.json       <= votre liste de paquets gérés par composer
        composer.lock       <= liste des paquets (avec numéro de version exacte) gérés par composer
        package.json        <= votre liste de paquets gérés par npm
        package-lock.json   <= liste des paquets (avec numéro de version exacte) gérés par npm
        phpunit.xml.dist    <= configuration des tests unitaires et fonctionnels
        README.md           <= documentation du projet
        symfony.lock        <= liste des paquets (avec numéro de version exacte) installés avec Symfony recipes
        webpack.config.js   <= configuration de webpack

[Documentation](https://symfony.com/doc/current/page_creation.html)

[Ressouces](http://www.lsis.org/elmouelhia/courses/php/sf/coursSymfonyInstallation.pdf)
