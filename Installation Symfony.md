
# Installation et configuration de Symfony


## Pré-requis
- PHP installé avec les modules Ctype, iconv, JSON, PCRE, Session, SimpleXML, Tokenizer ; pour vérifier : <br>
    `php -v`<br>
    `php -m`<br>
    `php --ini`
- COMPOSER ; pour vérifier :<br>
    `composer -V`
- GIT avec user.email et user.name configurés ; pour vérifier :<br>
    `git --version`<br>
    `git config --global --list`
- Symfony Cli (voir ci-dessous pour l'installation)<br>
    `symfony -V`<br>
- Configuration PHP optimale (voir ci-dessous si nécessaire)<br>
    `symfony check:requirements`<br>
     Vérifer la configuration de php.ini ; remplacer `` `php --ini` `` par le chemin complet de php.ini<br>
    ``php -e -c `php --ini` -r "echo 'OK';"``


## Installation de Symfony Cli

### Windows

```bat
echo Télécharger Symfony Cli 64-bits depuis https://symfony.com/download
rem Lien direct : https://github.com/symfony/cli/releases/download/v4.26.9/symfony_windows_amd64.exe
rem Aller dans le dossier symfony_windows_amd64.exe
rem Création du dossier Symfony
mkdir -p "%APPDATA%\Symfony"
IF EXIST symfony_windows_amd64.exe (
  move symfony_windows_amd64.exe "%APPDATA%\Symfony\symfony.exe"
  echo Ajouter le dossier "%APPDATA%\Symfony" dans la variable d'environnement PATH
  pause
  echo Veuillez redémarrer le processus explorer.exe et fermer cette fenêtre
  echo et pour tester exécuter symfony -V
  pause
  symfony -V
)
ELSE (
  echo Veuillez vous placer dans le dossier contenant symfony_windows_amd64.exe
  echo Exemple : 
  echo   cd "%USERPROFILE%\Downloads"
)
```

### Linux

`wget https://get.symfony.com/cli/installer -O - | bash`

### MacOS

`curl -sS https://get.symfony.com/cli/installer | bash`


## Configuration PHP optimale


### Windows

Téléchargement de APCU

```bat
echo Vérification de la configuration de php
php -er "phpinfo();" | findstr /I  "thread architecture"
echo Télécharger APCU : https://pecl.php.net/package/APCu/
echo Extraire le fichier dll dans le bon dossier par exemple c:\xampp\php\ext
```

Configuration php.ini - Relancher XAMPP si nécessaire

```ini
; augmentation de la taille du cache
realpath_cache_size=8M

; post_max_size supérieur à upload_max_filesize
post_max_size=41M
upload_max_filesize=40M

; Activer intl
extension=intl

; configurer le fichier php.ini
; Charger et activer OPCACHE
zend_extension=opcache
opcache.enable=1
opcache.enable_cli=On

; Charger et activer APCU
[apcu]
extension=php_apcu.dll
apc.enabled=1
apc.shm_size=32M
apc.ttl=7200
apc.enable_cli=1
apc.serializer=php
```
