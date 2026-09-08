# Fiche 07 : Modularité (imports)

## 📌 Les modules sont des fichiers de code à importer

## 🛠️ Syntaxes d'import
```python
import math
res = math.sqrt(25)          # via le nom du module

from math import sqrt        # importe une fonction précise
res = sqrt(25)

from math import *            # importe TOUTES les fonctions (déconseillé, pollue l'espace de noms)

# Import avec alias (utile si arborescence profonde)
import Repertoire1.Repertoire2.Repertoire3.nomModule as nomModule
nomModule.NomFonction()
```

## 🛠️ Importer son propre module
```python
import Modules.premierModule as premierModule

premierModule.direBonjour("Jérémie")
premierModule.direAurevoir()
```

## ✅ À retenir
Un module = un fichier `.py` réutilisable. `as` permet de raccourcir un chemin d'import long. Privilégier `import module` ou `from module import fonction_precise` plutôt que `from module import *`.
