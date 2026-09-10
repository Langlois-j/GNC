# Fiche 02 : Les conditions

## 📌 Afficher en console
```javascript
console.log("Bonjour les gens");   // affiche une valeur/variable dans la console du navigateur
```
💡 Astuce : l'extension VS Code **Live Server** recharge automatiquement la page à chaque sauvegarde.

## 🛠️ Structure if / else if / else
```javascript
if (age >= 18) {
    console.log("Vous êtes majeur");
} else if (age >= 13) {
    console.log("Ado");
} else {
    console.log("Enfant");
}
```

## 📌 Opérateurs de comparaison
| Opérateur | Signification |
|---|---|
| `>` `<` | strictement supérieur / inférieur |
| `>=` `<=` | supérieur ou égal / inférieur ou égal |
| `==` | égal **avec conversion de type** (déconseillé) |
| `===` | égal **strict** (même valeur ET même type) — à utiliser systématiquement |
| `!=` / `!==` | différent (large / strict) |

### ⚠️ Piège : `==` vs `===`
```javascript
"4" == 4     // true  → JS convertit la chaîne en nombre avant de comparer
"4" === 4    // false → types différents (string vs number)

[] == []     // false → deux objets différents en mémoire, même vides
```
✅ Règle : **toujours utiliser `===`**, ne jamais utiliser `==` dans du code écrit à la main.

## 📌 Opérateurs logiques
| Opérateur | Nom | Vrai si... |
|---|---|---|
| `&&` | ET | les deux conditions sont vraies |
| \| \| | OU | au moins une condition est vraie |
| `!` | NON | inverse un booléen |

```javascript
const peutConduireFrance = pays === "FR" && age >= 18;
const peutConduireUSA    = pays === "US" && age >= 16;

if (peutConduireFrance || peutConduireUSA) {
    console.log("Vous avez le droit de conduire");
} else {
    console.log("Vous n'avez pas le droit de conduire");
}
```
💡 Séparer les conditions complexes dans des variables nommées rend le code beaucoup plus lisible.

## 🛠️ Inverser une condition (lois de De Morgan)
- `!(A || B)` équivaut à `!A && !B`
- `!(A && B)` équivaut à `!A || !B`

## 🛠️ Valeurs "truthy" / "falsy"
Une condition n'a pas besoin d'être un booléen strict — JS convertit implicitement (*type coercion*).

**Falsy** (considérées comme fausses) : `false`, `0`, `""` (chaîne vide), `null`, `undefined`, `NaN`
**Truthy** (tout le reste) : chaînes non vides, nombres non nuls (même négatifs), objets/tableaux même vides

## 🛠️ switch / case
Utile pour comparer **une seule variable** à plusieurs valeurs fixes.
```javascript
switch (pays) {
    case "FR":
        console.log("Je suis en France");
        break;
    case "US":
        console.log("Je suis aux États-Unis");
        break;
    default:
        console.log("Pays inconnu");
        break;
}
```
⚠️ Ne pas oublier le `break` sous peine d'exécuter aussi le `case` suivant. En pratique, le `if/else` reste plus utilisé (syntaxe plus légère) ; le `switch` est réservé aux comparaisons d'une seule variable à plusieurs valeurs.

## ✅ À retenir
`===` > `==` (toujours), `&&`/`||`/`!` pour combiner des conditions, parenthèses pour clarifier l'ordre d'évaluation, `switch` seulement quand on compare une variable unique à plusieurs cas.
