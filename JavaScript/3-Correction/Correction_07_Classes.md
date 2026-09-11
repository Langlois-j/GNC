# Correction 07 : Les classes — formes géométriques

## Exercice 1 & 2 & 3
```javascript
class Rectangle {
    constructor(width, height) {
        this.width = width;
        this.height = height;
    }

    get perimeter() {
        return (this.width + this.height) * 2;
    }

    get isValid() {
        return this.width > 0 && this.height > 0;
    }

    isBiggerThan(shape) {
        return this.perimeter > shape.perimeter;
    }
}

class Square extends Rectangle {
    constructor(width) {
        super(width, width);
    }
}

const rect = new Rectangle(20, 10);
const square = new Square(10);

console.log(rect.perimeter);              // 60
console.log(square.perimeter);            // 40
console.log(square.isBiggerThan(rect));   // false
console.log(rect.isBiggerThan(square));   // true
```

## Exercice 4
```javascript
class Book {
    #page = 1;

    constructor(title, pages) {
        this.title = title;
        this.pages = pages;
    }

    get page() {
        return this.#page;
    }

    nextPage() {
        if (this.#page < this.pages) {
            this.#page++;
        }
    }

    close() {
        this.#page = 1;
    }
}

class Library {
    #books = [];

    addBook(book) {
        this.#books.push(book);
    }

    addBooks(books) {
        books.forEach(book => this.addBook(book));   // fonction fléchée : this reste Library
    }

    findBooksByLetter(letter) {
        return this.#books.filter(
            book => book.title[0].toLowerCase() === letter.toLowerCase()
        );
    }
}

const library = new Library();
library.addBooks([
    new Book("Le Seigneur des anneaux", 1200),
    new Book("Sillage", 48),
]);
console.log(library.findBooksByLetter("s"));   // les 2 livres
console.log(library.findBooksByLetter("z"));   // []
```
