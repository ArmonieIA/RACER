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
| RRN1 | Packed | 4,0 |  | Numéro d'enregistrement du sous-fichier SFL1 |
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
| RACECR | Format de l'écran RACEDILE pour la création d'une course |
| RACEMAJ | Format de l'écran RACEDILE pour la modification d'une course |
| RACEAFF | Format de l'écran RACEDILE pour l'affichage d'une course |
| RACEIMP | Format de l'écran RACEDILE pour l'impression d'une course |
| RACESUP | Format de l'écran RACEDILE pour la suppression d'une course |
| RACETP | Format de l'écran RACEDILE pour la sélection du type de course |
| RACEOPT | Format de l'écran RACEDILE pour la sélection de l'option |
| RACEPAG | Format de l'écran RACEDILE pour la pagination du sous-fichier |
| RACECLE | Format de l'écran RACEDILE pour la saisie clavier |
| RACEAID | Format de l'écran RACEDILE pour l'aide |
| RACEANN | Format de l'écran RACEDILE pour l'annulation |
| RACEIMPR | Format de l'écran RACEDILE pour l'impression |
| RACECREA | Format de l'écran RACEDILE pour la création |
| RACEMOD | Format de l'écran RACEDILE pour la modification |
| RACESUPP | Format de l'écran RACEDILE pour la suppression |
| RACEAFFI | Format de l'écran RACEDILE pour l'affichage |
| RACESEL | Format de l'écran RACEDILE pour la sélection |
| RACERO | Format de l'écran RACEDILE pour le défilement |
| RACENAM | Format de l'écran RACEDILE pour le changement de nom |
| RACESF | Format de l'écran RACEDILE pour la fin du sous-fichier |

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

Le programme RACERILE utilise des données fictives

RACERILE : Explication détaillée du code
=======================================

Dans ce document, nous allons expliquer en détail le code du programme RACERILE.

Déclaration des variables et des fichiers
-----------------------------------------

Le programme RACERILE commence par la déclaration de plusieurs variables et fichiers. Voici une explication détaillée de chacune d'entre elles :

### Variables

* `SflPag` et `SflMax` : ces deux constantes définissent respectivement le nombre de lignes à afficher par page dans le sous-fichier et le nombre maximum de lignes que peut contenir le sous-fichier.
* `Lstrrn` : cette variable de type packed stocke le dernier numéro d'enregistrement écrit dans le sous-fichier avant la pagination.
* `Decodage` : cette variable de type caractère stocke le code d'autorisation saisi par l'utilisateur.
* `chk` : cette variable de type entier est utilisée pour stocker le nombre d'enregistrements lus dans le fichier RACEL1.
* `i` : cette variable de type packed est utilisée comme compteur dans les boucles.
* `pos` : cette variable de type packed est utilisée pour stocker la position actuelle dans le tableau.
* `rang_race` : cette variable de type packed est utilisée pour stocker le rang de la course dans le fichier RACEL1.
* `norang_sfl` : cette variable de type packed est utilisée pour stocker le numéro d'enregistrement de la course dans le sous-fichier.
* `autorisation_modif` : cette variable de type indicateur est utilisée pour stocker l'autorisation de modification de l'utilisateur.

### Fichiers

* `RACEDILE` : ce fichier de travail station est utilisé pour afficher les enregistrements du sous-fichier.
* `RACETP1` : ce fichier disque clé est utilisé pour stocker les types de courses.
* `RACEL1` : ce fichier disque est utilisé pour stocker les enregistrements de course.

Initialisation du programme
---------------------------

Le programme commence par l'initialisation de certaines variables et la vérification de l'ouverture du fichier RACEL1. Si le fichier n'est pas ouvert, il est ouvert en mode entrée/sortie avec verrouillage exclusif.

Traitement du READC
-------------------

Le programme traite ensuite le READC du sous-fichier. Le READC est une opération qui lit toutes les lignes modifiées du sous-fichier. Dans RACERILE, le READC est utilisé pour traiter les options saisies par l'utilisateur.

