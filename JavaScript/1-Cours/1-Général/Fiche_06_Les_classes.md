# Fiche 06 : Les classes (POO en JavaScript)

## 📌 Le système de prototype
En JavaScript, chaque objet a un **prototype** : un autre objet dont il hérite les méthodes. Quand on accède à une propriété/méthode, le moteur JS cherche d'abord sur l'objet lui-même, puis remonte la **chaîne de prototypes** jusqu'à la trouver.
```javascript
Object.getPrototypeOf(maChaine);   // affiche le prototype String (split, toUpperCase...)
```
C'est ce mécanisme qui permet à toutes les chaînes de caractères d'avoir accès à `.split()`, `.toUpperCase()`, etc. sans qu'on les redéfinisse à chaque fois.

## 🛠️ Créer sa propre classe
```javascript
class Student {
    ecole = "Jules Ferry";   // propriété par défaut, injectée dans chaque instance

    constructor(prenom, nom) {
        this.firstName = prenom;
        this.lastName = nom;
    }

    setNotes(notes) {
        this._notes = notes;   // convention _ : propriété "interne", pas censée être utilisée dehors
    }

    canPass() {
        return moyenne(this._notes) >= 10;
    }
}

const john = new Student("John", "Do");
```
- `constructor` : méthode spéciale, appelée automatiquement à la création (`new`)
- Dans une classe, pas besoin du mot-clé `function` devant les méthodes
- `this` référence l'instance en cours de construction/utilisation

## 🛠️ Getters et Setters
Permettent d'accéder à une propriété calculée avec une syntaxe simple (`objet.propriete` au lieu de `objet.getPropriete()`).
```javascript
class Student {
    // ...
    set notes(v) {
        if (Array.isArray(v)) {
            this._notes = v;
        }
    }
    get notes() {
        return this._notes;
    }
    get name() {
        return `${this.firstName} ${this.lastName}`;
    }
}

john.notes = [15, 18, 12];   // appelle le setter automatiquement
console.log(john.name);       // appelle le getter automatiquement
```
⚠️ Piège : nommer le setter/getter **exactement** comme la propriété interne (`notes`/`notes`) crée une boucle infinie (`Maximum call stack size exceeded`). D'où la convention `_notes` pour la valeur réelle stockée.

## 🛠️ Propriétés et méthodes statiques
Disponibles directement sur la classe, pas sur les instances.
```javascript
class Student {
    static moyenneMinimale = 10;
    static hello() {
        console.log("Bonjour");
    }
}

Student.hello();               // appel direct sur la classe
console.log(Student.moyenneMinimale);
```

## 🛠️ Héritage (`extends` / `super`)
```javascript
class SuperStudent extends Student {
    constructor(prenom, nom, notes) {
        super(prenom, nom);      // appelle le constructeur parent
        this._notes = notes;
    }

    canPass() {
        return true;   // écrase (override) le comportement du parent
    }

    get name() {
        return "Super " + super.name;   // super.xxx = accès à la version parente
    }
}
```
- `extends` : la classe fille hérite de tout ce qui est dans le prototype parent
- `super(...)` dans le constructeur : appelle le constructeur de la classe parente
- `super.methode()` : permet de réutiliser la logique parente tout en l'enrichissant

## 🛠️ Propriétés vraiment privées (`#`)
```javascript
class Student {
    #secret = "hello";   // # = privé, inaccessible même en lecture depuis l'extérieur
}

john.#secret;   // ❌ SyntaxError en dehors de la classe
```
💡 Syntaxe récente, encore peu utilisée dans le code qu'on peut croiser — la convention `_propriete` (privé "par accord tacite", non bloqué techniquement) reste plus répandue.

## ✅ À retenir
1. Une classe = un prototype personnalisé + un constructeur qui initialise les propriétés propres à chaque instance.
2. `static` = sur la classe elle-même, pas sur les objets créés.
3. `extends`/`super` permettent de réutiliser et d'étendre le comportement d'une classe parente sans dupliquer le code.
4. La vraie difficulté n'est pas la syntaxe des classes, mais de savoir **comment découper** son problème en classes pertinentes.
