# Extension VS Code — Prévisualisation Markdown enrichie et export PDF

Extension VS Code qui enrichit la prévisualisation Markdown : diagrammes Mermaid, formules KaTeX, mise en page en colonnes et blocs colorés, templates, et export PDF fidèle au rendu.

Projet d'équipe réalisé en L3 Informatique à l'Université de Montpellier (2025–2026).

> Le pilotage de la présentation par gestes de la main (MediaPipe) est dans un dépôt séparé : [lien vers le dépôt gesture-control](https://github.com/laithRahil/NOM-DU-DEPOT)

![Démo](docs/demo.gif)

## Fonctionnalités

- **Mermaid** : les blocs ` ```mermaid ` sont détectés et rendus en SVG directement dans la prévisualisation.
- **KaTeX** : rendu des formules mathématiques.
- **Colonnes et blocs** : syntaxe `:::` pour structurer la mise en page.
- **Templates** : création, modification et suppression de modèles de documents (CRUD).
- **Prévisualisation en direct** : mise à jour à la frappe (`onType`) ou à l'enregistrement (`onSave`), avec scroll synchronisé entre l'éditeur et l'aperçu.
- **Export PDF** : génération d'un PDF identique au rendu (CSS, Mermaid, KaTeX compris).

## Syntaxe des blocs

```markdown
::: COL {l30, c20, r50}     → trois colonnes : 30 % gauche, 20 % centre, 50 % droite
::: ITEM Titre              → cellule dans la colonne courante, avec son titre
::: #de5d5d Titre           → bloc coloré (titre, bordure et fond léger)
```

## Export PDF

Le fichier Markdown est converti en HTML, puis Puppeteer lance un Chrome invisible (headless) qui fait le rendu complet et génère le PDF. Les fichiers temporaires sont ensuite supprimés.

Pour trouver un navigateur, l'extension cherche d'abord Chrome sur le système, puis dans son cache, et ne télécharge un navigateur headless qu'en dernier recours.

## Installation

```bash
git clone https://github.com/laithRahil/projetExtensionVSC.git
cd projetExtensionVSC
npm install
```

Ouvrir le dossier dans VS Code et appuyer sur `F5` pour lancer l'extension dans une fenêtre de développement.

## Technologies

TypeScript, API VS Code, Mermaid, KaTeX, Puppeteer

## Équipe

Laith Rahil · Marc Nasr · Maxime Roche · Gautier Camba
