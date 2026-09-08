# Fiche : Prompt Engineering — bases

## 📌 Définition
Technique pour formuler des instructions à un LLM afin d'obtenir des réponses plus précises et pertinentes.

## 🛠️ Principes clés
1. **Être précis et contextuel** : donner le rôle, le format attendu, les contraintes
2. **Décomposer les tâches complexes** en étapes
3. **Donner des exemples** (few-shot prompting)
4. **Demander un raisonnement explicite** ("réfléchis étape par étape")
5. **Itérer** : reformuler si le résultat ne convient pas

## 💡 Exemple avant/après
```
❌ "Fais-moi un résumé"

✅ "Résume ce texte en 3 points clés, en français,
   pour un public non technique, en 100 mots maximum."
```

## 💡 Techniques avancées
- **Chain of Thought** : demander un raisonnement pas à pas avant la réponse finale
- **Few-shot** : fournir 2-3 exemples du résultat attendu
- **System prompt** : définir un rôle/contexte global (ex : "Tu es un expert FastAPI")

## ✅ À retenir
Un bon prompt = contexte + tâche claire + format de sortie attendu + contraintes.