Les options disponibles sont les suivantes :

* `Afficher` : cette option permet d'afficher les détails de la course sélectionnée.
* `Kill` : cette option permet de supprimer la course sélectionnée.
* `Modification` : cette option permet de modifier la course sélectionnée.
* `Opt_imprimer` : cette option permet d'imprimer la course sélectionnée.

Pour chaque option, le programme appelle une procédure dédiée.

Traitement de l'option 8=Imprimer
---------------------------------

La procédure `Imprimere` est appelée lorsque l'utilisateur sélectionne l'option 8=Imprimer. Cette procédure appelle le programme d'impression `RACEPRINT` en passant le numéro de course à imprimer en paramètre.

Traitement de l'option 2=Modification
-------------------------------------

La procédure `Recencere` est appelée lorsque l'utilisateur sélectionne l'option 2=Modification. Cette procédure permet de modifier les informations de la course sélectionnée.

Tout d'abord, les informations de la course sélectionnée sont transférées dans le format écran `FMT2`. Ensuite, le programme entre dans une boucle infinie qui affiche le format écran `FMT2` et attend que l'utilisateur saisisse une option.

Les options disponibles sont les suivantes :

* `Sortie` : cette option permet de quitter la procédure de modification.
* `Annuler` : cette option permet d'annuler les modifications apportées à la course sélectionnée.

Si l'utilisateur saisit l'option `Confirmer`, le programme vérifie si le mot de passe saisi est correct en appelant la fonction `ok_modif`. Si le mot de passe est correct, les informations modifiées sont enregistrées dans le fichier RACEL1.

Traitement de l'option 5=Afficher
---------------------------------

La procédure `Ostendere` est appelée lorsque l'utilisateur sélectionne l'option 5=Afficher. Cette procédure affiche les détails de la course sélectionnée dans le format écran `FMT5`.

Traitement de l'option 4=Supprimer
---------------------------------

La procédure `Occidere` est appelée lorsque l'utilisateur sélectionne l'option 4=Supprimer. Cette procédure permet de supprimer la course sélectionnée du fichier RACEL1.

Tout d'abord, les informations de la course sélectionnée sont transférées dans le format écran `FMT4`. Ensuite, le programme entre dans une boucle infinie qui affiche le format écran `FMT4` et attend que l'utilisateur saisisse une option.

Les options disponibles sont les suivantes :

* `Sortie` : cette option permet de quitter la procédure de suppression.
* `Annuler` : cette option permet d'annuler la suppression de la course sélectionnée.

Si l'utilisateur saisit l'option `Confirmer`, le programme supprime la course sélectionnée du fichier RACEL1.

Traitement du F6=Création
-------------------------

La procédure `Creaturae` est appelée lorsque l'utilisateur appuie sur la touche F6 pour créer une nouvelle course. Cette procédure permet de saisir les informations de la nouvelle course dans le format écran `FMT6`.

Tout d'abord, les champs du format écran `FMT6` sont initialisés à blanc. Ensuite, le programme entre dans une boucle infinie qui affiche le format écran `FMT6` et attend que l'utilisateur saisisse une option.

Les options disponibles sont les suivantes :

* `Annuler` : cette option permet d'annuler la création de la nouvelle course.
* `Sortie` : cette option permet de quitter la procédure de création.
* `Aide` : cette option permet d'afficher un écran d'aide pour la saisie des informations de la nouvelle course.

Si l'utilisateur saisit l'option `Confirmer`, le programme vérifie si les informations saisies sont valides. Si les informations sont valides, la nouvelle course est ajoutée au fichier RACEL1.

Conclusion
----------

Dans ce document, nous avons expliqué en détail le code du programme RACERILE. Nous avons vu comment les différentes procédures sont appelées en fonction des options saisies par l'utilisateur, et comment les informations de course sont gérées dans le fichier RACEL1. Nous espérons que cette explication détaillée vous aidera à mieux comprendre le fonctionnement du programme RACERILE.
