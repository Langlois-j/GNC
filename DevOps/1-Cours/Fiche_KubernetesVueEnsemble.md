# Fiche : Kubernetes — vue d'ensemble

## 📌 Définition
Kubernetes (K8s) est un orchestrateur de conteneurs : il gère automatiquement le déploiement, la mise à l'échelle et la disponibilité d'applications conteneurisées sur un ensemble de machines (cluster).

## 🛠️ Concepts clés
| Terme | Définition |
|---|---|
| **Cluster** | Ensemble de machines (nodes) qui exécutent les applications |
| **Pod** | Plus petite unité déployable, contient un ou plusieurs conteneurs |
| **Deployment** | Décrit combien de répliques d'un pod doivent tourner |
| **Service** | Expose un ensemble de pods sur le réseau, avec une IP stable |
| **kubectl** | CLI officielle pour piloter un cluster Kubernetes |

## 🛠️ Commandes de base
```bash
kubectl get pods                  # lister les pods
kubectl get nodes                 # lister les nœuds du cluster
kubectl apply -f deployment.yaml  # appliquer une configuration
kubectl logs <pod>                # voir les logs d'un pod
kubectl describe pod <pod>        # détails/diagnostic d'un pod
```

## 📚 Ressources
- [Kubernetes Basics (tutoriel interactif officiel)](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
- [Killercoda](https://killercoda.com/) — pratiquer dans un vrai cluster, dans le navigateur

## ✅ À retenir
Docker = créer/exécuter un conteneur. Kubernetes = orchestrer des dizaines/centaines de conteneurs à grande échelle. Pertinent si `officerail_be` grandit au-delà d'un simple VPS avec Docker Compose.
