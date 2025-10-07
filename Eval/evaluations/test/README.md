# Package LaTeX college-eval v2.0 📚

Package LaTeX professionnel pour créer des contrôles de mathématiques au collège avec mise en page moderne et gestion automatique des versions élève/corrigé.

## 🚀 Installation

### Prérequis
- **LuaLaTeX** (recommandé) ou XeLaTeX
- Distribution TeX complète (TeX Live 2020+ ou MiKTeX)
- Packages requis :
  - fontspec
  - babel (french)
  - fontawesome5
  - tcolorbox
  - tikz
  - pgfplots
  - xlop
  - siunitx
  - geometry
  - fancyhdr
  - enumitem
  - multicol
  - xcolor
  - graphicx
  - array
  - tabularx
  - etoolbox

### Installation du package

1. Placer `college-eval.sty` dans le même dossier que vos fichiers `.tex`
   
   OU

2. Placer dans votre répertoire texmf local :
   - Linux/Mac : `~/texmf/tex/latex/college-eval/`
   - Windows : `C:\Users\<username>\texmf\tex\latex\college-eval\`

3. Exécuter `texhash` (ou `mktexlsr`) si installation globale

## 📁 Structure recommandée

```
controles/
├── college-eval.sty
├── controle_01/
│   ├── controle_01_eleve.tex
│   ├── controle_01_corrige.tex
│   └── controle_01_body.tex
├── controle_02/
│   ├── controle_02_eleve.tex
│   ├── controle_02_corrige.tex
│   └── controle_02_body.tex
└── images/
    └── ...
```

## 🎯 Démarrage rapide

### Fichier élève (controle_01_eleve.tex)

```latex
% !TeX program = lualatex
\documentclass[11pt,a4paper]{article}
\usepackage{college-eval}

\examsetup{6\textsuperscript{e}}{Mathématiques}{Nombres entiers}{1}{55 minutes}{Calculatrice autorisée}

\begin{document}
    \CorrigeWatermark
    \ExamBanner
    \StudentInfoBox
    
    \input{controle_01_body.tex}
\end{document}
```

### Fichier corrigé (controle_01_corrige.tex)

```latex
% !TeX program = lualatex
\documentclass[11pt,a4paper]{article}
\usepackage[corrige]{college-eval}  % ← Option corrige

\examsetup{6\textsuperscript{e}}{Mathématiques}{Nombres entiers}{1}{55 minutes}{Calculatrice autorisée}

\begin{document}
    \CorrigeWatermark
    \ExamBanner
    \StudentInfoBox
    
    \input{controle_01_body.tex}
\end{document}
```

### Fichier contenu (controle_01_body.tex)

```latex
% Barème
\bareme{
    \exbadge{1}{6} \quad
    \exbadge{2}{8} \quad
    \bonusbadge{2}
}

% Consignes
\begin{consignebox}
    \faIcon{info-circle} \textbf{CONSIGNES}
    \begin{itemize}[leftmargin=*,noitemsep]
        \item[\faIcon{check}] Justifiez vos réponses
    \end{itemize}
\end{consignebox}

\exspace

% Exercice
\begin{exercisebox}{\faIcon{calculator} Exercice 1 : Calculs \points{6}}
    
    Calcule : $25 + 17 = $ \ans{42}
    
\end{exercisebox}

\AutoEval
```

## 🎨 Fonctionnalités principales

### 1. Barème automatique

```latex
\bareme{
    \exbadge{1}{6} \quad      % Exercice 1: 6 pts
    \exbadge{2}{4} \quad      % Exercice 2: 4 pts
    \bonusbadge{2}            % Bonus: +2 pts
}
```

### 2. Boîtes thématiques élargies

```latex
% Boîte standard (bleue)
\begin{exercisebox}{\faIcon{book} Titre \points{6}}
    Contenu
\end{exercisebox}

% Boîte QCM (bleu clair)
\begin{qcmbox}{\faIcon{list-ul} QCM \points{4}}
    \begin{qcmtable}
        Question & A & B & C & \ans{B} \\
        \hline
    \end{qcmtable}
\end{qcmbox}

% Boîte construction (verte)
\begin{constructionbox}{\faIcon{drafting-compass} Construction \points{7}}
    Construis...
\end{constructionbox}

% Boîte problème (rouge clair)
\begin{problembox}{\faIcon{search} Problème \points{8}}
    Résous...
\end{problembox}
```

### 3. Gestion des réponses

```latex
% Réponse courte
La réponse est \ans{42}.

% Réponse avec espace
Résultat : \blanks{3cm}

% Réponse multiligne
\anslines[0.5cm]{4}{
    % Visible en rouge dans le corrigé
    % 4 lignes de pointillés en version élève
    La réponse détaillée...
}

% Zone de réponse vide
\zonereponse{4cm}
\zonereponseLignes{5}
```

### 4. Opérations posées

```latex
\begin{center}
    \AddPose{345}{78}    % Addition
    \SubPose{543}{287}   % Soustraction
    \MulPose{123}{45}    % Multiplication
    \DivEuc{547}{12}     % Division euclidienne
