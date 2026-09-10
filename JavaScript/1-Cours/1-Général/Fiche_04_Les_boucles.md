# Fiche 04 : Les boucles

## 📌 Principe
Une boucle répète un bloc de code tant qu'une condition est vraie (ou pour un nombre défini d'itérations).

## 🛠️ Boucle `while` (tant que)
```javascript
let i = 0;
while (i < 10) {
    console.log("Bonjour", i);
    i = i + 1;   // ou i++
}
```
⚠️ **Danger n°1 : la boucle infinie.** Si la condition ne devient jamais fausse (oubli d'incrémenter, mauvaise variable modifiée...), le navigateur se bloque. En cas de blocage : fermer l'onglet, ou accepter l'invite "un script ralentit la page".

## 🛠️ Boucle `for` (compteur)
```javascript
for (let i = 0; i < 10; i++) {
    console.log("Bonjour", i);
}
```
Structure : `for (initialisation ; condition de sortie ; mise à jour)`. `i++` = raccourci d'incrémentation (`i = i + 1`), `i--` = décrémentation.

### Parcourir un tableau avec `for`
```javascript
const notes = [12, 15, 18, 14];
for (let i = 0; i < notes.length; i++) {
    console.log(notes[i]);
}
```

## 🛠️ `for...in` — parcourt les **clés/index**
```javascript
const notes = [12, 15, 18, 14];
for (const i in notes) {
    console.log(i, notes[i]);   // 0 12 / 1 15 / 2 18 / 3 14
}

const personne = { nom: "John", age: 30 };
for (const cle in personne) {
    console.log(cle, personne[cle]);   // nom John / age 30
}
```
💡 Fonctionne aussi sur une chaîne de caractères (donne les index des lettres).

## 🛠️ `for...of` — parcourt directement les **valeurs**
```javascript
const notes = [12, 15, 18, 14];
for (const note of notes) {
    console.log(note);   // 12 / 15 / 18 / 14
}
```
⚠️ `for...of` ne fonctionne que sur des objets **itérables** (tableaux, chaînes...) — pas sur un objet `{}` classique (erreur "is not iterable").

## 📌 Résumé — quelle boucle choisir ?
| Boucle | Usage |
|---|---|
| `while` | Tant qu'une condition est vraie, nombre d'itérations inconnu à l'avance |
| `for` | Nombre d'itérations connu, ou parcours de tableau par index |
| `for...in` | Parcourir les clés d'un objet ou les index d'un tableau |
| `for...of` | Parcourir directement les valeurs d'un tableau (le plus lisible) |

## 🛠️ `break` — sortir d'une boucle de force
```javascript
while (true) {
    const reponse = Number(prompt("Devine le nombre :"));
    if (reponse === 8) {
        console.log("Bravo, vous avez deviné !");
        break;   // sort immédiatement de la boucle
    }
}
```

## ⚠️ Portée
Comme pour les conditions, une variable déclarée avec `let`/`const` à l'intérieur d'une boucle n'existe pas en dehors de celle-ci.

## ✅ À retenir
Toujours vérifier que la condition de sortie **peut** devenir fausse avant de lancer le code. `for...of` est en général la boucle la plus lisible pour parcourir un tableau quand on n'a pas besoin de l'index.
