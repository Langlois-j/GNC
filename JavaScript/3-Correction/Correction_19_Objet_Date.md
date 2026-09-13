# Correction 19 : L'objet `Date`

## Exercice 1
```javascript
function addHours(date, n) {
    const nouvelleDate = new Date(date.getTime());   // clone pour ne pas muter l'original
    nouvelleDate.setHours(nouvelleDate.getHours() + n);
    return nouvelleDate;
}

const now = new Date();
const plusTard = addHours(now, 5);
console.log(now);      // inchangé
console.log(plusTard); // +5 heures
```

## Exercice 2
```javascript
function calculerAge(dateNaissance) {
    const aujourdHui = new Date();
    let age = aujourdHui.getFullYear() - dateNaissance.getFullYear();

    const moisDiff = aujourdHui.getMonth() - dateNaissance.getMonth();
    const jourDiff = aujourdHui.getDate() - dateNaissance.getDate();

    if (moisDiff < 0 || (moisDiff === 0 && jourDiff < 0)) {
        age--;   // l'anniversaire de cette année n'est pas encore passé
    }
    return age;
}
```
⚠️ Piège évité : soustraire simplement les années (`aujourdHui.getFullYear() - dateNaissance.getFullYear()`) donne un âge faux tant que l'anniversaire de l'année en cours n'est pas passé — il faut comparer aussi le mois, puis le jour en cas d'égalité de mois.

## Exercice 3
```javascript
function estWeekend(date) {
    const jour = date.getDay();   // 0 = dimanche, 6 = samedi
    return jour === 0 || jour === 6;
}
```
📌 `getDay()` suit la convention anglo-saxonne : la semaine commence à dimanche (`0`), pas à lundi.

## Exercice 4
```javascript
function tempsRestant(dateCible) {
    const diffSecondes = (dateCible.getTime() - Date.now()) / 1000;

    const jours = diffSecondes / (60 * 60 * 24);
    if (jours >= 1) {
        return `Dans ${Math.floor(jours)} jours`;
    }

    const heures = diffSecondes / (60 * 60);
    if (heures >= 1) {
        return `Dans ${Math.floor(heures)} heures`;
    }

    const minutes = diffSecondes / 60;
    return `Dans ${Math.floor(minutes)} minutes`;
}
```
📌 On part de la plus grande unité (jours) et on redescend : dès qu'une unité donne un résultat `>= 1`, c'est celle-là qu'on affiche. `Math.floor` évite d'afficher des décimales ("Dans 2.7 jours").
