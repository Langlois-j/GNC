# Fiche : Async/Await

## 📌 Définition
Syntaxe qui permet d'écrire du code asynchrone (Promises) de façon linéaire et lisible, comme du code synchrone.

## 🛠️ Syntaxe
```javascript
async function recupererDonnees() {
  try {
    const reponse = await fetch("https://api.exemple.com/data");
    const donnees = await reponse.json();
    return donnees;
  } catch (erreur) {
    console.error("Erreur :", erreur);
  }
}
```

## 💡 Équivalent avec .then() (ancienne syntaxe)
```javascript
fetch("https://api.exemple.com/data")
  .then(reponse => reponse.json())
  .then(donnees => console.log(donnees))
  .catch(erreur => console.error(erreur));
```

## 💡 Exécuter plusieurs promesses en parallèle
```javascript
const [res1, res2] = await Promise.all([fetch(url1), fetch(url2)]);
```

## ⚠️ Piège courant
`await` ne fonctionne que dans une fonction déclarée `async`. Oublier `try/catch` = erreurs silencieuses non gérées.

## ✅ À retenir
`async/await` = sucre syntaxique au-dessus des Promises, plus lisible pour enchaîner des appels API.
