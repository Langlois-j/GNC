# Correction : Prompt Engineering, RAG, LLM

## Exercice 1
```
"Voici ma fonction Python [coller le code]. Elle devrait faire X mais renvoie Y.
Identifie le bug, explique pourquoi il se produit, et propose une correction
en respectant le style du reste du fichier."
```

## Exercice 2
Un chatbot RAG va chercher les passages pertinents de la documentation interne réelle et les injecte dans le prompt avant de générer la réponse. Le modèle s'appuie donc sur des faits vérifiables et à jour plutôt que sur sa seule mémoire d'entraînement, ce qui réduit fortement le risque d'inventer une information.

## Exercice 3
a) **Faux** — il prédit statistiquement le mot suivant, sans notion de vérité.
b) **Faux** — une température basse (proche de 0) rend les réponses plus déterministes ; une température élevée augmente l'aléatoire/créativité.
c) **Faux** — le RAG ajoute du contexte au moment de la requête, sans modifier le modèle.

## Exercice 4
```
Tu es un assistant spécialisé dans la relecture de code Python.
Pour chaque extrait fourni :
1. Signale les violations PEP8 (nommage, longueur de ligne, espacement)
2. Explique brièvement pourquoi c'est une violation
3. Propose la correction
Réponds de façon concise, sous forme de liste.
```
