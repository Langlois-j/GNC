# Fiche : Commits conventionnels (Conventional Commits)

## 📌 Définition
Convention de nommage des commits pour un historique lisible et exploitable automatiquement (changelogs, versioning sémantique).

## 🛠️ Format
```
<type>(<scope optionnel>): <description>

[corps optionnel]

[footer optionnel]
```

## 💡 Types courants
| Type | Usage |
|---|---|
| `feat` | Nouvelle fonctionnalité |
| `fix` | Correction de bug |
| `docs` | Documentation uniquement |
| `refactor` | Refactorisation sans changement de comportement |
| `test` | Ajout/modification de tests |
| `chore` | Tâches diverses (config, dépendances) |

## 💡 Exemples
```bash
git commit -m "feat(auth): ajout de la connexion via OAuth"
git commit -m "fix(api): correction du timeout sur /planning"
git commit -m "docs: mise à jour du README d'installation"
```

## ✅ À retenir
Très utile sur un projet long (comme `officerail_be`) pour retrouver rapidement l'historique des changements par type.
