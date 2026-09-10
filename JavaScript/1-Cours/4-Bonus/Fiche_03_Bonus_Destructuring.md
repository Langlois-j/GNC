# Fiche : Destructuring (déstructuration)

## 📌 Définition
Extraire rapidement des valeurs d'un objet ou d'un tableau vers des variables.

## 🛠️ Syntaxe - Objets
```javascript
const utilisateur = { nom: "Julien", ville: "Lille" };
const { nom, ville } = utilisateur;

// Renommer une variable
const { nom: prenomUtilisateur } = utilisateur;

// Valeur par défaut
const { pays = "France" } = utilisateur;
```

## 🛠️ Syntaxe - Tableaux
```javascript
const [premier, deuxieme] = [10, 20];

// Ignorer un élément
const [, second] = [1, 2, 3];

// Rest pattern
const [tete, ...reste] = [1, 2, 3, 4];
```

## 💡 Cas d'usage typique en React
```javascript
const { data, isLoading } = useQuery(...);
function MonComposant({ titre, description }) { ... }
```

## ✅ À retenir
Rend le code plus lisible, très utilisé pour extraire des props en React et des réponses d'API.
