# Fiche : .gitignore — astuces

## 📌 Définition
Fichier listant les fichiers/dossiers que Git doit ignorer (ne jamais suivre ni proposer au commit).

## 🛠️ Syntaxe de base
```gitignore
# Commentaire
node_modules/
*.log
.env
__pycache__/
.claude/
```

## 💡 Astuces pratiques
```gitignore
# Ignorer un fichier partout dans l'arborescence
**/config.local.json

# Ignorer tout un dossier sauf un fichier précis
build/*
!build/.gitkeep

# Ignorer les fichiers par extension
*.pyc
*.tmp
```

## 💡 Si un fichier est déjà suivi par erreur
```bash
git rm -r --cached nom_du_fichier_ou_dossier
git commit -m "chore: retrait du fichier du suivi git"
```
Ajouter la règle dans `.gitignore` seule ne suffit pas si le fichier est déjà commité.

## 💡 Ressource
[gitignore.io](https://www.toptal.com/developers/gitignore) génère des `.gitignore` prêts à l'emploi par langage/IDE.

## ✅ À retenir
Toujours créer le `.gitignore` **avant** le premier commit d'un projet pour éviter ce genre de rattrapage.
