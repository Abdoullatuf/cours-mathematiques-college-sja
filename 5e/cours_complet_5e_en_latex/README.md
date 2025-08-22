# Cours de Mathématiques 4e - Structure Modulaire

## Description

Ce cours de mathématiques pour la classe de 4e est organisé en structure modulaire pour faciliter la maintenance et les modifications.

## Structure des fichiers

### Fichier principal
- `main.tex` : Fichier principal contenant toute la configuration LaTeX et incluant tous les chapitres

### Dossier des chapitres
- `chapitres/` : Contient tous les fichiers de chapitres individuels

### Dossier des figures
- `chapitres/figures/` : Contient un sous-dossier pour chaque chapitre
  - `chapitre_01_nombres_relatifs/` : Figures du chapitre 1
  - `chapitre_02_pythagore/` : Figures du chapitre 2
  - etc.

#### Partie I : Nombres et Calculs
- `chapitre_01_nombres_relatifs.tex` : Nombres relatifs (1)
- `chapitre_02_pythagore.tex` : Théorème de Pythagore et sa réciproque
- `chapitre_03_puissances.tex` : Puissances
- `chapitre_04_racines_carrees.tex` : Racines carrées
- `chapitre_05_nombres_premiers.tex` : Nombres premiers et divisibilité

#### Partie II : Organisation et Gestion de Données
- `chapitre_06_proportionnalite.tex` : Proportionnalité
- `chapitre_07_statistiques.tex` : Statistiques
- `chapitre_08_probabilites.tex` : Probabilités

#### Partie III : Calcul Littéral et Équations
- `chapitre_09_calcul_litteral.tex` : Calcul littéral
- `chapitre_10_equations.tex` : Équations

#### Partie IV : Fonctions
- `chapitre_11_notion_fonction.tex` : Notion de fonction

#### Partie V : Géométrie
- `chapitre_12_pythagore_geometrie.tex` : Théorème de Pythagore
- `chapitre_13_thalès.tex` : Théorème de Thalès
- `chapitre_14_trigonometrie.tex` : Trigonométrie
- `chapitre_15_translation.tex` : Transformations : Translation
- `chapitre_16_agrandissement_reduction.tex` : Agrandissement et réduction

#### Partie VI : Grandeurs et Mesures
- `chapitre_17_aires_volumes.tex` : Aires et volumes

#### Partie VII : Algorithmique et Programmation
- `chapitre_18_algorithmique.tex` : Algorithmique
- `chapitre_19_programmation.tex` : Programmation

#### Annexes
- `annexe_formulaire.tex` : Formulaire
- `annexe_methodologie.tex` : Méthodologie

## Compilation

Pour compiler le cours complet :
```bash
pdflatex main.tex
```

## Avantages de cette structure

1. **Modularité** : Chaque chapitre est dans un fichier séparé
2. **Maintenance facile** : Modification d'un chapitre sans affecter les autres
3. **Réutilisation** : Possibilité d'inclure seulement certains chapitres
4. **Collaboration** : Plusieurs personnes peuvent travailler sur différents chapitres
5. **Versioning** : Suivi des modifications par chapitre
6. **Organisation des figures** : Chaque chapitre a son propre dossier de figures
7. **Gestion des ressources** : Séparation claire entre contenu et images

## Personnalisation

Pour modifier un chapitre spécifique, éditez simplement le fichier correspondant dans le dossier `chapitres/`.

Pour ajouter un nouveau chapitre :
1. Créez un nouveau fichier `.tex` dans le dossier `chapitres/`
2. Créez un dossier `chapitres/figures/chapitre_XX_nom/` pour les figures
3. Ajoutez la ligne `\input{chapitres/nom_du_fichier}` dans `main.tex`

### Ajout de figures
Pour ajouter des figures à un chapitre :
1. Placez les fichiers dans le dossier correspondant : `chapitres/figures/chapitre_XX_nom/`
2. Utilisez le chemin relatif dans le fichier LaTeX : `chapitres/figures/chapitre_XX_nom/nom_figure.png`

## Auteur

M. Abdoullatuf - Collège Sainte Jeanne d'Arc
Année scolaire 2025-2026 