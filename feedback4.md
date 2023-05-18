# Feedback apprenant 4

Tu as bien rédigé la partie routage de ton application, mais malheureusement il y'a plusieurs problèmes qui bloquent son bon fonctionnement.

Tu dois suivre les consignes pas à pas, et tester ton code au fur et à mesure, à chaque fonctionnalité implémentée. Cela te permettera d'avancer progressivement et sereinement.

Sois vigilant sur le bon nommage de tes variables et noms de méthodes. Par exemple, j'ai remarqué beaucoup de fautes de frappe , ce qui peut conduire à des références incorrectes et à des erreurs lors de l'exécution du code. Par exemple :

```php
// ici un "d" en trop
$teachers = $teachersdModel->findAll();

// ou encore ici $retour au lieu de $router
$retour = $studentsdFromDb->students();
```

Il est important de prendre le temps de relire et de vérifier ton code avant de l'exécuter afin de repérer ces erreurs et de les corriger. Tu peux te servir de VSCode avec un vérificateur de syntaxe comme **PHP Intelephense** pour t'aider à détecter ces erreurs plus facilement.

Si tu as du temps, je te conseil de reprendre ce parcours depuis le début et d'avancer point par point. Note les points bloquant et difficultés rencontrées et reviens vers moi.
