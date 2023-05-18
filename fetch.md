# La notion de fetch en JavaScript

La méthode **fetch** en JavaScript est utilisée pour effectuer des requêtes vers des ressources externes, comme des **API**, et récupérer les données qui y sont associées. C'est un moyen pratique de communiquer avec des serveurs et de récupérer des informations.

## Méthode fetch pour une requête en GET

```js
fetch(url)
  .then(function(response) {
    return response.json();
  })
  .then(function(data) {
    console.log(data);
  })
  .catch(function(error) {
    console.log(error);
  });
```

- `url` est l'adresse du serveur ou de l'API à laquelle tu souhaites envoyer une requête.

- La méthode fetch renvoie une **_promesse_**, qui est une manière de gérer les opérations **_asynchrones_** en JavaScript.

- Dans la première fonction `then`, nous recevons la réponse du serveur sous forme d'objet `response`. Nous utilisons la méthode `json()` pour extraire les données de la réponse et les convertir en format JSON.

- Dans la deuxième fonction `then`, nous avons accès aux données récupérées, qui sont maintenant stockées dans l'objet `data`. Nous pouvons les utiliser comme bon nous semble, par exemple en les affichant dans la console.

- Si une erreur se produit lors de l'envoi de la requête ou de la réception de la réponse, la fonction `catch` sera exécutée et affichera l'erreur dans la console.

## Autre exemple pour une requête en POST

```js
const url = 'https://api.skoule.com/students/add';

const studentData = {
  firstname: 'Sarah',
  lastname: 'Tatine',
  status: 1,
  teacher_id: 2
};

const options = {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(studentData)
};

fetch(url, options)
  .then(function(response) {
    return response.json();
  })
  .then(function(data) {
    console.log(data);
  })
  .catch(function(error) {
    console.log(error);
  });
```

Nous effectuons une requête POST vers l'URL <https://api.skoule.com/students/add> pour créer un nouvel étudiant. Les données de l'étudiant sont fournies sous forme d'objet `studentData`.

Les options de la requête sont définies dans l'objet `options`. Nous spécifions la méthode comme étant **'POST'**, définissons l'en-tête **'Content-Type'** comme **'application/json'** pour indiquer que nous envoyons des données au format JSON, et utilisons `JSON.stringify()` pour convertir les données en JSON.

Ensuite, nous utilisons la méthode `fetch` avec l'URL et les options de la requête. Les étapes suivantes sont similaires à l'exemple précédent : nous récupérons la réponse du serveur au format JSON, accédons aux données dans la deuxième fonction `then`, et affichons les données dans la console. En cas d'erreur, nous la capturons dans la fonction `catch`.

### Liens utiles

- <https://grafikart.fr/tutoriels/javascript-promise-2068>
- <https://developer.mozilla.org/fr/docs/Web/API/Fetch_API/Using_Fetch>
- <https://www.youtube.com/watch?v=gNPRe_lxosE>