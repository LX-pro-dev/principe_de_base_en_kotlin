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

### En savoir plus
[Vocabulaire pour les bases d'Android en Kotlin](https://developer.android.com/courses/android-basics-kotlin/android-basics-kotlin-vocab)

[Collections Kotlin](https://kotlinlang.org/docs/reference/collections-overview.html)

[Classe `List`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-list/)

[Classe `Set`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-set/)

[Classe `Map`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-map/)

[Transformations de `Collection`](https://kotlinlang.org/docs/reference/collection-transformations.html)

[Fonctions d'ordre supérieur et lambdas](https://kotlinlang.org/docs/reference/lambdas.html)

[Types de fonctions](https://kotlinlang.org/docs/reference/lambdas.html#function-types)

[`it`: nom implicite pour un seul paramètre](https://kotlinlang.org/docs/reference/lambdas.html#it-implicit-name-of-a-single-parameter)

[Fonctions lambdas](https://play.kotlinlang.org/byExample/04_functional/02_Lambdas)

[Fonctions d'ordre supérieur](https://play.kotlinlang.org/byExample/04_functional/01_Higher-Order%20Functions)

## Activités et intents

### Objectifs de l'atelier
Modifier une application de dictionnaire afin d'implémenter la navigation entre les écrans à l'aide d'intents et en ajoutant un menu d'options.

URL du code de démarrage : https://github.com/google-developer-training/android-basics-kotlin-words-app

Nom de la branche avec code de démarrage : starter

### Présentation de l'application Words
`LetterAdapter` est utilisé par `RecyclerView` dans `MainActivity`. Chaque lettre correspond à un bouton avec un élément `onClickListener`, qui est actuellement vide. C'est là que vous gérerez les pressions de bouton permettant d'accéder à `DetailActivity`.
`WordAdapter` est utilisé par `RecyclerView` dans `DetailActivity` pour afficher une liste de mots. Bien que vous ne puissiez pas encore accéder à cet écran, sachez simplement que chaque mot est associé à un bouton avec un élément `onClickListener`. C'est ici que vous ajouterez le code qui permettra d'accéder au navigateur afin d'afficher la définition du mot.
`MainActivity` nécessitera également quelques modifications. C'est là que vous implémenterez le menu d'options afin d'afficher un bouton permettant aux utilisateurs de basculer entre les mises en page "Liste" et "Grille".
![image](https://user-images.githubusercontent.com/44195741/205601268-e16d6a1f-8f67-4ea2-b310-c507c3068373.png)

### taches à réaliser
- Configurer un intent explicite
- Configurer l'activité de détail
- Configurer un intent implicite
- Configurer le menu et les icônes
- Implémenter le bouton Menu

### Résumé
![image](https://user-images.githubusercontent.com/44195741/205601724-ba304beb-0214-4df9-a74f-271e28a0b4bd.png)

- Les intents explicites permettent d'accéder à des activités spécifiques dans votre application.
- Les intents implicites correspondent à des actions spécifiques (comme ouvrir un lien ou partager une image) et laissent le système déterminer comment les traiter.
![image](https://user-images.githubusercontent.com/44195741/205601901-5847d439-6911-4c7f-b8e2-3d944876792c.png)

- Les options de menu vous permettent d'ajouter des boutons et des menus à la barre d'application.
- Les objets compagnons permettent d'associer des constantes réutilisables à un type plutôt qu'une instance de ce type.
Pour exécuter un intent :

- Effectuez une référence au contexte.
- Créez un objet Intent qui fournit un type d'activité ou d'intent (selon qu'il est explicite ou implicite).
- Transmettez toutes les données nécessaires en appelant putExtra().
- Appelez startActivity() en transmettant l'objet intent.

###  En savoir plus
[Intents et filtres d'intents](https://developer.android.com/guide/components/intents-filters)
[Intents couramment utilisés](https://www.google.com/search?client=safari&rls=en&q=common+intents+android&ie=UTF-8&oe=UTF-8)
[Créer des menus d'options avec du code XML](https://developer.android.com/guide/topics/ui/menus)
[Interfaces en Kotlin](https://kotlinlang.org/docs/reference/interfaces.html)
[Interface CharSequence](https://developer.android.com/reference/java/lang/CharSequence)
[Sécurité null en Kotlin](https://kotlinlang.org/docs/reference/null-safety.html)
[Expressions et déclarations d'objets en Kotlin](https://kotlinlang.org/docs/reference/object-declarations.html)
[Modèle Singleton](https://en.wikipedia.org/wiki/Singleton_pattern)
[Flux de contrôle en Kotlin](https://kotlinlang.org/docs/reference/control-flow.html)
