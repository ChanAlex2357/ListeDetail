# MiniTP5 — Prédictions

## Étape 1

| Prédiction | Votre réponse |
|---|---|
| P1 — Au lancement (AVANT tout TODO) : que fait un clic sur un produit de la liste, et pourquoi ? | un clic sur un produit de la liste va rediriger vers l'ecran de detail |
| P2 — Une fois les TODO faits : que fera le bouton retour SYSTÈME depuis l'écran de détail ? Et depuis la liste ? | Depuis le détail : le système retourne naturellement sur l'écran de liste qui est toujours présent en back, c'est l'empilement naturel des écrans. Depuis la liste : ça quitte l'application. |

## Étape 3 — Observation de la backstack

**Observations réelles (retour système) :**
1. Depuis le détail : retour à la liste.
2. Depuis la liste : quitte l'application.
3. Détail du Litchi (prix non fixé) : s'affiche correctement.

Conforme à la prédiction P2 — aucun écart.

**Explication (vocabulaire de la pile) :** Depuis le détail on dépile l'écran donc on retourne sur l'écran précédent qui est l'écran de liste. À partir de là on est sur le dernier écran de la pile donc si on fait retour on quitte.

**Construction Kotlin (séance 1) pour le prix du litchi :** on a utilisé un null safety pour afficher un texte par défaut dans le cas de prix null.

## Voie ouverte

| # | Remarque de l'IA | Pertinente ici ? | Justification |
|---|---|---|---|
| 1 | Routes en chaînes construites à la main, pas de sécurité de type sur l'argument | Pertinente | typage |
| 2 | `getString(...)?.toIntOrNull()` peut échouer silencieusement (id absent/non numérique), écran vide sans erreur ni log | Pertinente | robustesse |
| 3 | Recherche du produit par parcours de liste à chaque navigation, pas de ViewModel/repository | Non pertinente | hors périmètre |
| 4 | Pas d'animation de transition entre les écrans | Non pertinente | hors périmètre |
| 5 | Id passé comme argument plutôt que l'objet complet, mais choix non commenté | Non pertinente | hors périmètre |
