# 📚 Cours de Mathématiques - Collège Sainte Jeanne d'Arc

## 📖 Description

Ce repository contient les supports de cours de mathématiques pour les classes de 6e, 5e et 4e du Collège Sainte Jeanne d'Arc, année scolaire 2025-2026.

## 🏗️ Structure du projet

```
Annee_scolaire_2025-2026/
├── commun/
│   └── preambule_commun.tex          # Préambule LaTeX partagé
├── cours/
│   ├── 6e/
│   │   ├── main_6e.tex               # Document principal 6e
│   │   └── chapitres/
│   │       ├── seq_01.tex            # Séquence 1
│   │       └── seq_02.tex            # Séquence 2
│   ├── 5e/
│   │   ├── main_5e.tex               # Document principal 5e
│   │   └── chapitres/
│   │       └── seq_01.tex            # Enchaînement d'opérations
│   └── 4e/
│       ├── main_4e.tex               # Document principal 4e
│       └── chapitres/
│           ├── seq_01_nombres_relatifs.tex
│           └── seq_02_pythagore.tex
├── assets/
│   ├── images/                       # Images centralisées
│   │   ├── 6e/
│   │   ├── 5e/
│   │   └── 4e/
│   └── figures/                      # Figures communes
└── README.md
```

## 🎯 Fonctionnalités

### Environnements personnalisés
- `definitionbox` : Définitions (orange)
- `examplebox` : Exemples (vert)
- `exercisebox` : Exercices (violet)
- `objectifsbox` : Objectifs (teal)
- `proprietebox` : Propriétés (rouge)
- `activitybox` : Activités (bleu)
- `remarkbox` : Remarques (jaune)
- `quizbox` : Quiz (cyan)
- `methodebox` : Méthodes (pourpre)

### Commandes personnalisées
- `\trous[largeur]` : Crée des pointillés pour les exercices
- `\setseqtitle{titre}` : Définit le titre de la séquence

## 🛠️ Compilation

### Prérequis
- Distribution LaTeX (TeX Live, MiKTeX, etc.)
- Compilateur `pdflatex`

### Compilation d'un niveau
```bash
# Pour la 6e
cd cours/6e
pdflatex main_6e.tex

# Pour la 5e
cd cours/5e
pdflatex main_5e.tex

# Pour la 4e
cd cours/4e
pdflatex main_4e.tex
```

### Compilation avec VSCode
1. Installer l'extension "LaTeX Workshop"
2. Configurer `settings.json` (voir documentation)
3. Utiliser `Ctrl+Alt+B` pour compiler

## 📝 Contenu par niveau

### 6e
- **Séquence 1** : [Contenu à définir]
- **Séquence 2** : [Contenu à définir]

### 5e
- **Séquence 1** : Enchaînement d'opérations
  - Calculs sans parenthèses
  - Calculs avec parenthèses
  - Priorités opératoires
  - Vocabulaire mathématique

### 4e
- **Séquence 1** : Les nombres relatifs
  - Définition et représentation
  - Addition et soustraction
  - Multiplication et division
  - Généralisation de la règle des signes
  - Nombres inverses
  - Expressions numériques
- **Séquence 2** : Théorème de Pythagore

## 🎨 Personnalisation

### Couleurs des boîtes
Les couleurs peuvent être modifiées dans `commun/preambule_commun.tex` :

```latex
\newtcolorbox{definitionbox}{
    colback=orange!5!white,    # Fond orange clair
    colframe=orange!70!black,  # Bordure orange foncé
    % ...
}
```

### Espacement
L'espacement des titres et des boîtes est configuré dans le préambule commun :
- `\titlespacing` pour les titres
- `\tcbset` pour les boîtes

## 📚 Ressources

- [Documentation LaTeX](https://www.latex-project.org/)
- [Package tcolorbox](https://ctan.org/pkg/tcolorbox)
- [Package titlesec](https://ctan.org/pkg/titlesec)

## 🤝 Contribution

1. Fork le repository
2. Créer une branche pour votre fonctionnalité
3. Commiter vos changements
4. Pousser vers la branche
5. Créer une Pull Request

## 📄 Licence

Ce projet est destiné à un usage éducatif au Collège Sainte Jeanne d'Arc.

## 👨‍🏫 Auteur

Cours de mathématiques - Collège Sainte Jeanne d'Arc
Année scolaire 2025-2026

---

*Dernière mise à jour : Août 2025*
