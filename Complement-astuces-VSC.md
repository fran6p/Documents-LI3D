### Compléments, astuces
A) Pour éviter des problèmes de compilation, le mieux est que le dossier Marlin soit au plus proche de la racine du disque :
Exemple: C:\Marlin plutôt que dans le dossier perso de l'utilisateur (éviter les signes diacritiques (caractères accentués) et/ou espaces dans le chemin d'accès à ce dossier)

B) J'ai une erreur du type : «VSC me demande de mettre à jour les includepath»
C'est fréquent avec VSC. La base de données (Intellisense) n'est pas toujours à jour, la plupart du temps ça n'empêche pas la compilation. Il suffit parfois d'attendre quelques minutes pour que cette erreur disparaisse sinon une fermeture de VSC puis une réouverture permet parfois de tout faire rentrer dans l'ordre.
Voir également le point D/3 plus bas

C) La compilation (rappel) :
Via Platformio IDE :
1) Dans l'onglet «PIO Home», «Open Project» : 
![image](./images/VSC/platformio-ouvrir-projet.jpg)
2) Via l'explorateur de fichiers, sélectionner le dossier contenant à la fois le fichier platformio.ini et le dossier Marlin, clic sur «Open "nom-du-dossier-sélectionné" puis confirmation en cliquant «OUI» :
![image](./images/VSC/platformio-ouvrir-projet-selection-dossier.jpg)	![image](./images/VSC/platformio-ouvrir-projet-selection-dossier-confiance.jpg)	
	
	