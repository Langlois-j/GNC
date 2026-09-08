# Fiche 16 : Tkinter — fenêtre et widgets de base

## 📌 Créer une fenêtre
```python
import tkinter
app = tkinter.Tk()
app.title("Ma première fenêtre")
app.geometry("800x600+100+100")   # largeur x hauteur + position X + position Y
app.mainloop()                     # boucle d'événements (obligatoire, à la fin)
```

## 💡 Centrer la fenêtre à l'écran
```python
screen_x = app.winfo_screenwidth()
screen_y = app.winfo_screenheight()
windows_x, windows_y = 800, 600
position_x = (screen_x // 2) - (windows_x // 2)
position_y = (screen_y // 2) - (windows_y // 2)
app.geometry(f"{windows_x}x{windows_y}+{position_x}+{position_y}")
```

## 🛠️ Widgets de base
```python
label_welcome = tkinter.Label(app, text="Bonjour")
label_welcome.pack()

# Lire / modifier un widget
label_welcome.cget("text")                  # lire la valeur
label_welcome.configure(text="Au revoir")   # modifier la valeur

# Saisie utilisateur
entry_msg = tkinter.Entry(app, width=60)
entry_msg.pack(pady=10)

entry_password = tkinter.Entry(app, width=60, show="*")  # champ mot de passe

# Bouton avec callback
def au_clic():
    print("Vous avez appuyé sur le bouton !")

btn = tkinter.Button(app, text="Valider", command=au_clic)
btn.pack(pady=10)
```

## ✅ À retenir
`pack()` place le widget sur la fenêtre — sans lui, rien ne s'affiche ! Le paramètre `command=` d'un bouton attend une **référence de fonction** (sans parenthèses).
