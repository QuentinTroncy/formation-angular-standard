https://fr.wikipedia.org/wiki/ECMAScript

# ECMAScript
Standard (ensemble de normes) pour les langages de programmation de type script (JavaScript, ActionScript ...)

# Versions
Version  | Description
---      | ---
1997 ECMAScript 1 | 1er édition
1998 ECMAScript 2 | Modification et/ou amélioration mineures
1999 ECMAScript 3 | RegEx et try/catch
ECMAScript 4	  | Annulée
2009 ECMAScript 5 | "strict mode" et support JSON.
2015 ECMAScript 6 | Classes et modules.
2016 ECMAScript 7 | Exponential operator (**), Array.prototype.includes

# Support navigateurs
Version  | Support
---      | ---
ECMAScript 3 | supporté par tout les navigateurs
ECMAScript 5 | supporté par tout les navigateurs modernes
ECMAScript 6 | supporté partiellement par les navigateurs
ECMAScript 7 | supporté très faiblement par les navigateurs

# Implementations navigateurs
Version  | Navigateur
---      | ---
6 | Chrome (support partiel)
6 | Firefox (support partiel)
6 | Edge (support partiel)
6 | Safari (support partiel)
6 | Opera (support partiel)
5 | Chrome 23
5 | Firefox 21
5 | Safari 6
5 | Opera 15
5 | Edge 12
5 | IE 10

# Orienté prototype
* Programmation orientée objet qui n'utilise pas les classes.
* La réutilisation des propriétés d'un objet est effectuée via des objets qui seront des prototypes pour d'autres objets.

# Prototype
* Liste de propriétés, attaché à un constructeur,
* Sert de « fallback » lorsque l’on cherche à accéder à une propriété manquante d’une instance constructeur.

# Modules
"Good authors divide their books into chapters and sections; good programmers divide their programs into modules"
* "self-contained" avec des fonctionnalités distinctes
* ajoutés, supprimés, modifiés si necessaire sans perturber l'ensemble du système
* Réutilisation

## CommonJs
* CommonJS spécifie un standard de modules JavaScript en s'assurant que chaque module s'exécute dans son propre espace de noms.
* Les modules exportent explicitement les variables qu'ils veulent exposer, et en définissant les autres modules requis pour fonctionner correctement.
* Pour faire cela: 
    - la fonction require(), qui permet d'importer un module donné dans la portée actuelle
    - l'objet module, qui permet d'exporter quelque chose de la portée actuelle
* L'implémentation dominante de CommonJS se trouve dans Node.js
* Conçu pour le chargement synchrone
* Utilisation principale coté serveur

## AMD (Asynchronous Module Definition)
* Spécifie une norme pour le JavaScript de sorte que les modules puissent charger leurs dépendances de façon asynchrone, résolvant les problèmes du chargement synchrone
* L'API est constituée de deux fonctions: 
    - define(): qui définit un module en renvoyant une valeur ou une fonction
    - require(): qui est similaire mais se contente d'effectuer un simple callback
* L'implémentation dominante de AMD se trouve dans RequireJS
* Conçu pour le chargement asynchrone
* Utilisation principale coté navigateurs

## UMD (Universal Module Definition)
* Pour les projets qui nécessitent la prise en charge des fonctionnalités AMD et CommonJS
* UMD crée un moyen d'utiliser l'un des deux, tout en prenant en charge la définition de variable globale (modules Globals)
* UMD est capable de fonctionner à la fois sur le client et sur le serveur

## ES6 <=> ES2015
* Pour satisfaire les utilisateurs de CommonJS et AMD
* Similaire à CommonJS, avec une syntaxe compacte, une préférence pour les exportations uniques
* Similaire à AMD, ils supportent directement le chargement asynchrone

## Module loaders & Module bundlers

### Module loaders
* Généralement une bibliothèque qui peut charger, interpréter et exécuter des modules JavaScript avec syntaxe AMD ou CommonJS.
* Dans une application avec plusieurs modules, il peut être assez pénible de s'assurer que tous les fichiers sont inclus et dans le bon ordre. 
* Un Module loader s'occupera de la gestion des dépendances en s'assurant que tous les modules sont chargés lors de l'exécution de l'application. 
* Les Module loaders les plus populaires sont RequireJS et SystemJS.

### Module bundlers
* Une alternative aux Module loaders.
* Fondamentalement, ils font la même chose (gérer et charger des modules interdépendants), mais pendant la construction de l'application avant l'exécution.
* Au lieu de charger les dépendances telles qu'elles définient dans le code, un bundler assemble tous les modules en un seul fichier (un bundle) avant l'exécution. 
* Les Module loaders les plus populaires sont Webpack et Browserify.

### Quand utiliser quoi?
* Le choix dépend de la structure et de la taille de l'application
* Un bundler génère beaucoup moins de fichiers que le navigateur doit télécharger --> peut réduire le temps de chargement. 
* Un loader peut fournir de meilleures performances, car le chargement d'un gros fichier monolithique peut également bloquer le démarrage de l'application.