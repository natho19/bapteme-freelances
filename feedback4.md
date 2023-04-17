# Feedback 4

## Points forts :clap:

-   Accepté le challenge et n'a pas eu peur de commencer le projet

## Erreurs identifiées :boom:

### Étape 0 : Analyse du code fourni et mise en place

-   Sur la page qui liste toutes les cartes, Le lien qui permet de cliquer sur l'image de la carte est vide `<a href="#">...</a>`

```
<div class="card">
    <a href="#">
        <img src="/visuals/<%= card.visual_name %>" alt="<%= card.name %> illustration">
        <p class="cardName"><%= card.name %></p>
    </a>
    <a class="link--addCard" title="Ajouter au deck" href="#">[ + ]</a>
</div>
```

### Étape 1 : Détail d'une carte

-   Dans le `router`, pour afficher les détails d'une carte, il faut passer l'`id` en paramètre

-   Dans le `dataMapper` au niveau de la fonction `getCard()` `$1` n'est pas le paramètre de la requête mais l'`id`. S'il faut utiliser `$1` alors il faut lui associer la valeur de l'`id`

-   Dans la requête, il n'y a pas de champ `card.id` mais plutôt `id`

-   `queryResult` a été déclaré mais `resultQuery` qui n'existe pas a été utilisé à sa place

```
const queryResult = await client.query(
    `   SELECT *
        FROM card
        WHERE card.id = $1;
    `);
    if (resultQuery.rowCount === 1) {
        return queryResult.rows[0]
    }
return null;

```

-   Dans la fonction `cardPage()` de `mainController` on ne récupère pas l'id de la requête dans l'url avec Number(req.params.id) et donc quand on exécute `getCard()` de `dataMapper` on ne lui envoie pas l'id dont il a besoin pour trouver la carte correspondante

-   Quand on rend la réponse, `card` n'est pas envoyé (résultat de la requête)

-   Dans la vue `card.ejs` qui doit afficher les détails de la carte, plusieurs variables sont déclarées mais ne sont pas utilisées

-   Une boucle for aussi est utilisée alors qu'on veut juste afficher les informations d'une seule carte

-   **Incompréhension des principes de base de MVC, du routage, des variables et de la boucle for**
    > **Liens utiles**
    >
    > https://developer.mozilla.org/fr/docs/Glossary/MVC
    >
    > https://expressjs.com/fr/guide/routing.html
    >
    > https://developer.mozilla.org/fr/docs/Learn/JavaScript/First_steps/Variables
    >
    > https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/Loops_and_iteration

## Fonctionnalités manquantes :x:

-   Recherche par élément
-   Activer les sessions
-   Ajouter une carte au deck
-   Une page pour visualiser le deck !
-   Supprimer une carte du deck
-   Recherche par niveau
-   Recherche par valeur
-   Recherche par nom
