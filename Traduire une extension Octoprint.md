# AIDE MÉMOIRE

## Comment traduire une extension dans sa langue natale

1 Cloner l’extension pour OctoPrint et entrer dans le répertoire créé:

```
git clone https://github.com/pseudo-github-auteur/Octoprint_nom-extension.git
cd Octoprint_nom-extension
virtualenv venv
source venv/bin/activate
pip install -e . [develop]
```

Le **fichier modèle** PO se trouve sous **translations/messages.pot**.

Le fichier PO de chaque langue se trouve sous **translations/'code de langue'/LC_MESSAGES/messages.po**. 

Avant de commencer une traduction, s'assurer que le fichier modèle PO (**.pot**) est à jour et que les fichiers PO sont mis à jour en conséquence.

2 Faire d’abord un **`git pull`**, pour s'assurez que les ressources sont à jour. 

Le fichier **setup.py** fourni prend en charge quelques commandes supplémentaires pour faciliter la gestion des traductions :

`python setup.py babel_refresh`

3 Effectuer une nouvelle extraction de toutes les chaînes traduisibles depuis la source de l’extension et mettre à jour tous les fichiers PO. De là, il sera possible d'éditer la traduction dans la langue souhaitée. Si celle-ci n'est pas encore disponible, la créer via :

`python setup.py babel_new --locale=<locale>`

4 Vérifier de temps en temps la traduction en cours. Pour ce faire, compiler les traductions dans leurs équivalents MO et JS et les "regrouper" avec l’extension :

```
python setup.py babel_compile
python setup.py babel_bundle --locale=<locale>
```

5 Démarrer OctoPrint (**`octoprint serve`**), regarder les résultats de la traduction. Pour demander une locale spécifique pour l'affichage de l'interface utilisateur, ajouter le paramètre de requête **l18n** avec la locale désirée à l'URL d'OctoPrint, exemple :

http://localhost:5000/?l18n=fr

Il est également possible de sélectionner cette langue dans les paramètres "**Apparence**" (*Appearance*) d'OctoPrint ou encore dans les paramètres utilisateur de votre navigateur.

# BABEL readme

Les traductions de l'extension (plugin) sont placées dans le dossier «**translations**» au même niveau que le dossier de l’extension. Le fichier setup.py fourni supporte quelques commandes supplémentaires facilitant la gestion des traductions :

## babel_extract

> Extrait tous les messages *traduisibles* , marqués avec
> 
> - `_("...")` de Jinja ou
> -  `gettext("...")` de JavaScript)

ceci créera le fichier initial `messages.pot`.

## babel_refresh

> Relance l'extraction et met à jour le fichier `messages.pot`.

## babel_new --locale=<locale>

> Crée un nouveau dossier de traduction pour la locale `<locale>`.

## babel_compile

> Compile les traductions en fichiers `mo`, prêts à être utilisés dans OctoPrint.

## babel_pack --locale=<locale> [ --author=<author> ]

> Empaquette la traduction pour la locale `<locale>`, comme pour un pack linguistique, cette traduction est installable manuellement par les utilisateurs de l'extension. Ceci est intéressant pour les langues que **vous ne pouvez pas garantir de maintenir à jour vous-même** à chaque nouvelle version de votre extension et pour lesquelles vous devez *dépendre de contributeurs*.

Si vous voulez regrouper les traductions avec votre extension, créez un nouveau dossier **`octoprint_nom-extension/translations`**. Lorsque ce dossier existe, une commande supplémentaire devient disponible :

## babel_bundle --locale=<locale>

> Déplace la traduction de la locale `<locale>` vers **octoprint_nom-extension/translations**, en l'intégrant à votre extension. C'est intéressant avec les **langues dont vous pouvez garantir le maintien à jour par vous-même** pour chaque nouvelle version de votre extension.

