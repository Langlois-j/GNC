# Fiche 05 : Les fonctions

## 📌 Principe
Une fonction est un bloc de code réutilisable qui reçoit des **paramètres** en entrée et peut renvoyer une **valeur** de sortie (`return`).

## 🛠️ Trois façons de déclarer une fonction

### 1. Déclaration classique (`function`)
```javascript
function canDrive(age, pays) {
    if (pays === "FR" && age >= 18) return true;
    if (pays === "US" && age >= 16) return true;
    return false;
}
```
💡 **Hoisting** : une fonction déclarée avec `function` peut être appelée **avant** sa déclaration dans le fichier (le moteur JS la "remonte" automatiquement). Elle est aussi accessible globalement, même déclarée dans un bloc.

### 2. Expression de fonction (dans une constante)
```javascript
const canDrive = function (age, pays) {
    // ...
};
```
⚠️ Pas de hoisting ici : appeler `canDrive()` avant cette ligne lève une erreur. Portée de bloc classique (comme `let`/`const`).

### 3. Fonction fléchée (arrow function)
```javascript
const canDrive = (age, pays) => {
    // ...
};

// Retour direct si le corps ne contient qu'un `return` :
const isPair = (n) => n % 2 === 0;
```

## 📌 Quand utiliser quelle syntaxe ?
- Fonction utilisable **globalement partout** → `function nom() {}`
- Fonction locale à un bloc/une condition → constante + `function` ou fléchée
- Une seule instruction à retourner → fléchée (plus concis)

## ⚠️ Le mot-clé `this`
Son comportement change radicalement selon la syntaxe :
```javascript
function maFonction() { console.log(this); }
maFonction();                 // this = objet global (window)
maFonction.call(3);           // this = 3 (on peut l'imposer avec .call())

const obj = {
    prenom: "John",
    direBonjour: function () { console.log(this.prenom); }
};
obj.direBonjour();            // this = obj → "John"

const arrowFn = () => console.log(this);
arrowFn();                    // this = TOUJOURS le contexte global, jamais modifiable
```
✅ Règle pratique : dans un objet (méthode), utiliser `function` classique pour accéder à `this`. Pour tout le reste, la fonction fléchée est plus prévisible (beaucoup de développeurs évitent `this` autant que possible).

## 🛠️ Paramètres & valeurs par référence
```javascript
function ajouterPoint(notes) {
    notes[0] = notes[0] + 1;   // modifie le tableau original (objet = référence)
}
```
⚠️ Modifier un **objet/tableau** reçu en paramètre modifie l'original (même mécanisme que la fiche Listes). Modifier un paramètre simple (nombre, chaîne) ne modifie **pas** la variable d'origine.

## 🛠️ Callback — passer une fonction en paramètre
```javascript
function isPair(n, fn) {
    if (n % 2 === 0) fn(n);
}

isPair(4, function (nombre) {
    console.log("Mon nombre est pair :", nombre);
});
```
Une fonction passée en paramètre d'une autre fonction s'appelle un **callback** (souvent nommée `cb`).

## 🛠️ Commentaires
```javascript
// commentaire sur une ligne
/* commentaire
   sur plusieurs lignes */
```

## ✅ À retenir
`function` = hoisting + portée globale + `this` dynamique. Fonction fléchée = pas de hoisting + `this` figé sur le contexte global + syntaxe courte pour un simple `return`. Les deux sont interchangeables tant qu'on n'a pas besoin de `this`.
