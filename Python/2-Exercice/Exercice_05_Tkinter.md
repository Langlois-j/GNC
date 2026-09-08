# Exercice 05 : Tkinter (interface graphique)

## Exercice 1 — Fenêtre simple
Crée une fenêtre de 400x300, centrée à l'écran, avec pour titre "Mon application".

## Exercice 2 — Label + Entry + Bouton
Ajoute un champ de saisie (`Entry`) et un bouton "Afficher". Au clic, le texte saisi doit s'afficher dans un `Label` situé en dessous.

## Exercice 3 — Variable liée
Reprends l'exercice 2 en utilisant une `StringVar()` liée au `Label` via `textvariable`, avec un observateur `trace("w", ...)` qui met à jour le label **en temps réel** (sans bouton).

## Exercice 4 — Messagebox
Ajoute un bouton "Quitter" qui ouvre une boîte de confirmation (`askquestion`) avant de fermer l'application.
