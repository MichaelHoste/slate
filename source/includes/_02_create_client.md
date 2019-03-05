# Create a client

Translation.io was designed to help developers localizing and translating
ever-changing applications. To make the whole experience smoother, specific
clients were created and officially supported (see below). Unsupported clients
were also created by external teams for other frameworks or languages.

This public documented API will simplify the process of creating new clients.

## Workflow

Between 1 and 3 API calls will be needed for your client to be complete,
depending on what are your needs:

(sync peut être suffisant si rien n'est traduit. Init est utile s'il faut un truc traduit
et source_edits pour l'édition de clés => permettre de syncer un projet vide!?)

### Sync

Framework -----> Source text ----> Translation.io (create new segments + pretranslate if needed) -----> Source + Translated text -------> Framework

Le truc principal est la synchronisation qui consiste à envoyer tous les segments
de la branche courante de l'application (sans les traductions !) et récupérer toutes les
traductions de Translation.io (si le segment n'existe pas sur Translation.io,
il sera créé)

Les traductions reçues seront, quant à elles, insérées au sein de l'application.

LIEN VERS SEGMENTS/SYNC

------

### Init

Framework -----> Source + Translated text ----> Translation.io (create new segments with translations if any) -----> Source + Translated text -------> Framework


Si l'application est déjà partiellement traduite avant de la synchroniser avec Translation.io,
il faudra alors utiliser "INIT" qui permettra d'insérer une fois pour toutes toutes les traductions.

LIEN VERS SEGMENTS/INIT

---------

### Source Edits

Only 2 API calls are needed to create a client for a new framework. Or 3 if
you want to be able to edit the source text in the translation interface
(for key/value segments).

LIEN VERS SOURCE_EDITS/INDEX

## Existing clients

These implementations were usually started by contributors for their own projects.
Some of them are officially supported by [Translation.io](https://translation.io)
and some are not yet supported. However, they are quite well documented.

Thanks a lot to these contributors for their hard work!

### Ruby on Rails (Ruby)

Officially Supported on [https://translation.io/rails](https://translation.io/rails)

 * GitHub: https://github.com/translation/rails
 * RubyGems: https://rubygems.org/gems/translation/

Credits: [@aurels](https://github.com/aurels), [@michaelhoste](https://github.com/michaelhoste)

### Laravel (PHP)

Officially Supported on [https://translation.io/laravel](https://translation.io/laravel)

 * GitHub: https://github.com/translation/laravel
 * Packagist: https://packagist.org/packages/tio/laravel

Credits: [@armandsar](https://github.com/armandsar), [@michaelhoste](https://github.com/michaelhoste)

### React and React-Intl (JavaScript)

 * GitHub: https://github.com/deecewan/translation-io
 * NPM: https://www.npmjs.com/package/translation-io

Credits: [@deecewan](https://github.com/deecewan)

