# Exercice 18 : Commentaires et JSDoc

## Exercice 1 — Repérer un mauvais commentaire
Voici une fonction commentée. Identifiez ce qui ne va pas dans les commentaires actuels, puis réécrivez-les correctement (un commentaire qui explique le "pourquoi", pas le "quoi").
```javascript
function calculerRemise(prix, estMembre) {
    // on multiplie le prix par 0.9
    let remise = prix * 0.9;
    // si estMembre est vrai
    if (estMembre) {
        // on multiplie encore par 0.95
        remise = remise * 0.95;   // remise supplémentaire liée au programme de fidélité lancé en 2023
    }
    return remise;
}
```

## Exercice 2 — Documenter une fonction simple
Ajoutez une documentation JSDoc complète (description, `@param` typés, `@returns` typé) à cette fonction :
```javascript
function creerUtilisateur(nom, age, estActif = true) {
    return { nom, age, estActif };
}
```

## Exercice 3 — `@typedef` réutilisable
Définissez un type `Utilisateur` (avec `@typedef`/`@property`) correspondant à l'objet renvoyé par `creerUtilisateur` de l'exercice 2, puis utilisez ce type dans la JSDoc de deux fonctions :
- `creerUtilisateur(nom, age, estActif)` → renvoie un `Utilisateur`.
- `listerUtilisateursActifs(utilisateurs)` → prend un tableau d'`Utilisateur` et renvoie un tableau d'`Utilisateur`.

## Exercice 4 — Fonction asynchrone typée
Documentez cette fonction avec JSDoc, y compris le type de retour de la promesse (réutilisez le type `Utilisateur` de l'exercice 3) :
```javascript
async function fetchUtilisateur(id) {
    const r = await fetch(`https://jsonplaceholder.typicode.com/users/${id}`);
    return await r.json();
}
```
