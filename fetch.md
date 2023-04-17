# Explication de la notion de fetch

**_fetch est une fonction JavaScript native qui permet d'effectuer des requêtes `HTTP`. Elle peut être utilisée pour récupérer des données à partir d'une API ou d'un serveur distant._**

On peut comparer `fetch` à l'action d'aller _"chercher une pizza"_.

> Imaginons que tu veux commander une pizza. Pour cela, tu dois appeler la pizzeria et passer ta commande. La pizzeria va ensuite préparer la pizza et te la livrer.

De la même manière, `fetch` permet de demander des données à un serveur distant en envoyant **une requête** `HTTP` **(passer la commande à la pizzeria)**. Le serveur distant va ensuite **traiter** ta demande **(préparer la pizza)** et **renvoyer les données** que tu as demandées **(livraison de la pizza)**.

Une fois que les données sont renvoyées, tu peux les **utiliser** dans ton application, comme si tu **mangeais ta pizza !**

Voici un exemple d'utilisation :

```
homePage: async function (req, res) {
    try {
        fetch('https://jsonplaceholder.typicode.com/todos/1')
            .then(response => response.json())
            .then(data => console.log(data))
            .catch(error => console.error(error));

        const cards = await dataMapper.getAllCards();
        res.render('cardList', {
            cards: cards,
            title: 'Liste des cartes',
        });
    } catch (error) {
        console.error(error);
        res.status(500).render('error');
    }
}

```

Dans cet exemple, nous utilisons `fetch` pour récupérer un objet JSON à partir d'une API. L'URL 'https://jsonplaceholder.typicode.com/todos/1' est celle d'un service web fictif qui renvoie un objet JSON sous la forme de :

```json
{
    "userId": 1,
    "id": 1,
    "title": "delectus aut autem",
    "completed": false
}
```

Une fois que nous avons récupéré la réponse avec `fetch`, nous appelons la méthode `json()` sur l'objet `Response` retourné pour transformer la réponse en un objet JavaScript.

Ensuite, nous utilisons la méthode `then()` pour récupérer les données et les afficher dans la console.

Si la requête échoue, la méthode `catch()` sera appelée avec l'erreur correspondante.

> Note que `fetch` utilise le protocole `HTTP` et par conséquent peut être utilisé pour effectuer des requêtes `GET`, `POST`, `PUT`, `DELETE`, etc.

J'espère que cela t'a aidé à comprendre la notion de `fetch` en JavaScript :sunglasses:. N'hésite pas à me faire un retour s'il y a encore des zones d'ombre :wink:.