\end{center}
```

### 5. Template exercice rapide

```latex
\ExTemplate{1}{Titre de l'exercice}{6}{book}{
    Contenu de l'exercice ici
}
```

### 6. Visibilité conditionnelle

```latex
\onlycorrige{Texte visible uniquement dans le corrigé}
\onlyeleve{Texte visible uniquement pour l'élève}
```

## 🎨 Personnalisation

### Couleurs disponibles

```latex
primary     % Bleu moderne (41,128,185)
secondary   % Gris foncé (52,73,94)
accent      % Vert menthe (46,204,113)
warning     % Rouge moderne (231,76,60)
light       % Gris clair (236,240,241)
bglight     % Fond clair (247,249,250)
info        % Bleu info (52,152,219)
success     % Vert succès (39,174,96)
```

### Icônes FontAwesome disponibles

```latex
\faIcon{book}              % Livre
\faIcon{calculator}        % Calculatrice
\faIcon{drafting-compass}  % Compas
\faIcon{lightbulb}         % Ampoule
\faIcon{divide}            % Division
\faIcon{percentage}        % Pourcentage
\faIcon{search}            % Loupe
\faIcon{list-ul}           % Liste
\faIcon{check}             % Coche
\faIcon{times}             % Croix
\faIcon{info-circle}       % Info
\faIcon{star}              % Étoile
```

Liste complète : [FontAwesome 5 Documentation](http://mirrors.ctan.org/fonts/fontawesome5/doc/fontawesome5.pdf)

## 📝 Exemples d'exercices

### QCM

```latex
\begin{qcmbox}{\faIcon{list-ul} QCM \points{4}}
    Pour chaque question, choisis la bonne réponse :
    
    \begin{qcmtable}
        \textbf{1.} $2 + 3 = $ ? & 4 & 5 & 6 & \ans{B} \\
        \hline
        \textbf{2.} $10 \div 2 = $ ? & 4 & 5 & 6 & \ans{B} \\
        \hline
    \end{qcmtable}
\end{qcmbox}
```

### Construction géométrique

```latex
\begin{constructionbox}{\faIcon{drafting-compass} Construction \points{5}}
    Construis un triangle ABC tel que :
    \begin{itemize}
        \item $AB = 5$ cm
        \item $AC = 7$ cm
        \item $BC = 6$ cm
    \end{itemize}
    
    \figureespace{6cm}
\end{constructionbox}
```

### Problème

```latex
\begin{problembox}{\faIcon{search} Problème \points{8}}
    Un cycliste parcourt 15 km en 30 minutes.
    
    \textbf{1.} Quelle est sa vitesse en km/h ? \points{4}
    
    \anslines{3}{
        $\text{Vitesse} = \frac{15 \times 2}{1} = 30$ km/h
    }
    
    \textbf{2.} Combien parcourt-il en 2 heures ? \points{4}
    
    \anslines{2}{
        $\text{Distance} = 30 \times 2 = 60$ km
    }
\end{problembox}
```

## 🔧 Compilation

### Terminal

```bash
# Version élève
lualatex controle_01_eleve.tex

# Version corrigé
lualatex controle_01_corrige.tex
```

### TeXmaker / TeXstudio

1. Configurer le compilateur sur LuaLaTeX
2. Ou ajouter en première ligne : `% !TeX program = lualatex`

### Overleaf

1. Menu → Compilateur → LuaLaTeX
2. Upload `college-eval.sty` dans le projet

## 📊 Nouveautés v2.0

✨ **Améliorations :**
- Boîtes élargies de 3mm → 5mm (meilleure lisibilité)
- Nouvelles boîtes thématiques (QCM, Construction, Problème)
- Templates d'exercices rapides
- Commande `\AutoEval` pour pied de page
- Helpers pour badges de barème
- Espacement adaptatif (`\exspace`, `\smallspace`)
- Commandes `\onlyeleve` et `\onlycorrige`
- Support amélioré des opérations posées (xlop)
- Grille de compétences optionnelle

## 🐛 Résolution de problèmes

### Erreur: fontawesome5.sty not found

```bash
# Linux (TeX Live)
sudo apt install texlive-fonts-extra

# Mac (MacTeX)
sudo tlmgr install fontawesome5

# Windows (MiKTeX)
# Installer via MiKTeX Package Manager
```

### Erreur: xlop.sty not found

```bash
sudo tlmgr install xlop
```

### Compilation échoue

1. Vérifier que LuaLaTeX est bien installé : `lualatex --version`
2. Vérifier l'encodage UTF-8 du fichier
3. Compiler 2 fois pour les références

## 📚 Documentation complète

Voir `GUIDE_UTILISATION.tex` pour :
- Exemples détaillés de tous les environnements
- Liste exhaustive des commandes
- Bonnes pratiques
- Templates réutilisables

## 📄 Licence

Ce package est distribué sous licence LaTeX Project Public License (LPPL) v1.3c.

## 👤 Auteur

Package créé pour faciliter la création de contrôles au collège.

## 🤝 Contribution

Pour signaler un bug ou proposer une amélioration, créez un fichier texte avec :
- Description du problème ou de la fonctionnalité
- Exemple minimal de code
- Version de votre distribution TeX

## 📌 Changelog

### v2.0 (2025-10-04)
- Boîtes élargies (5mm au lieu de 3mm)
- Nouvelles boîtes thématiques
- Templates d'exercices
- Helpers de barème
- Auto-évaluation automatique
- Support amélioré xlop

### v1.0 (2025-09-17)
- Version initiale
- Bandeau et cartouche élève
- Gestion corrigé/élève
- Boîtes exercices et consignes

---

**Bon courage pour vos contrôles ! 📝✨**
