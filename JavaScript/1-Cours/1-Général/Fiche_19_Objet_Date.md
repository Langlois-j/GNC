# Fiche 19 : L'objet `Date`

## 📌 Représentation interne
JavaScript n'a qu'un seul objet pour représenter les dates : `Date`. En interne, une date est stockée comme un **timestamp** : le nombre de millisecondes écoulées depuis le **1er janvier 1970 00:00 UTC** (point de référence arbitraire mais standard).
💡 Une API plus moderne, `Temporal`, est en cours de développement mais encore trop peu supportée pour être utilisée aujourd'hui — `Date` reste la référence universelle.

## 🛠️ Créer une date
```javascript
new Date();                        // date/heure actuelle
new Date(1000);                    // 1000 ms après le 1er janvier 1970 UTC
new Date("2022-10-07T16:00:00Z");  // à partir d'une chaîne au format ISO 8601
new Date(2022, 0, 1);              // année, mois, jour, [heures, minutes, secondes, ms]
```
⚠️ **Piège important** : le mois est un **index qui commence à 0** (`0` = janvier, `11` = décembre) — pas le numéro habituel du mois.

## 🛠️ Dépassement de valeur toléré
`Date` accepte des valeurs "hors plage" et recalcule automatiquement :
```javascript
new Date(2022, 13, 1);   // mois 13 (hors 0-11) → devient mars 2023
new Date(2022, 0, 32);   // 32 janvier → devient le 1er février 2022
```
💡 Ce comportement, qui peut surprendre au premier abord, est en réalité pratique pour des calculs de type "ajouter N jours" (voir plus bas).

## 🛠️ Fuseau horaire : UTC vs heure locale
Une date est toujours stockée en UTC en interne, mais affichée par défaut dans le fuseau horaire de la machine qui exécute le code (le navigateur pour le client, le serveur pour le back-end).
```javascript
const d = new Date();
d.getTimezoneOffset();   // décalage en minutes entre l'heure locale et UTC
```

## 🛠️ Récupérer des informations
| Méthode | Retourne |
|---|---|
| `getFullYear()` | Année |
| `getMonth()` | Mois (index 0-11) |
| `getDate()` | Jour du mois (1-31) |
| `getDay()` | Jour de la semaine — **0 = dimanche**, 1 = lundi... |
| `getHours()` / `getMinutes()` / `getSeconds()` / `getMilliseconds()` | Heure, minute, seconde, milliseconde |

Chaque méthode a son équivalent en UTC : `getUTCFullYear()`, `getUTCHours()`, etc. — pour lire la valeur indépendamment du fuseau horaire local.

## 🛠️ Modifier une date : les setters
```javascript
const d = new Date();
d.setDate(15);        // change le jour du mois
d.setMonth(2);        // change le mois (index 0-11)
d.setFullYear(2025);  // change l'année
```
⚠️ Les setters **modifient l'objet en place** (mutation) plutôt que de renvoyer une nouvelle date — point important pour la suite de la fiche.

## 🛠️ Formater une date en chaîne
```javascript
const d = new Date();
d.toISOString();          // "2022-10-07T16:00:00.000Z" — standard ISO, utile pour échanger avec un serveur
d.toUTCString();          // format utilisé notamment pour les cookies / flux RSS
d.toLocaleDateString();   // format adapté à la langue de l'utilisateur (ex : "07/10/2022" en français)
d.toLocaleDateString("en-US");   // "10/7/2022" — locale explicite
d.toLocaleString();       // date ET heure, selon la locale
d.toLocaleTimeString();   // uniquement l'heure, selon la locale
```
📌 Les méthodes `toLocale...` sont en réalité des raccourcis vers l'objet `Intl`, plus complet et dédié à l'internationalisation (dates, nombres, monnaies...). Pour un formatage plus précis :
```javascript
new Intl.DateTimeFormat(undefined, { dateStyle: "long" }).format(d);
// "7 octobre 2022" (locale de l'ordinateur, undefined = auto)
new Intl.DateTimeFormat(undefined, { dateStyle: "long", timeStyle: "long" }).format(d);
```

