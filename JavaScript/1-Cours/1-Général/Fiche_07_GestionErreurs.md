# Fiche 07 : Gestion des erreurs (exceptions)

## 📌 Principe
Les exceptions permettent de signaler qu'une donnée reçue est invalide, et d'arrêter (ou de gérer) l'exécution en conséquence.

## 🛠️ Lever une erreur avec `throw`
```javascript
class Rectangle {
    constructor(largeur, hauteur) {
        if (largeur <= 0 || hauteur <= 0) {
            throw new Error("Impossible d'avoir une forme géométrique avec des dimensions négatives");
        }
        this.largeur = largeur;
        this.hauteur = hauteur;
    }
}

new Rectangle(-10, 20);   // ❌ lève une erreur, coupe immédiatement l'exécution du script
```
⚠️ Par défaut, une erreur non gérée **stoppe tout le script** : aucune ligne après le `throw` ne sera exécutée (contrairement à un simple `return`).

## 🛠️ Capturer une erreur avec try / catch
```javascript
try {
    const largeur = parseInt(prompt("Largeur ?"), 10);
    const hauteur = parseInt(prompt("Hauteur ?"), 10);
    const rect = new Rectangle(largeur, hauteur);
    console.log("Périmètre :", (rect.largeur + rect.hauteur) * 2);
} catch (e) {
    console.log("Impossible de construire le rectangle :", e.message);
}
```
- `try { }` : code potentiellement risqué
- `catch (e) { }` : exécuté si **n'importe quelle** instruction du `try` lève une erreur
- `e` (ou `error`) est un objet avec (au moins) une propriété `.message`

💡 `parseInt(valeur, base)` convertit une chaîne en entier dans la base indiquée (10 = décimal) — alternative à `Number(valeur) * 1`.

## 🛠️ Re-lancer une erreur plus explicite (rethrow)
```javascript
function promptRectangle() {
    const largeur = parseInt(prompt("Largeur ?"), 10);
    const hauteur = parseInt(prompt("Hauteur ?"), 10);
    try {
        return new Rectangle(largeur, hauteur);
    } catch (e) {
        throw new Error("Entrée utilisateur invalide", { cause: e });
    }
}
```
Le second paramètre `{ cause: e }` de `Error` conserve l'erreur d'origine — utile pour remonter à la source du problème sans perdre l'erreur métier plus lisible.

## 🛠️ Erreurs personnalisées
```javascript
class PromptError extends Error {
    // hérite de tout le comportement standard d'Error
}

function promptRectangle() {
    try {
        // ...
    } catch (e) {
        throw new PromptError("Entrée utilisateur invalide", { cause: e });
    }
}

try {
    promptRectangle();
} catch (e) {
    if (e instanceof PromptError) {
        console.log("Erreur de saisie utilisateur :", e.message);
    } else {
        console.log("Erreur classique :", e.message);
    }
}
```
`instanceof` permet de distinguer le **type** d'erreur rencontré et de réagir différemment selon le cas (utile côté serveur : erreur 404, erreur de validation, etc.).

## ✅ À retenir
1. Levez une erreur **le plus tôt possible** dans le code (dès qu'une donnée invalide est détectée), pas plus tard quand elle causerait un bug difficile à tracer.
2. Ne capturez (`try/catch`) que si vous avez une vraie solution de secours à proposer — sinon, laissez le script planter, c'est plus sûr qu'un état invalide silencieux.
3. Les erreurs personnalisées et `instanceof` deviennent surtout utiles sur des projets plus avancés (API/serveur) ; pour les premiers algorithmes, un simple `try/catch` suffit.
