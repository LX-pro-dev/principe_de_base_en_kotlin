# Module 3 : Navigation
Facilitez la navigation dans et entre les écrans, pour une expérience utilisateur cohérente et prévisible.

## Collections en Kotlin
Comprendre le fonctionnement des collections et leur manipulation à l'aide de lambdas et de fonctions d'ordre supérieur

- Une collection est un groupe d'éléments associés
- Les collections peuvent être modifiables ou immuables
- Les collections peuvent être triées ou non triées
- Les collections peuvent nécessiter des éléments uniques ou inclure des doublons
- Kotlin accepte différents types de collections, y compris les listes (List), les ensembles (Set) et les maps (Map == dictionnaire : sytème key/value)
- Kotlin fournit de nombreuses fonctions pour le traitement et la transformation des collections, y compris `forEach`, `map`, `filter`, `sorted`, etc.
- Un lambda est une fonction sans nom pouvant être transmise immédiatement en tant qu'expression. Voici un exemple : { a: Int -> a * 3 }.
> Remarque : Il est courant qu'un lambda n'ait qu'un seul paramètre. Kotlin offre donc un raccourci. Kotlin utilise implicitement l'identifiant spécial `it` pour le paramètre unique d'un lambda.

> Remarque : Pour comparer deux objets pour les trier, la convention est de renvoyer une valeur inférieure à 0 si le premier objet est inférieur au second, de renvoyer une valeur égale à 0 s'ils sont égaux et enfin de renvoyer à une valeur supérieure à 0 si le premier objet est supérieur au second.

> Remarque : Si vous n'utilisez pas de paramètre lambda dans le corps de la fonction, vous pouvez le nommer `_` pour le rendre plus lisible et ordonné. Ce code a le même comportement.
ex :
costOfServiceEditText.setOnKeyListener { view, keyCode, _ -> handleKeyEvent(view, keyCode) }
- Une fonction d'ordre supérieur permet de transmettre une fonction à une autre ou de renvoyer une fonction depuis une autre fonction.
ex : 
val words = listOf("about", "acute", "awesome", "balloon", "best", "brief", "class", "coffee", "creative")
val filteredWords = words.filter { it.startsWith("b", ignoreCase = true) }
        .shuffled()
        .take(2)
        .sorted()
