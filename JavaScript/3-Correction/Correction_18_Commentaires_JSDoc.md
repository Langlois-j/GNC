# Correction 18 : Commentaires et JSDoc

## Exercice 1
Problème : chaque commentaire reformule littéralement la ligne juste en dessous (`// on multiplie le prix par 0.9` au-dessus de `prix * 0.9`) — ça n'apporte rien, le code se lit très bien seul. Le seul commentaire qui avait une vraie valeur ("remise supplémentaire liée au programme de fidélité lancé en 2023") est celui qui explique le **pourquoi** du taux `0.95`.
```javascript
function calculerRemise(prix, estMembre) {
    let remise = prix * 0.9;
    if (estMembre) {
        // Remise supplémentaire liée au programme de fidélité lancé en 2023
        remise = remise * 0.95;
    }
    return remise;
}
```

## Exercice 2
```javascript
/**
 * Crée un objet représentant un utilisateur.
 * @param {string} nom
 * @param {number} age
 * @param {boolean} [estActif=true]
 * @returns {{nom: string, age: number, estActif: boolean}}
 */
function creerUtilisateur(nom, age, estActif = true) {
    return { nom, age, estActif };
}
```
💡 `[estActif=true]` (crochets autour du nom) est la notation JSDoc standard pour indiquer qu'un paramètre est optionnel avec une valeur par défaut.

## Exercice 3
```javascript
/**
 * @typedef {object} Utilisateur
 * @property {string} nom
 * @property {number} age
 * @property {boolean} estActif
 */

/**
 * Crée un objet représentant un utilisateur.
 * @param {string} nom
 * @param {number} age
 * @param {boolean} [estActif=true]
 * @returns {Utilisateur}
 */
function creerUtilisateur(nom, age, estActif = true) {
    return { nom, age, estActif };
}

/**
 * Filtre les utilisateurs actifs.
 * @param {Utilisateur[]} utilisateurs
 * @returns {Utilisateur[]}
 */
function listerUtilisateursActifs(utilisateurs) {
    return utilisateurs.filter((u) => u.estActif);
}
```
📌 Le `@typedef` est défini une seule fois puis réutilisé comme n'importe quel autre type (`Utilisateur`, `Utilisateur[]`...) dans toutes les fonctions qui le manipulent.

## Exercice 4
```javascript
/**
 * Récupère un utilisateur depuis l'API par son id.
 * @param {number} id
 * @returns {Promise<Utilisateur>}
 */
async function fetchUtilisateur(id) {
    const r = await fetch(`https://jsonplaceholder.typicode.com/users/${id}`);
    return await r.json();
}
```
📌 Même si la fonction est `async` et manipule une `Promise` en interne, le type documenté est bien `Promise<Utilisateur>` — c'est ce que reçoit l'appelant, pas ce qui se passe à l'intérieur de la fonction.
