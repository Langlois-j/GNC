# Correction 06 : Fonctions — mise en pratique avancée

## Exercice 1
```javascript
function isPalindrome(str) {
    const reversed = str.split("").reverse().join("");
    return str.toLowerCase() === reversed.toLowerCase();
}

console.log(isPalindrome("kayak"));   // true
console.log(isPalindrome("Kayak"));   // true
console.log(isPalindrome("bonjour")); // false
```

## Exercice 2
```javascript
const etudiants = [
    { nom: "John", notes: [12, 15, 16, 12, 15] },
    { nom: "Jane", notes: [18, 15, 17, 16, 17] },
    { nom: "Manon", notes: [19, 12, 18, 18, 17] },
];

function moyenne(notes) {
    let somme = 0;
    for (const note of notes) {
        somme += note;
    }
    return somme / notes.length;
}

function compareEtudiants(a, b) {
    return b.moyenne - a.moyenne;
}

for (const etudiant of etudiants) {
    etudiant.moyenne = moyenne(etudiant.notes);
    etudiant.best = Math.max(...etudiant.notes);
    etudiant.worst = Math.min(...etudiant.notes);
}

etudiants.sort(compareEtudiants);

function formatEtudiant(etudiant) {
    return `${etudiant.nom} avec une moyenne de ${etudiant.moyenne} (meilleure note: ${etudiant.best}, pire note: ${etudiant.worst})`;
}

console.log(`Top 3 étudiants :
1. ${formatEtudiant(etudiants[0])}
2. ${formatEtudiant(etudiants[1])}
3. ${formatEtudiant(etudiants[2])}`);
```

## Exercice 3
```javascript
const phrase = "Le chat mange, le chien mange, et le chat dort.";

const ignore = [",", ".", "!", "?"];
let cleanPhrase = phrase.toLowerCase();
for (const caractere of ignore) {
    cleanPhrase = cleanPhrase.replaceAll(caractere, "");
}

const mots = cleanPhrase.split(" ");
const frequencies = {};

for (const mot of mots) {
    if (mot === "") continue;
    if (frequencies[mot]) {
        frequencies[mot]++;
    } else {
        frequencies[mot] = 1;
    }
}

const tableauFrequences = [];
for (const mot in frequencies) {
    tableauFrequences.push({ mot: mot, count: frequencies[mot] });
}
tableauFrequences.sort((a, b) => b.count - a.count);

console.log(`Les mots les plus fréquents sont : "${tableauFrequences[0].mot}", "${tableauFrequences[1].mot}", "${tableauFrequences[2].mot}"`);
```
