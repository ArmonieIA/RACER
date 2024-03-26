RACERILE - Programme de gestion de courses
=========================================

Le programme RACERILE est un programme de gestion de courses écrit en RPG (Rational Program Generator) FREE et destiné à être exécuté sur un système IBM i. Il permet de gérer des courses de marathon et de les afficher dans un sous-fichier.

Généralités
-----------

### Dépendances

Le programme RACERILE dépend des éléments suivants :

* Bibliothèque RACES
* Fichiers RACEDILE, RACETP1 et RACEL1
* Programme d'impression RACEPRINT
* Modules VIMOIS, DIFFJOURS, LOOSER et WINNER

### Compilation

Le programme RACERILE doit être compilé avec les options suivantes :

* CTL-OPT option(\*SRCSTMT) DFTACTGRP(\*NO)
* BNDDIR('RACERDIR')

Variables
---------

Le programme RACERILE utilise les variables suivantes :

| Nom | Type | Longueur | Décimales | Description |
| --- | --- | --- | --- | --- |
| SFL1 | SFILE |  |  | Sous-fichier de la liste des courses |
| SFL2 | SFILE |  |  | Sous-fichier de la liste des types de courses |
| RRN1 | Packed | 4,0 |  | Numéro d'enregistrement du sous-fichier SFL1 |
| RRN2 | Packed | 4,0 |  | Numéro d'enregistrement du sous-fichier SFL2 |
| INFO |  |  |  | Informations sur la saisie clavier |
| CFKEY | Char | 1 |  | Touche fonction saisie clavier |
| AUTORISATION | Char | 1 |  | Indicateur d'autorisation de modification |
| CODE\_LDA | Char | 10 |  | Code d'autorisation de modification |
| DECODAGE | Char | 10 |  | Code d'autorisation saisi par l'utilisateur |
| NORACE | Packed | 5,0 |  | Numéro de la course |
| DTRACE | Date |  |  | Date de la course |
| TPRACE | Char | 3 |  | Type de la course |
| NMRACE | Char | 30 |  | Nom de la course |
| GRRACE | Char | 1 |  | Genre de la course |
| DSRACE | Packed | 3,1 |  | Distance de la course |
| T1RACE | Char | 1 |  | Temps de la course |
| P3RACE | Packed | 4,0 |  | Position de la course |
| AVRACE | Packed | 4,2 |  | Vitesse moyenne de la course |
| FORME | Char | 3 |  | Forme du coureur |
| VAINQUEUR | Char | 10 |  | Nom du vainqueur de la course |
| PERDANT | Char | 10 |  | Nom du perdant de la course |
| LIBELLE | Char | 10 |  | Libellé du type de course |
| TYPE | Char | 3 |  | Code du type de course |
| ZOPT | Char | 1 |  | Option de sélection du type de course |
| OPT | Char | 1 |  | Option de sélection de la course |
| Z\_NORACE | Packed | 5,0 |  | Numéro de la course à sélectionner |
| Z\_TYP | Char | 3 |  | Type de la course à sélectionner |

Zones
-----

Le programme RACERILE utilise les zones suivantes :

| Nom | Type | Longueur | Décimales | Description |
| --- | --- | --- | --- | --- |
| SFLPAG | Const |  |  | Nombre de lignes à afficher par page dans le sous-fichier |
| SFLMAX | Const |  |  | Nombre maximum de lignes dans le sous-fichier |
| CHK | Int | 10 |  | Variable de vérification |
| I | Packed | 4,0 |  | Compteur |
| POS | Packed | 4,0 |  | Position |
| RANG\_RACE | Packed | 5,0 |  | Rang de la course |
| NORANG\_SFL | Packed | 4,0 |  | Numéro d'enregistrement du sous-fichier |
| AUTORISATION\_MODIF | Ind |  |  | Indicateur d'autorisation de modification |
| SORTIE\_TPCHOIX | Ind |  |  | Indicateur de sortie du sous-fichier des types de courses |
| CODE1 | Char | 26 |  | Table de correspondance des caractères |
| CODE2 | Char | 26 |  | Table de correspondance des caractères |
| PINDICATORS | Pointer |  |  | Pointeur sur les indicateurs de l'écran |
| DSPIND | Based |  |  | Structure des indicateurs de l'écran |
| SORTIE | Ind |  |  | Indicateur de sortie de l'écran |
| AIDE | Ind |  |  | Indicateur d'aide de l'écran |
| CREATION | Ind |  |  | Indicateur de création de l'écran |
| IMPRESSION | Ind |  |  | Indicateur d'impression de l'écran |
| ANNULER | Ind |  |  | Indicateur d'annulation de l'écran |
| CONFIRMER | Ind |  |  | Indicateur de confirmation de l'écran |
| SFL\_CLR | Ind |  |  | Indicateur de nettoyage du sous-fichier |
| SFL\_DSP | Ind |  |  | Indicateur d'affichage du sous-fichier |
| ROLL | Ind |  |  | Indicateur de défilement du sous-fichier |
| NAME\_CHANGE | Ind |  |  | Indicateur de changement de nom de l'écran |
| SFL\_END | Ind |  |  | Indicateur de fin du sous-fichier |
| ODBF | DS |  |  | Structure pour le OVRDBF |
| COMMANDE | Char | 80 |  | Commande à exécuter |
| QCMDEXC | PR |  |  | Prototype du programme QCMDEXC |
| F\_SIX | Const |  |  | Valeur hexadécimale de la touche F6 |
| SELECTION | Const |  |  | Valeur de l'option de sélection |
| AFFICHER | Const |  |  | Valeur de l'option d'affichage |
| KILL | Const |  |  | Valeur de l'option de suppression |
| MODIFICATION | Const |  |  | Valeur de l'option de modification |
| OPTIM | Const |  |  | Valeur de l'option d'impression |

