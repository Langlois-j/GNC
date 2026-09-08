# Fiche : LLM — notions de base

## 📌 Définition
LLM = Large Language Model, un modèle de deep learning entraîné sur d'énormes volumes de texte pour prédire/générer du langage.

## 🛠️ Concepts clés
| Terme | Définition |
|---|---|
| **Token** | Unité de texte (mot, sous-mot ou caractère) traitée par le modèle |
| **Context window** | Quantité de texte (en tokens) que le modèle peut "voir" en une fois |
| **Fine-tuning** | Ré-entraînement partiel d'un modèle sur des données spécifiques |
| **Température** | Paramètre contrôlant le caractère aléatoire des réponses (0 = déterministe, 1+ = créatif) |
| **Hallucination** | Le modèle génère une information fausse avec assurance |
| **System prompt** | Instructions de contexte/rôle données au modèle avant la conversation |

## 💡 Pourquoi les LLM "hallucinent"
Ils prédisent le mot suivant le plus probable statistiquement, sans "savoir" ce qui est vrai — d'où l'intérêt du RAG pour ancrer les réponses dans des faits vérifiables.

## ✅ À retenir
Un LLM ne "comprend" pas au sens humain : c'est un système de prédiction de séquences, extrêmement performant mais sans garantie de véracité.
