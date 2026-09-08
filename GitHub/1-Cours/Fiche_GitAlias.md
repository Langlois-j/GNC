# Fiche : Alias Git utiles

## 📌 Définition
Raccourcis configurables pour gagner du temps sur les commandes Git fréquentes.

## 🛠️ Configuration
```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.cm "commit -m"
git config --global alias.lg "log --oneline --graph --all --decorate"
```

## 💡 Résultat
```bash
git st     # au lieu de git status
git co main
git cm "fix: correction bug login"
git lg     # historique visuel en une ligne par commit
```

## 💡 Alias avancé utile
```bash
git config --global alias.undo "reset --soft HEAD~1"
# Annule le dernier commit sans perdre les modifications
```

## ✅ À retenir
Les alias sont stockés dans `~/.gitconfig` (ou `C:\Users\<user>\.gitconfig` sous Windows) — à sauvegarder/versionner comme fichier de config perso.
