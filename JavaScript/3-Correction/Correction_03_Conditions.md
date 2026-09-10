# Correction 03 : Les conditions

## Exercice 1
```javascript
const anneeActuelle = 2026;
const anneeNaissance = prompt("En quelle année êtes-vous né ?");
const age = anneeActuelle - anneeNaissance;

console.log("Nous vous conseillons le(s) film(s) suivant(s) :");
if (age <= 13) {
    console.log("- Lilo & Stitch");
} else if (age < 18) {
    console.log("- Matrix");
} else {
    console.log("- Evil Dead");
}
```

## Exercice 2
```javascript
const a = prompt("Entrez un premier nombre :");
const b = prompt("Entrez un deuxième nombre :");
const resultat = a * b;

if (isNaN(resultat)) {
    console.log(`L'opération est impossible : ${a} * ${b}`);
} else {
    let signe;
    if (resultat >= 0) {
        signe = "positif";
    } else {
        signe = "negatif";
    }
    console.log(`Le résultat de ${a} * ${b} est ${signe}`);
}
```

## ⚠️ Erreur fréquente
Attention à la casse : c'est **`isNaN`** (avec 2 majuscules N) et non `isNan`. Un mauvais nommage lève une `ReferenceError: isNan is not defined`, à ne pas confondre avec un vrai bug logique.
