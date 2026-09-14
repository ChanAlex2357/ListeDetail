ITUniversity — Module M1 · Développement mobile Kotlin — Séance 5

**MINI-TP 5 — NAVIGATION**

« Relier deux écrans »

*NavHost, routes, arguments, retour — travail individuel, sur le projet fourni « ListeDetail »*

# 1. Objectifs

* Compléter un NavHost : déclarer une route avec argument, naviguer, revenir.
* Faire voyager un identifiant de la liste vers le détail — et comprendre pourquoi l'identifiant plutôt que l'objet.
* Vérifier le comportement de la backstack avec le retour système (lien avec la séance 3).
* Trier les remarques d'une revue IA : pertinente ou non pertinente ici.

# 2. Règles du mini-TP

1. Les prédictions se remplissent dans le modèle de l'étape 1 AVANT tout lancement de l'application : lire, prédire, puis seulement exécuter.
2. Pendant les étapes 1 à 3, aucune assistance IA — complétion IA de l’IDE désactivée.
3. Les deux écrans sont fournis et fonctionnels : SEULE la fonction AppNavigation() est à modifier — trois TODO, rien d'autre.

**ÉTAPE 1 — LIRE ET PRÉDIRE (SUR PAPIER, AVANT TOUT LANCEMENT)**

Téléchargez MiniTP5\_ListeDetail.zip depuis le dossier Drive de la séance, décompressez-le, ouvrez le projet dans Android Studio (File → Open) et LISEZ MainActivity.kt en entier — les deux écrans fournis, le NavHost et ses trois TODO. Puis remplissez le modèle :

| **Prédiction** | **Votre réponse** |
| --- | --- |
| **P1 — Au lancement (AVANT tout TODO) : que fait un clic sur un produit de la liste, et pourquoi ?** |  |
| **P2 — Une fois les TODO faits : que fera le bouton retour SYSTÈME depuis l’écran de détail ? Et depuis la liste ? (souvenez-vous de la séance 3)** |  |

Ne lancez rien avant d'avoir rempli les deux lignes du modèle.

**ÉTAPE 2 — LES TROIS TODO, DANS L’ORDRE**

1. TODO 1 — la route du détail : déclarez composable("detail/{produitId}") en recopiant le modèle fourni en commentaire — pas pour le deviner, pour le COMPRENDRE : à chaque ligne recopiée, dites-vous à voix basse ce qu'elle fait (déclarer l'argument, le relire en texte, le convertir, retrouver le produit, gérer le null).
2. TODO 2 — naviguer au clic : une ligne dans onProduitClick.
3. TODO 3 — le retour : une ligne dans onRetour.
4. Vérifiez le circuit complet : liste → clic sur « Girofle » → le détail affiche bien le girofle (pas un autre !) → « Retour à la liste ».

**ÉTAPE 3 — OBSERVER LA BACKSTACK**

1. Depuis l'écran de détail, utilisez le retour SYSTÈME (geste ou touche du téléphone) : comparez à votre prédiction P2.
2. Depuis la liste, utilisez encore le retour système : notez la différence sur la feuille, et expliquez-la en une phrase avec le vocabulaire de la pile.
3. Cas limite : ouvrez le détail du litchi (prix non fixé) — vérifiez que l'écran l'affiche proprement. Quelle construction Kotlin de la séance 1 rend cela possible ? (une phrase sur la feuille)

**VOIE OUVERTE — UNE TÂCHE IA UNIQUE : TRIER UNE REVUE**

1. Soumettez votre fonction AppNavigation() complétée à l'IA de votre choix. Prompt suggéré : « Fais une revue de ce code de navigation Compose : liste tes remarques, ne réécris pas tout. »
2. Triez ensuite CHAQUE remarque en deux colonnes sur la feuille : pertinente / non pertinente ICI — avec un mot de justification. L'IA suggérera probablement des choses hors périmètre (routes typées, ViewModel, animations…) : les classer « non pertinentes ici » est exactement l'exercice. Vous recopierez les deux ou trois lignes de synthèse de ce tri dans le champ « JOURNAL-IA » du formulaire.

# 3. Livrables (formulaire « S5 · Dépôt des livrables »)

Tout se dépose en fin de séance dans le formulaire unique « S5 · Dépôt des livrables » — le lien est affiché en séance et dans le dossier Drive de la séance :

* cette feuille remplie (modèle de prédictions, observations de la backstack, tri des remarques), en photo ou PDF ;
* le projet avec la navigation fonctionnelle, en url GIT
* la synthèse de votre tri des remarques IA, recopiée dans le champ « JOURNAL-IA » du formulaire.

Ces dépôts servent au suivi de votre progression. Les modalités d'évaluation du module vous seront précisées ultérieurement.