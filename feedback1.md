# Feedback Apprenant 1

Tu as démontré une bonne compréhension de l'exercice en proposant un code propre et bien commenté.
  
## Pour aller plus loin

- Au lieu d'utiliser la variable globale **$match** dans le constructeur du `CoreController`, il est préférable de passer cette variable en tant que paramètre du constructeur. De cette manière, tu peux injecter les dépendances nécessaires de manière explicite.Par exemple :
  
```php
class CoreController
{
    private $match;

    public function __construct($match)
    {
        $this->match = $match;
        // ...
    }
    // ...
}
```

En passant la variable **$match** en tant que paramètre du constructeur, tu peux assigner à une propriété de la classe **\$match** qui sera ensuite accessible dans toutes les autres méthodes de la classe.

Lorsque tu instancies le `CoreController` depuis un autre contrôleur, tu peux lui passer la variable **$match** :

```php
$coreController = new CoreController($match);
```

De cette manière, tu as explicitement fourni la dépendance requise au CoreController plutôt que de dépendre d'une variable globale.

[`Lien vers la doc`](https://www.php.net/manual/en/language.oop5.decon.php)
