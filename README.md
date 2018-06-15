# Documentation

 ## Pseudos attributs ::after & ::before;

les pseudos attributs 'before' et 'after' sont essentiellement utilisés pour ajouter des
élèments à votre DOM pour décorer sans que cele ait un impact sur le
référencement ou votre HTML.
    
 #### Que fait un pseudo-élément ?
 
Il fait exactement ce que son nom implique : il crée un élément factice et l'insère avant ou après le contenu de l'élément que vous       avez ciblé.
Exemple :
```
   #example:before {
   content: "";
   display: block;
   width: 100px;
   height: 100px;
   }
```

La propriété content est utilisée avec les pseudo-éléments ::before et ::after afin de générer le contenu d'un élément.
Les objets insérés via la propriété content sont des éléments remplacés anonymes.


## Box sizing

La propriété box-sizing est utilisée pour modifier le modèle de boîte CSS par défaut qui est utilisé pour calculer la largeur et la hauteur des éléments.


Valeurs avec un mot-clé 
```
   box-sizing: content-box;
   box-sizing: border-box;
```
Valeurs globales 
```
   box-sizing: inherit;
   box-sizing: initial;
   box-sizing: unset;
```

CSS Box-sizing suit le modèle de boîte dans la mesure où il intègre la surface du contenu d'abord, puis le padding, puis la bordure, Mais il n'inclut pas les marges.
Cependant, nous devons définir la largeur ou la hauteur de notre élément, qui est maintenant la largeur ou la hauteur de l'élément dans son ensemble. Donc au lieu d'ajouter le padding et la bordure, vous devez les soustraire pour obtenir les dimensions du contenu :

Largeur = la largeur totale de l'élément
et Largeur - padding - bordure = largeur du contenu


## Attributs universels 

  - **Accesskey**
      ( L'attribut universel accesskey fournit une indication afin de générer un raccourci clavier
      pour l'élément courant. La valeur de cet attribut est une liste de caractères (un caractère étant ici
      un seul point de code Unicode) séparés par des espaces. Le navigateur utilisera le premier caractère
      qui est disponible selon la disposition du clavier utilisée. La combinaison de touches utilisée pour
      le raccourci clavier dépend du navigateur et du système d'exploitation utilisés.)
  - **Autocapitalize**
    (Cet attribut contrôle la façon dont le texte saisi est automatiquement converti en majuscules. Les valeurs autorisées pour cet     attribut sont :
    off ou none : il n'y pas de convertion en majuscules réalisée.
    on ou sentences : la première lettre de chaque phrase est écrite en majuscule par défaut. Les autres lettres sont en minuscules par défaut.
    words : la première lettre de chaque mot est écrite en majuscule par défaut, les autres lettres sont en minuscules par défaut.
    characters : toutes les lettres sont écrites en majuscules par défaut.)
  - **Class**
      (Une liste de classes, séparées par des espaces, qui permettent de catégoriser l'élément.
      Les classes permettent au CSS et à JavaScript de manipuler des éléments spécifiques grâce à
      des sélecteurs de classe (pour CSS) ou grâce à des fonctions telles que Document.getElementsByClassName() (pour JavaScript). )
  - **Contenteditable**
      (Un attribut à valeur contrainte qui indique si l'élément peut être édité par l'utilisateur.
      Si c'est le cas, le navigateur modifie l'interface utilisateur afin de permettre l'édition.
      Les valeur autorisées pour cet attribut sont :true ou la chaîne vide : ces valeurs indiquent que l'élément doit pouvoir être édité
      false qui indique que l'élément ne doit pas pouvoir être édité.)
  - **Contextmenu**
      (La valeur de cet attribut correspond à la valeur de l'attribut id d'un élément <menu> qui doit être utilisé comme menu contextuel par cet élément.)

D'autres attributs universels : https://developer.mozilla.org/fr/docs/Web/HTML/Attributs_universels

## REM, EM, %, VW Sizing

__%__
__VW(idth) /VH(eight)__

* Unités relative à la taille de votre écran (peu importe le device).
* Attention au VH et à son contenu. 100vh === 100vh quoi qu'il arrive.
* Ses proportions seront égaleme,t gardées quand l'utilisateur zoomera dans votre page.

**EM**

* Relative à la taille de son parent direct.

```CSS

.cover{
   font-size: 100%;    /* 100% = 16px  */
  /*  1em = 16px / .8em =/ 16px */
  &__mainTitle{
    font-size: .8em;
  }
}

```

**REM**

* LE REM est basé sur la taille de la racine (soit la balise <html>) qui, par défaut a une valeur
de 16px. Afin d'éviter tout calcul il est nécessaire de l'ecraser donnant une base de 10px soit 62.5%.

* Le REM est intéressant à utiliser si les média-queries employées sont en rem également.
Cela vous permettra de garder les proportions égales lorsqu'on va redimensionner la page.

* Ses proportions seront également gardées quand l'utilistateur zoomera dans votre page.



```css
html {
  font-size: 62.5%;
}

```

## CSS Next

**http://cssnext.io/**

PostCSS-cssnext est un plugin PostCSS qui vous aide à utiliser la dernière syntaxe CSS aujourd'hui. Il transforme les nouvelles spécifications CSS en CSS plus compatibles, de sorte que vous n'avez pas besoin d'attendre la prise en charge du navigateur.

## Comment compiler en CSS ?
Un préprocesseur est un méta-langage qui nécessite d’être compilé en CSS “normal” pour être interprété par un navigateur. Il est donc nécessaire d’introduire une étape de compilation, où une moulinette va se charger de la transformation Sass en CSS.

Cette étape peut être réalisée de différentes manières, dont voici les plus courantes :

-Une application graphique : Prepros, Codekit, Koala, Scout, etc.
-Un plugin éditeur : Sass autocompile (Atom), Sass Sublime (Sublime Text), Brackets Sass (Brackets), etc.
-À l’aide de task runners : Gulp, Grunt, Brunch, etc.
-Directement en ligne : Sassmeister, Pleeease, Lesstester, etc.s

**Extensions de fichiers Sass**
Un fichier Sass aura pour extension .scss (anciennement .sass dont la syntaxe était plus éloignée de CSS). en voici quelques exemples :

```
styles.scss
kiwi.scss
```
Sera compilé en :
```
styles.css
kiwi.css
```
**Variables**

Une variable Sass est composée d’un préfixe $, le nom de la variable, le séparateur : et la valeur de la variable. Tout ceci est très proche du langage CSS et ne devrait pas vous choquer.

Ainsi, les variables suivantes :
```
$unicorn: yellow;
$kitten: pink;
```

Employées dans les règles suivantes :
```
div {
  color: $unicorn;
}
p {
  background: $kitten;
}
```

Seront compilées ainsi :
```
div {
  color: yellow;
}
p {
  background: pink;
}
```
