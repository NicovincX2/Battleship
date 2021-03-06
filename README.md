<p align="center">
  <img src="http://icons.iconarchive.com/icons/everaldo/crystal-clear/128/App-battleship-boat-icon.png" width=72 height=72>

  <h1 align="center">Battleship</h1>

  <p align="center">
    Jeu de bataille navale développé en Python avec l'interface graphique Tkinter (en cours d'intégration).
  </p>
</p>

## Status
[![Join the Battleship-python chat](https://young-island-83658.herokuapp.com/badge.svg)](https://young-island-83658.herokuapp.com/)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/2cd632423fed43b3be7294659e4ab71e)](https://www.codacy.com/app/NicovincX2/Battleship?utm_source=github.com&utm_medium=referral&utm_content=NicovincX2/Battleship&utm_campaign=badger)
[![Code Issues](https://www.quantifiedcode.com/api/v1/project/471352311f004f6cba93c5be69076df7/badge.svg)](https://www.quantifiedcode.com/app/project/471352311f004f6cba93c5be69076df7)

## Installation
Pour installer les modules utilisés dans le programme. 
```
pip install -r requirements.txt
```  
Si les modules nécessaires ne sont pas installés, le lancement de ```naval_battle.py``` les installera auomatiquement via ```pip```.  
Si ```pip``` n'est pas reconnu que l'erreur renvoyée est de type: ```'python pip' is not recognized as an internal or external command, operable program or batch file.```.  
Voir [pip is not recognized](https://github.com/Langoor2/PokemonGo-Map-FAQ/wiki/%27python---pip%27-is-not-recognized-as-an-internal-or-external-command,-operable-program-or-batch-file) pour ajouter le répertoire ```Scripts``` de votre répertoire Python au ```path```.

## Description
Jeu de société dans lequel deux joueurs tentent de couler tous les navires adverses.
Le gagnant est celui qui parvient à torpiller complètement les navires de l'adversaire avant que tous les siens ne le soient.

Chaque joueur possède les mêmes navires, 5 tailles de navires sont disponibles:
 - Porte-avions (5 cases)
 - Croiseur (4 cases)
 - Contre-torpilleurs (3 cases)
 - Sous-marin (3 cases)
 - Torpilleur (2 cases)  

Leur nombre dépend de la taille du plateau. Ce dernier peut aller de 10 à 26 colonnes ou lignes.
La grille est numérotée de A à Z verticalement et de 0 à 26 horizontalement selon la configuration choisie.
Les coordonnées d'une case sont définies par la lettre de la ligne (A-...-Z) puis par le numéro de la colonne (0-...-26).
Un pion blanc signale l'emplacement de nos tir dans l'eau et un pion rouge l'emplacement d'un tir réussi.  

## Spécifications des interfaces.
Fichier de configuration par défaut: ```configs.txt```

### COMMAND LINE : inline
```
usage: naval_battle.py [-h] [--version] [-ec ligne] [-cf filename] [-m mode] [-n N]
                  {new-config} ...

Jeu de bataille navale

positional arguments:
  {new-config}
    new-config          Création d'une nouvelle configuration. Entrer le
                        nombre de colonnes, suivi du nombre de ligne et de la
                        liste des bateaux.

optional arguments:
  -h, --help            show this help message and exit
  --version             show program's version number and exit

Configuration:
  -ec ligne, --exist-config ligne
                        Choix d'une configuration existante dans la liste des
                        configurations. Entrer la ligne voulue.
  -cf filename, --conf-file filename
                        Fichier contenant les configurations.
  -m mode, --mode mode  Mode de jeu. 1. PVP/ 2. PVE/ 3. IA vs IA.
  -n N, --number N      Nombre de parties IA vs IA.
```

#### Exemple
``` 
naval_battle.py -cf configs -ec 6 -m 3 -n 2
```
 * Fichier de configuration: configs.txt, 
 * Configuration N° 6, 
 * Mode: IA vs IA,
 * Nombre de parties: 2.

### COMMAND LINE : input
Choix de la configuration :
 1. Créer un nouveau fichier,
    * Entrer le nombre de colones (10-26):
    * Entrer le nombre de lignes (10-26):
    * Entrer à la suite les nombres de bateaux de tailles 2,3,4 et 5 séparés par une virgule :
 2. Utiliser un fichier existant,
    * Entrer le nombre correspondant à la ligne de la configuration que vous voulez entrer :

Choix du mode jeux (PVP, PVE):
 1. Joueur contre joueur,
 2. Joueur contre IA,

#### Création d'un joueur.
Enter le nom du joueur (20 caractères maximum):  
Choix du mode de génération de l'emplacement des bateaux pour ```joueur.name```
 1. Génération par le joueur,
    * Entrer la taille de votre bateau (1-```taillemax```):
    * Entrer la première case de votre bateau :
    * Entrer la direction vers laquelle se dirige votre navire (N/S/E/O) :
 2. Génération aléatoire,
    1. Autoriser les bateaux côtes à côtes,
    2. Ne pas autoriser les bateaux côtes à côtes,

> Même chose pour le joueur 2

Enter le nom de l'IA (20 caractères maximum):

Choisissez qui commence la partie (1, 2, A):  
Entrer la case cible de votre tir :

### TK INTERFACE:
