# Feedback 3

## Points forts :clap:

-   Les vues sont regroupés par dossier
-   Présence de commentaires
-   Utilisation des préférences pour personnaliser l'interface de l'éditeur

## Erreurs identifiées :boom:

### Étape 0 : Analyse du code fourni et mise en place

-   Mauvaise indentation du code

-   Dans `cardList.ejs`, Le lien (balise a) qui permet de cliquer sur l'image de la carte est fermé mais n'a jamais été ouvert.

```
<div class="card">
    <a href="/card/<%= card.id %>"><%= card.name %></a>
        <img src="/visuals/<%= card.visual_name%>" alt="<%= card.name %> illustration">
        <p class="cardName">
        <%= card.name %>
        </p>
    </a>
    <a class="link--addCard" title="Ajouter au deck" href="/card/<%= card.id %>"><%= card.name %>[ + ]</a>
</div>

```

### Étape 1 : Détail d'une carte

-   Dans la vue `cardDetail.ejs`, on ne peut pas faire une boucle for sur un seul élément. La requête retourne un seul objet à afficher et non un tableau d'objets

-   Incompréhension dans l'utilisation de la boucle for

> **_Notes_** : On utilise une boucle for dans une liste pour avoir accès à chaque élément de la liste (itération). Mais quand on a un seul élément on ne peut pas utiliser une boucle for. On l'utilise à partir de deux éléments. (Cf https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/Loops_and_iteration)

-   Si le rendu était visible, les informations sont affichées côte à côte sans libellé ni distinction. Ce sera très difficile à l'utilisateur de savoir à quoi correspond chaque valeur

### Étape 2 : Recherche

-   Le formulaire de recherche ne marche pas
-   `dataMapper` n'a pas été importé et n'est pas défini alors qu'il est utilisé
-   `element` est envoyé à la vue au lieu du résultat de la requête
-   La fonction `cardElement()` n'existe pas dans le `dataMapper`, c'est plutôt la fonction `getCardByElement()`
-   La boucle for doit être utilisé mais ne peut pas marcher car c'est `element` qui est envoyé à la vue et non le résultat de la requête (tableau d'objet cartes).
-   Un formulaire est rendu dans la vue alors qu'on aimerait afficher les cartes qui correspondent à l'élément sélectionné.

## Fonctionnalités manquantes :x:

-   Activer les sessions
-   Ajouter une carte au deck
-   Une page pour visualiser le deck !
-   Supprimer une carte du deck
-   Recherche par niveau
-   Recherche par valeur
-   Recherche par nom
