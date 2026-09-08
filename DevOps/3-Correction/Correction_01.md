# Correction : Docker & Kubernetes

## Exercice 1
```dockerfile
FROM node:20-slim
WORKDIR /app
COPY package*.json .
RUN npm install
COPY . .
EXPOSE 3000
CMD ["node", "server.js"]
```

## Exercice 2
a) **Vrai** — une image est un modèle réutilisable, on peut en lancer autant de conteneurs qu'on veut.
b) **Faux** — `docker ps` liste les conteneurs en cours d'exécution (ajouter `-a` pour voir aussi les arrêtés). `docker images` liste les images.
c) **Vrai** — tant que le conteneur n'est pas supprimé (`docker rm`), son état est conservé et il peut être relancé avec `docker start`.

## Exercice 3
1. `kubectl` — CLI pour piloter le cluster
2. `Service` — expose des pods avec une IP stable
3. `Pod` — plus petite unité déployable
4. `Deployment` — décrit le nombre de répliques souhaitées

## Exercice 4
Sur un playground Killercoda "2 nodes", `kubectl get nodes` affichera typiquement 2 nœuds (souvent 1 control-plane + 1 worker, ou 2 nœuds selon le scénario choisi).
