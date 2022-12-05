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

## Étapes du cycle de vie d'une activité

### Objectifs de l'atelier
- Modifier une application de démarrage appelée DessertClicker afin d'ajouter les informations de journalisation affichées dans l'outil Logcat
- Remplacer les méthodes de rappel de cycle de vie et consigner les modifications apportées à l'état d'une activité
- Exécuter l'application et observer les informations de journalisation qui s'affichent lorsque l'activité démarre, s'arrête et reprend
- Implémenter la méthode `onSaveInstanceState()` pour conserver les données de l'application qui pourraient être perdues en cas de changement de la configuration Ajouter un code pour restaurer ces données lorsque l'application redémarrera

Téléchargez le code de démarrage de DessertClicker et ouvrez-le dans Android Studio.

URL du code de démarrage : https://github.com/google-developer-training/android-basics-kotlin-dessert-clicker-app/tree/starter
Le nom du dossier est `android-basics-kotlin-dessert-clicker-app-starter`

### cycle de vie d'une activity
![image](https://user-images.githubusercontent.com/44195741/205606908-9fce872c-8193-4b34-817f-e018494a78aa.png)
> Remarque : Lorsque vous remplacez la méthode `onCreate()`, vous devez appeler l'implémentation de la super-classe pour terminer la création de l'activité. Au sein de celle-ci, vous devez donc appeler immédiatement `super.onCreate()`. Il en va de même pour d'autres méthodes de rappel de cycle de vie.

### journalisation
La classe `Log` écrit les messages dans l'outil **Logcat**. **Logcat** est la console de journalisation des messages. C'est là que les messages Android concernant votre application s'affichent, y compris ceux que vous envoyez explicitement au journal avec la méthode `Log.d()` ou d'autres méthodes de classe `Log`.

Cette commande se compose de trois parties :
- La *priorité* du message de journal, c'est-à-dire son importance. Dans ce cas, la méthode `Log.d()` écrit un message de débogage. Les autres méthodes de la classe Log incluent `Log.i()` pour les messages d'information, `Log.e()` pour les erreurs, `Log.w()` pour les avertissements ou `Log.v()` pour les messages détaillés.
- La *balise* de journal (premier paramètre), dans ce cas `"MainActivity"`. La balise est une chaîne qui vous permet de trouver plus facilement vos messages de journal dans Logcat. Elle correspond généralement au nom de la classe.
- Le *message réel* (deuxième paramètre) est une chaîne courte qui, dans ce cas, est `"onCreate called"`.
> Remarque : Nous vous recommandons de déclarer une const>Remarque : Nous vous recommandons de déclarer une constante TAG dans la classe, comme suit.
const val TAG = "MainActivity"
Utilisez-la dans les appels suivants aux méthodes de journalisation, comme ci-dessous :
Log.d(TAG, "onCreate Called")

`override fun onCreate() {
   super.onCreate()
   Log.d(TAG, "onCreate Called")
}
override fun onResume() {
   super.onResume()
   Log.d(TAG, "onResume Called")
}

override fun onPause() {
   super.onPause()
   Log.d(TAG, "onPause Called")
}

override fun onStop() {
   super.onStop()
   Log.d(TAG, "onStop Called")
}

override fun onDestroy() {
   super.onDestroy()
   Log.d(TAG, "onDestroy Called")
}

override fun onRestart() {
   super.onRestart()
   Log.d(TAG, "onRestart Called")
}`

> Remarque : Le point clé à retenir ici est que onCreate() et onDestroy() ne sont appelés qu'une seule fois pendant la durée de vie d'une seule instance d'activité : onCreate() pour initialiser l'application pour la première fois et onDestroy() pour nettoyer les ressources utilisées par l'application.

> Remarque : Il est important de noter que les éléments onStart() et onStop() sont appelés plusieurs fois lorsque l'utilisateur accède à l'activité, puis la quitte.

### Enregistrer les données du bundle à l'aide de la fonction onSaveInstanceState()
La méthode `onSaveInstanceState()` est un rappel qui permet d'enregistrer les données dont vous pourriez avoir besoin si l'activité (`Activity`) était éliminée. Dans le schéma de rappel de cycle de vie, `onSaveInstanceState()` est appelé après l'arrêt de l'activité. Il est appelé chaque fois que votre application passe en arrière-plan.

`override fun onSaveInstanceState(outState: Bundle) {
   super.onSaveInstanceState(outState)

   Log.d(TAG, "onSaveInstanceState Called")
}`
> Remarque : Il existe deux forçages pour `onSaveInstanceState()`, l'un avec un paramètre outState uniquement, et l'autre qui comprend les paramètres `outState` et `outPersistentState`. Utilisez celui indiqué dans le code ci-dessus, avec le seul paramètre `outState`.

#### Enregistrer et récupérer les données du bundle d'états d'instance.
`outState.putInt(KEY_REVENUE, revenue)
outState.putInt(KEY_DESSERT_SOLD, dessertsSold)`

#### Restaurer les données d'un bundle dans onCreate()
`override fun onCreate(savedInstanceState: Bundle?) {`

> Remarque : Pendant que l'activité est recréée, le rappel onRestoreInstanceState() est appelé après onStart(), également avec le bundle. La plupart du temps, vous restaurez l'état de l'activité dans onCreate(). Toutefois, comme onRestoreInstanceState() est appelé après onStart(), vous pouvez utiliser onRestoreInstanceState() si vous devez restaurer un état après onCreate().

`if (savedInstanceState != null) {
   revenue = savedInstanceState.getInt(KEY_REVENUE, 0)
   dessertsSold = savedInstanceState.getInt(KEY_DESSERT_SOLD, 0)
}`

### Résumé
#### Cycle de vie de l'activité
- Le *cycle de vie de l'activité* correspond à un ensemble d'états par lesquels passe une activité. Il commence lorsque l'activité est créée pour la première fois et se termine lorsque l'activité est éliminée.
- Lorsque l'utilisateur passe d'une activité à l'autre et de votre application à une autre, l'état change dans le cycle de vie de l'activité.
- Chaque état du cycle de vie de l'activité possède une méthode de rappel correspondante que vous pouvez remplacer dans la classe `Activity`. Les principales méthodes de cycle de vie sont les suivantes : `onCreate()` `onStart()` `onPause()` `onRestart()` `onResume()` `onStop()` `onDestroy()`
- Pour ajouter le comportement qui se produit lorsque votre activité passe à un état du cycle de vie, remplacez la méthode de rappel de correspondante.
- Pour ajouter des méthodes de remplacement à vos classes dans Android Studio, sélectionnez **Code > Remplacer les méthodes** ou appuyez sur `Control+o`.

#### Journalisation
- L'API de journalisation Android, et plus particulièrement la classe `Log`, vous permet d'écrire des messages courts affichés dans l'outil Logcat dans Android Studio.
- Utilisez `Log.d()` pour rédiger un message de débogage. Cette méthode utilise deux arguments : la balise de journal (généralement un nom de classe) et le message de journal (une courte chaîne).
- Utilisez la fenêtre **Logcat** d'Android Studio pour afficher les journaux système, y compris les messages que vous écrivez.

#### Conserver l'état de l'activité
- Lorsque votre application passe en arrière-plan, juste après l'appel de la méthode `onStop()`, les données de l'application peuvent être enregistrées dans un bundle. Certaines données de l'application, telles que le contenu d'un élément `EditText`, sont automatiquement enregistrées.
- Le bundle est une instance de `Bundle`, qui correspond à un ensemble de clés et de valeurs. Les clés sont toujours des chaînes.
- Utilisez le rappel `onSaveInstanceState()` pour enregistrer d'autres données dans le bundle que vous souhaitez conserver, même si l'application a été fermée automatiquement. Pour placer des données dans le bundle, utilisez les méthodes correspondantes commençant par `put`, telles que `putInt()`.
- Vous pouvez récupérer des données du bundle dans la méthode `onRestoreInstanceState()` ou, plus communément, dans `onCreate()`. La méthode `onCreate()` comporte un paramètre `savedInstanceState` qui détient le bundle.
- Si la variable `savedInstanceState` est `null`, l'activité a été lancée sans bundle d'état et il n'existe pas de données d'état à récupérer.
- Pour récupérer des données du bundle avec une clé, utilisez les méthodes `Bundle` commençant par `get`, par exemple `getInt()`.

#### Modifications de la configuration
- Une *modification de la configuration* se produit lorsque l'état de l'appareil change de manière si radicale que le moyen le plus simple de s'adapter à cette modification consiste à éliminer l'activité et à la recréer.
- L'exemple le plus courant de modification de la configuration est lorsque l'utilisateur fait pivoter l'appareil du mode Portrait au mode Paysage, ou inversement. Une modification de la configuration peut également se produire lorsque la langue de l'appareil change ou qu'un clavier matériel est branché.
- Lorsqu'une modification de configuration se produit, Android appelle tous les rappels d'arrêt du cycle de vie de l'activité. Android redémarre ensuite toute l'activité, en exécutant tous les rappels de démarrage du cycle de vie.
- Quand Android arrête une application en raison d'une modification de la configuration, il redémarre l'activité avec le bundle d'état disponible pour `onCreate()`.
- Comme pour l'arrêt d'un processus, enregistrez l'état de votre application dans le bundle dans `onSaveInstanceState()`.
