# Correction 04 : Structures de données

## Exercice 1
```python
phrase = input("Entre une phrase : ")
print(phrase.upper())
print("Nombre de 'e' :", phrase.lower().count("e"))
```

## Exercice 2
```python
courses = ["Pain", "Lait", "Oeufs", "Beurre", "Fromage"]
courses.append("Pommes")
courses.remove("Lait")
courses.sort()
print(courses)
```

## Exercice 3
```python
def coordonnees():
    return (12, 34)

x, y = coordonnees()
print("x =", x, "y =", y)
```

## Exercice 4
```python
contact = {"nom": "Julien", "telephone": "0600000000", "email": "julien@mail.fr"}
contact["ville"] = "Lille"

for cle, valeur in contact.items():
    print("{} : {}".format(cle, valeur))
```

## Exercice 5
```python
utilisateurs = [
    {"nom": "Alice", "age": 34},
    {"nom": "Bob", "age": 41},
    {"nom": "Chloe", "age": 28},
]

plus_age = utilisateurs[0]
for u in utilisateurs:
    if u["age"] > plus_age["age"]:
        plus_age = u

print("Le plus âgé est :", plus_age["nom"])
```
