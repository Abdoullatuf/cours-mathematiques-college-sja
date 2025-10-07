# 🚀 DÉMARRAGE RAPIDE - college-eval v2.0

## ⏱️ En 5 minutes : Créer votre premier contrôle

### Étape 1 : Télécharger les fichiers (✅ Déjà fait !)

Vous avez tous les fichiers nécessaires dans `/mnt/user-data/outputs/`

### Étape 2 : Créer la structure de votre contrôle

Créez 3 fichiers :

**1. `mon_controle_eleve.tex`**
```latex
% !TeX program = lualatex
\documentclass[11pt,a4paper]{article}
\usepackage{college-eval}

\examsetup{6\textsuperscript{e}}{Mathématiques}{Mon premier contrôle}{1}{55 minutes}{Calculatrice autorisée}

\begin{document}
    \CorrigeWatermark
    \ExamBanner
    \StudentInfoBox
    \smallspace
    \input{mon_controle_body.tex}
\end{document}
```

**2. `mon_controle_corrige.tex`**
```latex
% !TeX program = lualatex
\documentclass[11pt,a4paper]{article}
\usepackage[corrige]{college-eval}  % ← Ajouter [corrige]

\examsetup{6\textsuperscript{e}}{Mathématiques}{Mon premier contrôle}{1}{55 minutes}{Calculatrice autorisée}

\begin{document}
    \CorrigeWatermark
    \ExamBanner
    \StudentInfoBox
    \smallspace
    \input{mon_controle_body.tex}
\end{document}
```

**3. `mon_controle_body.tex`**
```latex
% Barème
\bareme{
    \exbadge{1}{6} \quad
    \exbadge{2}{8}
}

% Consignes
\begin{consignebox}
    \faIcon{info-circle} \textbf{CONSIGNES}
    \begin{itemize}[leftmargin=*,noitemsep]
        \item[\faIcon{check}] Justifiez vos réponses
    \end{itemize}
\end{consignebox}

\exspace

% Votre premier exercice
\begin{exercisebox}{\faIcon{calculator} Exercice 1 \points{6}}
    Calcule : $12 + 8 = $ \ans{20}
\end{exercisebox}

\AutoEval
```

### Étape 3 : Compiler

```bash
lualatex mon_controle_eleve.tex
lualatex mon_controle_corrige.tex
```

C'est tout ! 🎉

---

## 📝 Exemples rapides de code

### QCM
```latex
\begin{qcmbox}{\faIcon{list-ul} QCM \points{4}}
    \begin{qcmtable}
        \textbf{1.} $5+7=$ ? & 11 & 12 & 13 & \ans{B} \\
        \hline
    \end{qcmtable}
\end{qcmbox}
```

### Construction
```latex
\begin{constructionbox}{\faIcon{drafting-compass} Construction \points{5}}
    Construis un triangle ABC...
    \figureespace{6cm}
\end{constructionbox}
```

### Problème
```latex
\begin{problembox}{\faIcon{search} Problème \points{7}}
    Un train parcourt 180 km en 2h...
    
    \textbf{1.} Quelle est sa vitesse ?
    \anslines{3}{
        Vitesse = 180 ÷ 2 = 90 km/h
    }
\end{problembox}
```

### Opération posée
```latex
\begin{center}
    \DivEuc{547}{12}  % Division euclidienne
\end{center}
```

---

## 🎨 Personnalisation rapide

### Changer le titre
```latex
\examsetup{5\textsuperscript{e}}{Physique}{Les forces}{2}{45 min}{Calculatrice autorisée}
```

### Ajouter un bonus
```latex
\bareme{
    \exbadge{1}{6} \quad
    \bonusbadge{2}  % ← Badge bonus
}
```

### Changer l'icône d'un exercice
```latex
\begin{exercisebox}{\faIcon{star} Exercice spécial \points{10}}
    % Icônes disponibles: book, calculator, star, lightbulb, etc.
\end{exercisebox}
```

---

## 🆘 Résolution de problèmes

### ❌ Erreur : "fontawesome5.sty not found"
```bash
sudo tlmgr install fontawesome5
```

### ❌ Erreur : "xlop.sty not found"  
```bash
sudo tlmgr install xlop
```

### ❌ Les réponses n'apparaissent pas en rouge
➡️ Vérifiez que vous utilisez `\usepackage[corrige]{college-eval}`

### ❌ Le filigrane "CORRIGÉ" n'apparaît pas
➡️ Normal en version élève, seulement visible avec `[corrige]`

---

## 📚 Fichiers fournis

| Fichier | Description |
|---------|-------------|
| `college-eval.sty` | **Package principal** |
| `README.md` | Documentation complète |
| `GUIDE_UTILISATION.tex` | Guide détaillé avec exemples |
| `controle_6e_geometrie_*` | Contrôle complet (géométrie) |
| `exemple_complet_*` | Démonstration de toutes les fonctionnalités |

---

## ✅ Check-list avant de commencer

- [ ] LuaLaTeX installé (`lualatex --version`)
- [ ] Package fontawesome5 installé
- [ ] Package xlop installé
- [ ] `college-eval.sty` dans le même dossier que vos `.tex`
- [ ] 3 fichiers créés : `*_eleve.tex`, `*_corrige.tex`, `*_body.tex`

---

## 🎯 Prochaines étapes

1. ✅ Testez avec l'exemple fourni : `exemple_complet_eleve.tex`
2. 📖 Lisez `README.md` pour plus de détails
3. 🎨 Consultez `GUIDE_UTILISATION.tex` pour voir toutes les commandes
4. 🚀 Créez votre premier contrôle !

---

**Besoin d'aide ?**
- Consultez `README.md` section "Résolution de problèmes"
- Regardez `exemple_complet_body.tex` pour voir toutes les fonctionnalités
- Lisez `GUIDE_UTILISATION.tex` pour les détails

**Bon courage pour vos contrôles ! 📝✨**
