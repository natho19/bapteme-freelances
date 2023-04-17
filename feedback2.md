# Feedback 2

## Points forts :clap:

-   Utilisation de BEM dans les vues
-   Utilisation d'un tableau en html pour afficher le deck

## Erreurs identifiées :boom:

### Étape 1 : Détail d'une carte

-   Le titre de la page n'est pas présent
-   Toutes les informations disponibles ne sont pas visibles notamment `value_north`, `value_east`, `value_south`, `value_west`
-   Rajouter un message qui informe l'utilisateur quand la carte n'existe pas

### Étape 2 : Recherche

-   Sur la vue, mentionner l'élément dans le titre **_(Ex : Résultat de recherche par élément : tonnerre)_**
-   Afficher directement les cartes au lieu d'utiliser pour chaque carte un lien qui redirige vers le détail de la carte
-   Afficher toutes les cartes si **"aucun élément"** n'est sélectionné dans le formulaire de recherche par élément

### Étape 3 : Construire un deck

#### 3.1: Activer les sessions

-   Utiliser une variable dotenv pour la clé secrète au lieu de la mentionner directement dans la déclaration de la session (Cf https://www.npmjs.com/package/dotenv). **La clé secrète étant une information sensible**

#### 3.2 Ajouter une carte au deck

-   L'ajout de carte est possible même si le deck **possède déjà 5 cartes**

#### 3.3 Une page pour visualiser le deck

-   Mauvaise utilisation des th et des td (un th et un td vide) pour afficher les cartes dans le deck. (Cf https://developer.mozilla.org/fr/docs/Web/HTML/Element/table)
-   Affichage d'une variable `card.price` qui n'existe pas

## Fonctionnalités manquantes :x:

-   Supprimer une carte du deck
-   Recherche par niveau
-   Recherche par valeur
-   Recherche par nom
