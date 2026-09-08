# Correction : Git — Rebase, Alias, Commits, .gitignore

## Exercice 1
```bash
git checkout feature-login
git rebase main
```
Un rebase est préférable ici car la branche n'est pas partagée : ça évite un commit de fusion inutile et garde un historique linéaire et lisible.

## Exercice 2
```bash
git config --global alias.unstage "reset HEAD"
# Usage : git unstage nom_du_fichier
```

## Exercice 3
```
fix(auth): correction du bug empêchant la connexion OAuth
```

## Exercice 4
```bash
# 1. Ajouter la règle dans .gitignore
echo ".claude/" >> .gitignore

# 2. Retirer le dossier du suivi Git (sans le supprimer du disque)
git rm -r --cached .claude
git commit -m "chore: retrait de .claude du suivi git"
```