Fonctions
----------

Le programme RACERILE utilise les fonctions suivantes :

| Nom | Description |
| --- | --- |
| INZSR | Initialisation du programme |
| BUILD\_SUBF | Construction du sous-fichier |
| DISPLAY\_RACE | Affichage des informations sur une course |
| DELETE\_RACE | Suppression d'une course |
| UPDATE\_RACE | Modification d'une course |
| ADD\_RACE | Ajout d'une course |
| DIFFJOURS | Calcul de la différence entre deux dates |
| VISMOIS | Calcul du mois visé pour une course |
| LOOSER | Détermination du perdant d'une course |
| WINNER | Détermination du vainqueur d'une course |
| QCMDEXC | Exécution d'une commande système |
| TRT\_READC | Traitement de la touche F12 |
| TRT\_CHOIXTP | Traitement de la sélection du type de course |
| TRT\_CHOIXOPT | Traitement de la sélection de l'option |
| TRT\_PAGINATION | Traitement de la pagination du sous-fichier |
| TRT\_CLE | Traitement de la saisie clavier |
| TRT\_AIDE | Traitement de la touche d'aide |
| TRT\_ANNULER | Traitement de la touche d'annulation |
| TRT\_IMPRESSION | Traitement de la touche d'impression |
| TRT\_CREATION | Traitement de la touche de création |
| TRT\_MODIFICATION | Traitement de la touche de modification |
| TRT\_SUPPRESSION | Traitement de la touche de suppression |
| TRT\_AFFICHAGE | Traitement de la touche d'affichage |
| TRT\_SELECTION | Traitement de la touche de sélection |
| TRT\_ROLL | Traitement de la touche de défilement |
| TRT\_NAME\_CHANGE | Traitement de la touche de changement de nom |
| TRT\_SFL\_END | Traitement de la fin du sous-fichier |

Écrans
-------

Le programme RACERILE utilise les écrans suivants :

| Nom | Description |
| --- | --- |
| RACEDILE | Écran principal du programme |
| RACECR | Écran de création d'une course |
| RACEMAJ | Écran de modification d'une course |
| RACEAFF | Écran d'affichage d'une course |
| RACEIMP | Écran d'impression d'une course |
| RACESUP | Écran de suppression d'une course |
| RACETP | Écran de sélection du type de course |
| RACEOPT | Écran de sélection de l'option |
| RACEPAG | Écran de pagination du sous-fichier |
| RACECLE | Écran de saisie clavier |
| RACEAID | Écran d'aide |
| RACEANN | Écran d'annulation |
| RACEIMPR | Écran d'impression |
| RACECREA | Écran de création |
| RACEMOD | Écran de modification |
| RACESUPP | Écran de suppression |
| RACEAFFI | Écran d'affichage |
| RACESEL | Écran de sélection |
| RACERO | Écran de défilement |
| RACENAM | Écran de changement de nom |
| RACESF | Écran de fin du sous-fichier |

Fichiers
--------

Le programme RACERILE utilise les fichiers suivants :

| Nom | Description |
| --- | --- |
| RACEDILE | Fichier de description du sous-fichier |
| RACETP1 | Fichier de description des types de courses |
| RACEL1 | Fichier de description des courses |

Remarques
---------

Le programme RACERILE est un programme de démonstration et ne doit pas être utilisé en production sans modification. Il est recommandé de tester le programme dans un environnement de test avant de l'utiliser en production.

Le programme RACERILE utilise des données fictives et ne doit pas être utilisé pour gérer des données réelles sans modification.

Le programme RACERILE utilise des fonctions et des procédures externes qui doivent être présentes dans la bibliothèque RACES. Il est recommandé de vérifier la présence de ces éléments avant d'exécuter le programme.

Le programme RACERILE utilise des écrans qui doivent être présents dans la bibliothèque QUSRSYS. Il est recommandé de vérifier la présence de ces écrans avant d'exécuter le programme.

Le programme RACERILE utilise des données stockées dans des data areas. Il est recommandé de vérifier la présence de ces data areas avant d'exécuter le programme.

Le programme RACERILE utilise des commandes système qui nécessitent des autorisations spécifiques. Il est recommandé de vérifier les autorisations de l'utilisateur avant d'exécuter le programme.
