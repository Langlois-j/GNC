# Prompt : Traiter une fiche GNC à partir d'une transcription

**Répertoire :** `[À COMPLÉTER — ex: C:\Users\langl\source\repos\GNC\JavaScript\1-Cours\1-Général]`
**Fichier :** `[À COMPLÉTER — ex: Fiche_13_Sucre_syntaxique.md]`

---

Regarde le fichier ci-dessus via le MCP filesystem Windows. Il contient soit une transcription brute de vidéo (avec horodatages type `0:00`, `1:23`...), soit un simple placeholder (titre + lien vidéo + section "Transcription" vide).

## Si le fichier est vide / placeholder
Dis-le moi simplement, ne fabrique aucun contenu à partir de rien.

## Si le fichier contient une vraie transcription
1. **Lis-la intégralement** avant d'écrire quoi que ce soit.
2. **Corrige les erreurs de transcription automatique** que tu repères (mots mal retranscrits, opérateurs mal interprétés, casse incorrecte comme `isNan`/`isNaN`, etc.) — ne les reproduis pas telles quelles.
3. **Réécris le contenu en fiche mémoire concise**, dans le même style que les fiches déjà présentes dans `GNC` :
   - `📌` pour les définitions/principes
   - `🛠️` pour la syntaxe et les exemples de code
   - `⚠️` pour les pièges à éviter
   - `💡` pour les astuces
   - `✅ À retenir` en conclusion
   - Tableaux Markdown quand plusieurs éléments sont comparables (méthodes, opérateurs...)
4. **Écrase le fichier** (même nom, même emplacement) avec cette version propre — supprime la transcription brute.
5. **Renomme le fichier** si son nom actuel est un placeholder générique (garde le numéro déjà présent dans le nom, ex: `Fiche_13_...`) pour qu'il soit cohérent avec les autres (`Fiche_XX_TitreCourt.md`).
6. **Crée des exercices** dans `2-Exercice\Exercice_XX_Titre.md` (même numéro que la fiche) — des exercices *nouveaux*, pas une redite de ce qui est déjà résolu dans les projets sources (`PasAPas-JavaScript`, `JS-Apprentissage`, `PythonFormationFERTIG`, etc.) si le sujet y a déjà été traité.
7. **Crée la correction** correspondante dans `3-Correction\Correction_XX_Titre.md`, avec du code commenté et les pièges éventuels signalés.
8. Si la transcription fait référence à des méthodes/notions déjà vues dans une fiche précédente, **fais un lien** vers cette fiche plutôt que de dupliquer l'explication.

## Contraintes de forme
- Tout en français, sauf le code et les mots-clés du langage.
- Rester concis : une fiche doit pouvoir se relire en quelques minutes, pas remplacer la vidéo.
- Ne pas halluciner de contenu qui ne serait pas dans la transcription ni dans les fondamentaux du langage déjà établis dans les fiches précédentes.
- Une fois terminé, fais un court récap (fiche traitée, exercices créés, points de vigilance repérés).