# Fiche : Git Rebase vs Merge

## 📌 Définition
Deux façons d'intégrer les changements d'une branche dans une autre, avec un impact différent sur l'historique.

## 🛠️ Merge
```bash
git checkout main
git merge feature-branch
```
Crée un commit de fusion, conserve l'historique complet (y compris les branches).

## 🛠️ Rebase
```bash
git checkout feature-branch
git rebase main
```
Rejoue les commits de la branche par-dessus `main`, produit un historique linéaire (sans commit de fusion).

## ⚠️ Règle d'or
**Ne jamais rebaser une branche déjà partagée/pushée** avec d'autres personnes → réécrit l'historique et casse les clones existants.

## 💡 Quand utiliser quoi
| Situation | Choix |
|---|---|
| Branche perso, pas encore pushée | Rebase (historique propre) |
| Branche partagée en équipe | Merge (sécurité) |
| Nettoyer avant une PR | `rebase -i` (interactif) |

## ✅ À retenir
Rebase = historique propre mais dangereux si partagé. Merge = plus sûr, historique plus "bruyant".
