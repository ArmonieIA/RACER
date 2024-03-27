## Fonctions principales

### trt_readc()

La fonction `trt_readc()` traite les actions de l'utilisateur sur le sous-fichier. Elle lit les enregistrements du sous-fichier et exécute les actions appropriées en fonction de l'option sélectionnée par l'utilisateur.

#### Entrées
- Aucune

#### Sorties
- Aucune

#### Description
La fonction `trt_readc()` lit les enregistrements du sous-fichier jusqu'à ce qu'elle atteigne la fin du fichier. Pour chaque enregistrement, elle vérifie l'option sélectionnée par l'utilisateur et exécute les actions suivantes :

- Si l'option est `AFFICHER`, la fonction `affiche()` est appelée pour afficher les détails de l'enregistrement.
- Si l'option est `SUPPRIMER`, la fonction `suppression()` est appelée pour supprimer l'enregistrement.
- Si l'option est `MODIFIER`, la fonction `modification()` est appelée pour modifier l'enregistrement.

#### Exemple d'utilisation
Supposons que l'utilisateur a sélectionné l'option `AFFICHER` pour afficher les détails de l'enregistrement avec le code de produit `12345`. La fonction `trt_readc()` lit les enregistrements du sous-fichier jusqu'à ce qu'elle trouve l'enregistrement avec le code de produit `12345`. Elle appelle alors la fonction `affiche()` pour afficher les détails de l'enregistrement.

#### Code
```sql
dcl-proc trt_readc;
  Readc SFL1;
  dow not %eof;
    select;
      when opt = AFFICHER;  // option 5 Afficher
        affiche();
      when opt = SUPPRIMER; // option 4 Supprimer
        suppression();
      when opt = MODIFIER;  // option 2 Modifier
        modification();
    endsl;
    Readc SFL1;
  enddo;
end-proc;
