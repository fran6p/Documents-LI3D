En préliminaire, ce document n'est que la description de ma méthode de travail pour préparer un firmware basé sur Marlin. D'autres méthodes existent, l'important est de trouver celle qui vous sied le plus.

Ce tutoriel ne s'adresse pas dans un premier temps à de purs débutants. Toutefois, en acceptant de s'y mettre et en faisant vos propres essais / erreurs (principe de tout apprentissage) la réussite peut être en vue (la courbe d'apprentissage n'est pas extrêmement pentue mais la route qui y mène n'est pas aussi droite comme l'avait judicieusement remarqué J.-P. Raffarin en son temps).

# AU COMMENCEMENT

Quand j’ai commencé à préparer mes propres firmwares pour mes imprimantes, je reproduisais la méthode décrite dans bon nombre de tutoriels (écrits ou vidéos) : je récupérais le fichier compressé de la version de Marlin sur laquelle je me basais pour faire mes modifications (platformio.ini, configuration.h et configuration_adv.h. 

![image](./images/GD/github-code-zip.jpg)

Si parmi les [exemples de modèles fournis par l’équipe du Marlin](https://github.com/MarlinFirmware/Marlin/tree/2.0.x/config) existait l’imprimante à préparer, la tâche était facilitée :

1. copier les configuration.h et configuration_adv.h (et éventuellement s’ils étaient également fournis, _Statusscreen.h et _Bootscreen.h) puis les coller dans le dossier Marlin en remplacement de ceux par défaut.
2. ensuite l’étape de compilation
  * correction des erreurs,
  * retour à l’étape 2 (compilation)
3. finalement la compilation étant réussie alors dernière étape, flasher le firmware.

Si une nouvelle version stable de Marlin était disponible, il fallait répéter les étapes précédentes depuis la récupération du Marlin compressé jusqu’au flashage.

La gestion des différences entre les fichiers de configurations pouvait être facilitée par l’utilisation de [Winmerge](https://winmerge.org/) (ou [Notepad++](https://notepad-plus-plus.org/) et l’ajout d’[un greffon](https://github.com/pnedev/compare-plugin) ou encore avec [Visual Studio Code](https://code.visualstudio.com/) ).

S’il fallait préparer des versions différentes de firmware (modèle d’imprimante différent, variation de carte mère, présence d’un ABL, type d’ABL, détection de fin de filament, …) alors il était nécessaire d’organiser les dossiers, de les nommer correctement sinon le troisième élément de la trilogie : **hardware, software … foutoir** ne tardait pas à surgir (loi de Murphy oblige).

En gros c’était pour le moins fastidieux et nécessitait une bonne organisation 😉 De plus ça finissait par occuper de la place sur l’unité de stockage.

En résumé :

![image](./images/GD/marlin-zip.jpg)

## Un outil de gestion de versions : GIT

C’est là que j’ai découvert qu’on pouvait «bénéficier» d’outils de gestion de versions : [Git](https://git-scm.com/) (son créateur n’est autre que Linus Torvald également connu pour avoir au milieu des années 1990 développé le système Linux).

Pour aller plus loin dans l’utilisation de GIT :

- https://www.mcorbin.fr/posts/2020-06-26-git-introduction/

- https://rogerdudler.github.io/git-guide/index.fr.html

- [un cours assez complet](https://www.pierre-giraud.com/git-github-apprendre-cours/)

- [la cheat sheet](https://training.github.com/downloads/fr/github-git-cheat-sheet/) [(PDF)]](https://training.github.com/downloads/fr/github-git-cheat-sheet.pdf)

Git est pratique pour travailler localement mais pour pouvoir diffuser, modifier et faire bénéficier d’autres utilisateurs de ce travail, un système distant comme [github](https://github.com/) augmente les possibilités.

Utiliser github.com (ou gitlab si Microsoft vous hérisse le poil) nécessite la création d’un compte uniquement si vous voulez créer vos propres dépôts.

[Créer son compte Github](https://github.com/pricing) (gratuit) en cliquant sur «Create a free orgaization» : 

![image](./images/GD/creer-compte-github.jpg)


