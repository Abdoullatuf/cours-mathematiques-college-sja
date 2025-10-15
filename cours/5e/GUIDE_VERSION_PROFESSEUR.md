# Guide : Générer la Version Professeur (Corrigé)

## 📚 Principe

Le système permet de générer **deux versions** du même cours :
- **Version ÉLÈVE** (par défaut) : avec des espaces à trous `______`
- **Version PROFESSEUR** : avec toutes les réponses affichées en bleu

## 🔧 Comment activer la version professeur ?

### Méthode : Modifier le fichier `main_5e.tex`

1. **Ouvrir le fichier** `main_5e.tex`

2. **Ajouter cette ligne** juste après `\begin{document}` :

```latex
\documentclass[12pt,a4paper]{book}
\newcommand{\niveau}{5\textsuperscript{e}}
\input{../../commun/preambule_commun}

\title{Cours de Mathématiques — Classe de 5\textsuperscript{e}\\[0.4em]\large Année scolaire 2025–2026}
\author{Abdoullatuf Maoulida}

\begin{document}
\VersionCorrige    % ← AJOUTER CETTE LIGNE POUR LA VERSION PROFESSEUR
\maketitle
\tableofcontents
...
```

3. **Compiler** le document :
```bash
pdflatex main_5e.tex
```

4. **Pour revenir à la version élève**, commenter ou supprimer la ligne :
```latex
% \VersionCorrige    % ← Commenté pour version élève
```

## 📋 Résumé des commandes

| Commande | Effet |
|----------|-------|
| `\VersionEleve` | Active la version élève (par défaut) |
| `\VersionCorrige` | Active la version professeur avec réponses |

## 💡 Astuce : Deux fichiers séparés

Pour ne pas avoir à modifier le fichier à chaque fois, vous pouvez créer **deux fichiers main différents** :

### Fichier `main_5e_eleve.tex`
```latex
\documentclass[12pt,a4paper]{book}
\newcommand{\niveau}{5\textsuperscript{e}}
\input{../../commun/preambule_commun}

\title{Cours de Mathématiques — Classe de 5\textsuperscript{e}\\[0.4em]
\large Année scolaire 2025–2026\\[0.3em]
\normalsize VERSION ÉLÈVE}
\author{Abdoullatuf Maoulida}

\begin{document}
% VERSION ÉLÈVE (par défaut)
\maketitle
\tableofcontents
\cleardoublepage

\input{chapitres/seq_01}
\input{chapitres/seq_02}
\input{chapitres/seq_03_nombres_en_ecriture_fractionnaire}

\cleardoublepage
\appendix
\chapter{Progression annuelle (récapitulatif)}
Cette progression correspond à la répartition établie pour l'année 2025–2026.

\end{document}
```

### Fichier `main_5e_prof.tex`
```latex
\documentclass[12pt,a4paper]{book}
\newcommand{\niveau}{5\textsuperscript{e}}
\input{../../commun/preambule_commun}

\title{Cours de Mathématiques — Classe de 5\textsuperscript{e}\\[0.4em]
\large Année scolaire 2025–2026\\[0.3em]
\normalsize \textcolor{blue}{VERSION PROFESSEUR}}
\author{Abdoullatuf Maoulida}

\begin{document}
\VersionCorrige    % ← VERSION PROFESSEUR
\maketitle
\tableofcontents
\cleardoublepage

\input{chapitres/seq_01}
\input{chapitres/seq_02}
\input{chapitres/seq_03_nombres_en_ecriture_fractionnaire}

\cleardoublepage
\appendix
\chapter{Progression annuelle (récapitulatif)}
Cette progression correspond à la répartition établie pour l'année 2025–2026.

\end{document}
```

Ainsi, vous pouvez compiler les deux versions indépendamment :
- `pdflatex main_5e_eleve.tex` → génère la version élève
- `pdflatex main_5e_prof.tex` → génère la version professeur

## 🎨 Apparence des réponses

Dans la **version professeur**, les réponses apparaissent :
- En **bleu** (couleur `mainBlue`)
- À la place des pointillés

Exemple :
- Version élève : `Le numérateur est ......`
- Version professeur : `Le numérateur est` **numérateur** (en bleu)

## ✅ Vérification

Pour vérifier que la version professeur fonctionne, cherchez dans le PDF les zones qui étaient à trous :
- Section "Vocabulaire et notation" → définition numérateur/dénominateur
- Exemples de simplification → calculs complétés
- Exercices → réponses affichées

---

**Créé le :** 12 octobre 2025
**Pour :** Cours de mathématiques 5e
**Contact :** Abdoullatuf Maoulida
