# Correction 05 : Tkinter

## Exercice 1
```python
import tkinter
app = tkinter.Tk()
app.title("Mon application")

screen_x = app.winfo_screenwidth()
screen_y = app.winfo_screenheight()
pos_x = (screen_x // 2) - 200
pos_y = (screen_y // 2) - 150
app.geometry(f"400x300+{pos_x}+{pos_y}")

app.mainloop()
```

## Exercice 2
```python
import tkinter
app = tkinter.Tk()

entry = tkinter.Entry(app, width=40)
entry.pack(pady=10)

label = tkinter.Label(app, text="")
label.pack()

def afficher():
    label.configure(text=entry.get())

btn = tkinter.Button(app, text="Afficher", command=afficher)
btn.pack(pady=10)

app.mainloop()
```

## Exercice 3
```python
import tkinter
app = tkinter.Tk()

var_texte = tkinter.StringVar()

def maj_label(*args):
    label.configure(text=var_texte.get())

entry = tkinter.Entry(app, textvariable=var_texte, width=40)
entry.pack(pady=10)
var_texte.trace("w", maj_label)

label = tkinter.Label(app, text="")
label.pack()

app.mainloop()
```

## Exercice 4
```python
import tkinter
from tkinter import messagebox

app = tkinter.Tk()

def quitter():
    reponse = messagebox.askquestion("Confirmation", "Voulez-vous vraiment quitter ?")
    if reponse == "yes":
        app.destroy()

btn_quitter = tkinter.Button(app, text="Quitter", command=quitter)
btn_quitter.pack(pady=10)

app.mainloop()
```
