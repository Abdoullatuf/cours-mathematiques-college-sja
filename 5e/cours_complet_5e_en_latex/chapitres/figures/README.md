# Organisation des Figures par Chapitre

## Structure

Chaque chapitre a son propre dossier de figures dans `chapitres/figures/chapitre_XX_nom/`

## Utilisation

### Dans les fichiers LaTeX
Pour inclure une figure dans un chapitre, utilisez le chemin relatif :

```latex
\includegraphics[width=0.8\textwidth]{chapitres/figures/chapitre_02_pythagore/demo_pythagore.png}
```

### Conventions de nommage
- Utilisez des noms descriptifs en minuscules
- Séparez les mots par des underscores
- Incluez le numéro du chapitre si nécessaire
- Exemple : `demo_pythagore_config1.png`

## Types de fichiers supportés
- Images : PNG, JPG, PDF
- Graphiques : SVG, EPS
- Diagrammes : PDF, PNG

## Organisation recommandée
- `figures/` : Images et graphiques
- `diagrams/` : Diagrammes et schémas
- `screenshots/` : Captures d'écran (si applicable)

## Exemple d'utilisation dans un chapitre

```latex
\begin{figure}[H]
\centering
\includegraphics[width=0.8\textwidth]{chapitres/figures/chapitre_02_pythagore/demo_pythagore_config1.png}
\caption{Démonstration du théorème de Pythagore - Configuration 1}
\label{fig:demo_pythagore_1}
\end{figure}
``` 