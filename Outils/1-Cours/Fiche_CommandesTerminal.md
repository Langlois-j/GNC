# Fiche : Terminal — commandes utiles au quotidien

## 📌 Navigation & fichiers
```bash
ls -la          # lister avec détails et fichiers cachés
cd -             # revenir au dossier précédent
pwd              # afficher le chemin courant
mkdir -p a/b/c   # créer des dossiers imbriqués en une commande
```

## 📌 Recherche
```bash
grep -r "texte" .          # rechercher du texte récursivement
find . -name "*.py"        # trouver des fichiers par motif
```

## 📌 Processus
```bash
ps aux | grep python   # lister les process Python en cours
kill -9 <PID>           # forcer l'arrêt d'un process
```

## 💡 Astuce productivité
```bash
history | grep git   # retrouver une ancienne commande git dans l'historique
!!                    # rejouer la dernière commande
```

## ✅ À retenir
Combiner `grep`, `find` et les pipes (`|`) permet de traiter la majorité des besoins de recherche/filtrage sans quitter le terminal.
