# Fiche : Docker — les bases

## 📌 Définition
Docker permet d'empaqueter une application avec toutes ses dépendances dans un conteneur, garantissant qu'elle tourne de façon identique partout (dev, test, prod).

## 🛠️ Commandes essentielles
```bash
docker build -t mon-image .        # construire une image depuis un Dockerfile
docker run -d -p 8080:80 mon-image # lancer un conteneur en arrière-plan
docker ps                          # lister les conteneurs actifs
docker stop <id>                   # arrêter un conteneur
docker logs <id>                   # voir les logs d'un conteneur
docker exec -it <id> bash          # ouvrir un shell dans un conteneur
```

## 💡 Dockerfile minimal (exemple Python/FastAPI)
```dockerfile
FROM python:3.12-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
```

## 📚 Ressource
[Docker – Get Started](https://docs.docker.com/get-started/)

## ✅ À retenir
Une image = un modèle figé. Un conteneur = une instance en cours d'exécution de cette image. Pertinent pour le déploiement Docker Compose sur VPS évoqué pour `officerail_be`.
