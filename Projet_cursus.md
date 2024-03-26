
# Projet CURSUS

Le projet CURSUS est une application de gestion de courses de marathon développée en RPGLE sur IBM i. Le projet est divisé en plusieurs programmes, modules et fichiers qui travaillent ensemble pour fournir une interface utilisateur et gérer les données de course.

## Programmes

### RACERILE

RACERILE est le programme principal du projet CURSUS. Il fournit une interface utilisateur pour afficher, ajouter, modifier et supprimer des enregistrements de course. Le programme utilise deux sous-fichiers pour afficher les données de course et les options de sélection. Les utilisateurs peuvent trier et filtrer les données de course en utilisant différentes options de sélection.

### RACEPRINT

RACEPRINT est un programme d'impression qui peut être appelé à partir de RACERILE pour imprimer des rapports de course. Le programme utilise des données de course à partir du fichier RACEL1 pour générer des rapports.

### Modules

Le projet CURSUS comprend également plusieurs modules qui fournissent des fonctionnalités spécifiques.

#### VIMOIS

Le module VIMOIS calcule le mois visé pour une course en fonction de la date de la course et de la fréquence de la course.

#### DIFFJOURS

Le module DIFFJOURS calcule la différence entre deux dates en nombre de jours.

#### LOOSER et WINNER

Les modules LOOSER et WINNER sont utilisés pour déterminer les perdants et les gagnants d'une course.

## Fichiers

Le projet CURSUS utilise plusieurs fichiers pour stocker les données de course.

### RACEL1

RACEL1 est le fichier principal de données de course. Il contient des enregistrements pour chaque course, y compris le numéro de course, la date, le type, le nom, la catégorie, la distance, le temps, la position, la moyenne, la forme et le vainqueur.

### RACEDILE

RACEDILE est un fichier de sous-fichier utilisé par RACERILE pour afficher les données de course.

### RACETP1

RACETP1 est un fichier de données de type de course. Il contient des enregistrements pour chaque type de course, y compris le code de type de course et la description.

## Écrans

Le projet CURSUS utilise plusieurs écrans pour fournir une interface utilisateur.

### RACEDILE

L'écran RACEDILE est utilisé pour afficher les données de course dans un format de sous-fichier. Les utilisateurs peuvent trier et filtrer les données de course en utilisant différentes options de sélection.

### FMTOVRDBF

L'écran FMTOVRDBF est utilisé pour changer la bibliothèque et le nom du fichier de données de course.

### FMTCODOTO

L'écran FMTCODOTO est utilisé pour saisir un code d'autorisation pour accéder aux fonctionnalités de modification et de suppression de course.

### FMT5 et FMT4

Les écrans FMT5 et FMT4 sont utilisés pour afficher les détails d'une course sélectionnée dans RACEDILE. Les utilisateurs peuvent modifier ou supprimer une course en utilisant ces écrans.

## Conclusion

Le projet CURSUS est une application de gestion de course complète développée en RPGLE sur IBM i. Le projet utilise plusieurs programmes, modules et fichiers pour fournir une interface utilisateur et gérer les données de course. Les utilisateurs peuvent afficher, ajouter, modifier et supprimer des enregistrements de course, ainsi qu'imprimer des rapports de course. Le projet CURSUS est un excellent exemple d'application de gestion de données développée en RPGLE sur IBM i.
