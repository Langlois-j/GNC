# Fiche 17 : Tkinter — widgets avancés & variables liées

## 🛠️ Autres widgets courants
```python
tkinter.Checkbutton(app, text="Valider", onvalue=5, offvalue=2)
tkinter.Radiobutton(app, text="Selection 1", value=0)
tkinter.Scale(app, orient="horizontal", from_=5, to=10)
tkinter.Spinbox(app, from_=0, to=10)
w_list = tkinter.Listbox(app)
w_list.insert(1, "Eau")
```

## 🛠️ Fenêtres modales (messagebox)
```python
from tkinter import messagebox

messagebox.showerror("Erreur", "Une erreur est survenue")
messagebox.showinfo("Info", "Voici une information")
messagebox.showwarning("Warning", "Ceci est un warning")
messagebox.askquestion("Question", "Aimes-tu Python ?")
messagebox.askretrycancel("Alors...", "Que souhaitez-vous faire ?")
```

## 🛠️ Variables Tkinter (liaison UI ↔ code)
| Variable | Type Python équivalent |
|---|---|
| `StringVar()` | `str` |
| `IntVar()` | `int` |
| `DoubleVar()` | `float` |
| `BooleanVar()` | `bool` |

```python
var_label = tkinter.StringVar()
w_label = tkinter.Label(app, textvariable=var_label)
var_label.set("Bienvenue !")

# Observateur : réagit à chaque changement de la variable
def maj_entry(*args):
    var_label.set(var_entry.get())

var_entry = tkinter.StringVar()
var_entry.trace("w", maj_entry)   # "w" = déclenché à l'écriture
w_entry = tkinter.Entry(app, textvariable=var_entry)
```

## ✅ À retenir
Les variables Tkinter (`StringVar`, `IntVar`...) permettent de **connecter** l'interface graphique au code Python sans manipuler directement chaque widget. `trace("w", fonction)` déclenche automatiquement une fonction à chaque modification de la variable.
