# 📚 Guide de Compilation - Cours de Mathématiques 5e

## 📁 Fichiers Disponibles

Vous disposez maintenant de **3 fichiers LaTeX principaux** dans ce dossier :

| Fichier | Description | Usage |
|---------|-------------|-------|
| `main_5e.tex` | Fichier original | Version élève par défaut |
| `main_5e_eleve.tex` | **VERSION ÉLÈVE** | Génère le cours avec espaces à trous |
| `main_5e_prof.tex` | **VERSION PROFESSEUR** | Génère le cours avec toutes les réponses |

## 🚀 Compilation Rapide

### Version Élève (avec espaces à trous)
```bash
pdflatex main_5e_eleve.tex
```
**Résultat :** `main_5e_eleve.pdf` avec des pointillés à la place des réponses

### Version Professeur (corrigé complet)
```bash
pdflatex main_5e_prof.tex
```
**Résultat :** `main_5e_prof.pdf` avec toutes les réponses en **bleu**

## 🎨 Différences Visuelles

### Exemple : Section "Vocabulaire et notation"

**Version ÉLÈVE :**
```
Le nombre du haut, a, s'appelle le ..................
Le nombre du bas, b, s'appelle le .......................
```

**Version PROFESSEUR :**
```
Le nombre du haut, a, s'appelle le numérateur (en bleu)
Le nombre du bas, b, s'appelle le dénominateur (en bleu)
```

## 📖 Contenu du Cours

### Séquence 03 : Nombres en écriture fractionnaire

**Objectifs :**
- Comprendre les différentes interprétations d'une fraction
- Reconnaître et produire des fractions égales
- Simplifier une fraction par division
- Décomposer une fraction en somme d'un entier et d'une fraction inférieure à 1
- Comparer des fractions entre elles
- Encadrer une fraction par deux entiers consécutifs

**Améliorations pédagogiques incluses :**
- ✅ Activité de manipulation divisée en 2 parties (meilleure mise en page)
- ✅ Note pour l'enseignant sur la difficulté du tiers
- ✅ Questions d'analyse des transformations pour découvrir la propriété
- ✅ Méthode de simplification en 2 approches (pas à pas / efficace)
- ✅ Encadré "De = multiplication" pour faire le lien linguistique
- ✅ Question de justification avec schéma dans les exercices
- ✅ Exercice bonus "Trouve l'erreur" pour développer l'esprit critique

## 💻 Compilation avec un Éditeur LaTeX

### TeXstudio, TeXmaker, Overleaf, etc.

1. **Ouvrir** le fichier désiré :
   - `main_5e_eleve.tex` pour la version élève
   - `main_5e_prof.tex` pour la version professeur

2. **Compiler** avec PDFLaTeX (bouton "Compiler" ou F5)

3. **Visualiser** le PDF généré

## 🔄 Recompilation

Si vous modifiez le contenu des chapitres (dans le dossier `chapitres/`), vous devez **recompiler les deux versions** pour mettre à jour les PDF :

```bash
# Version élève
pdflatex main_5e_eleve.tex

# Version professeur
pdflatex main_5e_prof.tex
```

## 📦 Structure des Fichiers

```
5e/
├── main_5e.tex                  # Fichier original (à garder pour référence)
├── main_5e_eleve.tex            # 🎓 VERSION ÉLÈVE
├── main_5e_prof.tex             # 👨‍🏫 VERSION PROFESSEUR
├── main_5e_eleve.pdf            # PDF généré (élève)
├── main_5e_prof.pdf             # PDF généré (professeur)
├── chapitres/
│   ├── seq_01.tex
│   ├── seq_02.tex
│   └── seq_03_nombres_en_ecriture_fractionnaire.tex  # ← Cours amélioré
├── GUIDE_VERSION_PROFESSEUR.md  # Documentation détaillée
└── README_COMPILATION.md        # Ce fichier
```

## ⚙️ Paramètres du Système

Le système de gestion des versions est défini dans :
- **Fichier préambule :** `../../commun/preambule_commun.tex`
- **Commande principale :** `\VersionCorrige` (active les réponses)
- **Commande par défaut :** `\VersionEleve` (espaces à trous)

### Personnalisation (avancé)

Si vous souhaitez modifier l'apparence des réponses dans la version professeur, éditez le fichier `../../commun/preambule_commun.tex` :

```latex
% Ligne ~424 : Couleur des réponses
\newcommand{\solution}[2][\solutionspace]{%
    \ifcorrige
        {\color{mainBlue}#2}%    % ← Changer mainBlue ici
    \else
        \makebox[#1]{\rule{0pt}{1.2ex}\dotfill}%
    \fi
}
```

## 🎯 Conseils d'Utilisation

### Pour les élèves
- Imprimez `main_5e_eleve.pdf`
- Les élèves complètent les espaces à trous pendant le cours

### Pour l'enseignant
- Projetez `main_5e_eleve.pdf` en classe
- Gardez `main_5e_prof.pdf` pour vos corrections et préparations
- Utilisez la version professeur pour préparer les corrections à projeter

## 🐛 Résolution de Problèmes

### Les réponses n'apparaissent pas en bleu dans la version professeur
➡️ Vérifiez que la ligne `\VersionCorrige` est présente dans `main_5e_prof.tex` (ligne 11)

### Erreur de compilation "pgf Error: No shape named..."
➡️ Ces erreurs sont **normales** et n'empêchent pas la génération du PDF. Elles concernent un schéma TikZ avec des références croisées.

### Les modifications ne s'affichent pas
➡️ Pensez à **recompiler** après chaque modification de fichier

## 📧 Support

**Auteur :** Abdoullatuf Maoulida
**Année scolaire :** 2025-2026
**Établissement :** CLG Sainte Jeanne d'Arc

---

**Dernière mise à jour :** 12 octobre 2025