## 🛠️ Méthodes statiques utiles
```javascript
Date.now();             // timestamp actuel (nombre de ms), sans créer d'objet Date
Date.parse("2022-10-07T16:00:00Z");   // convertit une chaîne en timestamp
Date.UTC(2022, 0, 1);   // comme le constructeur, mais renvoie un timestamp interprété en UTC
```

## 🛠️ Exercice guidé : ajouter des jours sans muter l'original
Une première approche naïve, mais fautive :
```javascript
function addDays(date, n) {
    date.setDate(date.getDate() + n);   // ⚠️ mute directement l'objet reçu en paramètre !
    return date;
}

const today = new Date();
const tomorrow = addDays(today, 1);
// today a aussi été décalé d'un jour : effet de bord inattendu
```
⚠️ **Piège classique** : les setters de `Date` mutent l'objet. Une fonction qui manipule des dates devrait être **pure** (ne pas modifier ce qu'elle reçoit en paramètre). Solution : cloner la date avant de la modifier.
```javascript
function addDays(date, n) {
    const nouvelleDate = new Date(date.getTime());   // clone : nouvel objet, même timestamp
    nouvelleDate.setDate(nouvelleDate.getDate() + n);
    return nouvelleDate;
}

const today = new Date();
const tomorrow = addDays(today, 1);
// today reste inchangé, tomorrow est bien le lendemain
```
💡 Le dépassement de valeur toléré par `Date` (vu plus haut) rend `setDate(date.getDate() + n)` fiable même en fin de mois : `setDate(32)` en janvier bascule automatiquement en février.

## 🛠️ Généraliser : ajouter n'importe quelle unité
```javascript
const YEARS = 0, MONTHS = 1, DAYS = 2, HOURS = 3, MINUTES = 4, SECONDS = 5;

function addInterval(date, n, unite) {
    const parts = [
        date.getFullYear(), date.getMonth(), date.getDate(),
        date.getHours(), date.getMinutes(), date.getSeconds(),
    ];
    parts[unite] += n;
    return new Date(...parts);
}

addInterval(new Date(), 3, MONTHS);   // +3 mois
addInterval(new Date(), 2, YEARS);    // +2 ans
```
📌 Plutôt qu'un `switch` avec un cas par unité, on découpe la date en tableau ordonné (année, mois, jour...) et on incrémente directement l'élément à l'index voulu — un peu moins de code à maintenir pour le même résultat.

## 🛠️ Aller plus loin : un intervalle multi-unités
```javascript
function addInterval(date, intervalle) {
    const parts = [
        date.getFullYear(), date.getMonth(), date.getDate(),
        date.getHours(), date.getMinutes(), date.getSeconds(),
    ];
    for (const [unite, valeur] of Object.entries(intervalle)) {
        parts[unite] += valeur;
    }
    return new Date(...parts);
}

addInterval(new Date(), { [MONTHS]: 2, [DAYS]: 1 });   // +2 mois ET +1 jour en un seul appel
```
💡 `Object.entries(objet)` renvoie un tableau de paires `[clé, valeur]`, ce qui permet ici de traiter plusieurs unités en une seule boucle plutôt que d'enchaîner les appels.

## 🛠️ Calculer une différence entre deux dates
```javascript
const dansLeFutur = addInterval(new Date(), 3, DAYS);
const secondesRestantes = (dansLeFutur.getTime() - Date.now()) / 1000;
const joursRestants = secondesRestantes / (60 * 60 * 24);
```
📌 `getTime()` (ou `Date.now()`) renvoie des millisecondes ; diviser par `1000` donne des secondes, puis par le nombre de secondes dans l'unité voulue (jour, heure...) pour obtenir une différence lisible — utile par exemple pour afficher "dans 3 jours".

## ✅ À retenir
Une date est un timestamp (ms depuis le 1er janvier 1970 UTC). Le mois est indexé à partir de 0. Les setters (`setDate`, `setMonth`...) **mutent** l'objet — cloner avec `new Date(date.getTime())` avant de modifier si on veut une fonction pure. `toLocaleDateString()`/`Intl.DateTimeFormat` pour un affichage adapté à l'utilisateur, `toISOString()` pour échanger avec un serveur.
