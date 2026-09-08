# Fiche : RAG (Retrieval-Augmented Generation)

## 📌 Définition
Technique qui combine un LLM avec une base de connaissances externe (documents, base vectorielle) pour générer des réponses ancrées dans des données précises et à jour.

## 🛠️ Fonctionnement (simplifié)
1. La question de l'utilisateur est transformée en vecteur (embedding)
2. Recherche des documents les plus pertinents dans une base vectorielle (similarité)
3. Ces documents sont injectés dans le prompt envoyé au LLM
4. Le LLM génère une réponse en s'appuyant sur ce contexte

## 💡 Pourquoi c'est utile
- Réduit les hallucinations
- Permet d'utiliser des données privées/récentes sans réentraîner le modèle
- Moins coûteux qu'un fine-tuning

## 🛠️ Outils courants
- Bases vectorielles : Chroma, Pinecone, Qdrant, pgvector (PostgreSQL)
- Frameworks : LangChain, LlamaIndex
- Embeddings : OpenAI, Voyage, modèles open-source (sentence-transformers)

## ✅ À retenir
RAG ≠ fine-tuning. RAG ajoute du contexte au moment de la requête, le fine-tuning modifie le modèle lui-même. Pertinent pour un projet type "second brain" (Obsidian).
