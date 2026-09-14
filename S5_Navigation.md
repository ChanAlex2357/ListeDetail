ITUNIVERSITY — MODULE M1 · SÉANCE 5
Navigation :
une application est un graphe d’écrans
NavHost, routes, arguments, retour
Mini-TP « Relier deux écrans »
Kit pédagogique — Séance 5 — version M1

Penser en graphe : écrans, routes, chemins
clic sur un produit → navigate("detail/3")
ÉCRAN LISTE ÉCRAN DÉTAIL
route : "liste" route : "detail/{produitId}"
LazyColumn des produits Un produit, ses informations,
(séance 4) un bouton retour
retour → popBackStack()
Le parallèle web
Route URL · argument paramètre d’URL · retour bouton précédent du navigateur. La navigation mobile a convergé vers les idées du web — vous êtes
en terrain connu.

Le graphe en code : NavHost et routes
AppNavigation() — le code exact du projet fourni
À retenir
val navController = rememberNavController()
• NavHost : la carte routière — toutes les destinations
NavHost(navController, startDestination = "liste") {
• composable("route") { … } : une route → un écran
• navController : le GPS — navigate, popBackStack
composable("liste") {
EcranListe(
• Les écrans ne connaissent pas le navController : ils
produits = produits,
reçoivent des lambdas — l’écran signale, la navigation
onProduitClick = { produitId ->
décide
// TODO 2 du mini-TP
}
)
}
// TODO 1 du mini-TP : la route "detail/…"
}

Faire voyager une information : l’argument de route
Déclarer → naviguer → relire
Pourquoi l’identifiant, pas l’objet ?
// (1) DÉCLARER la route avec son argument
• La route est du texte, comme une URL
composable("detail/{produitId}") { backStackEntry ->
• L’écran retrouve la donnée par lui-même (find
// (3) RELIRE l’argument à l’arrivée
aujourd’hui, requête Room en séance 7)
val id = backStackEntry.arguments
• toIntOrNull + if ≠ null : un identifiant invalide n’affiche
?.getString("produitId")?.toIntOrNull()
rien — il ne plante pas
val produit = produits.find { it.id == id }
if (produit != null) {
EcranDetail(produit, onRetour = { … })
}
}
// (2) NAVIGUER en remplissant l’emplacement
navController.navigate("detail/$produitId")

Revenir : la backstack — retrouvailles avec la séance 3
| EMPILE un écran | DÉPILE | DÉPILE aussi — gratuitement |
| --------------- | ------ | --------------------------- |
liste → liste + détail. L’écran précédent reste  Retour à l’écran précédent — le bouton « Retour  Le geste ou la touche du téléphone fait la même
dessous, prêt au retour. à la liste » du détail (TODO 3). chose, sans une ligne de code. Deux chemins, un
comportement.
| navigate(…) | popBackStack() | Retour système |
| ----------- | -------------- | -------------- |
Et quand un écran entier est de trop ?
Une confirmation → AlertDialog · une information passagère → Snackbar. À reconnaître aujourd’hui ; vous les utiliserez naturellement le moment venu.

Mini-TP 5 · « Relier deux écrans »
1 Lire et prédire
Lire MainActivity.kt ; prédire : que fait un clic avant les TODO ? que fera le retour SYSTÈME depuis le détail (souvenir de la séance 3) ?
2 Les trois TODO
TODO 1 : la route detail/{produitId} (modèle en commentaire). TODO 2 : navigate au clic. TODO 3 : popBackStack. Vérifier le bon produit.
3 Observer
Retour système depuis le détail, puis depuis la liste : noter la différence. Vérifier l’affichage du litchi (prix null).
4 Voie ouverte — trier une revue
Revue IA de votre AppNavigation() ; trier chaque remarque : pertinente / non pertinente ici, avec un mot de justification.
Dépôt en fin de séance : formulaire « S5 · Dépôt des livrables » — feuille, projet ZIP, tri des remarques en 3 lignes.