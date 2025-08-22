# Structure des Images - Cours de Mathématiques

## Organisation des images

```
assets/
├── images/
│   ├── 6e/                    # Images pour la classe de 6e
│   │   ├── seq_01/           # Images pour la séquence 1
│   │   ├── seq_02/           # Images pour la séquence 2
│   │   ├── ...
│   │   └── seq_20/           # Images pour la séquence 20
│   ├── 5e/                    # Images pour la classe de 5e
│   └── 4e/                    # Images pour la classe de 4e
└── figures/                   # Figures communes à tous les niveaux
```

## Chemins dans les fichiers LaTeX

### Pour les fichiers dans `cours/6e/chapitres/` :
```latex
\includegraphics[width=1\linewidth]{../../../assets/images/6e/seq_02/nom_image.png}
```

### Pour les fichiers dans `cours/5e/chapitres/` :
```latex
\includegraphics[width=1\linewidth]{../../../assets/images/5e/seq_01/nom_image.png}
```

### Pour les fichiers dans `cours/4e/chapitres/` :
```latex
\includegraphics[width=1\linewidth]{../../../assets/images/4e/seq_01/nom_image.png}
```

## Conventions de nommage

- **Images par séquence** : `assets/images/6e/seq_XX/nom_descriptif.png`
- **Figures communes** : `assets/figures/nom_descriptif.png`
- **Format recommandé** : PNG, JPG, ou PDF pour les graphiques vectoriels

## Avantages de cette structure

1. **Centralisation** : Toutes les images au même endroit
2. **Réutilisabilité** : Possibilité de partager des images entre niveaux
3. **Organisation claire** : Structure hiérarchique par niveau et séquence
4. **Maintenance facile** : Un seul endroit pour gérer les ressources
5. **Cohérence** : Structure uniforme pour tous les niveaux

## Ajout d'images

1. Placer l'image dans le bon dossier : `assets/images/6e/seq_XX/`
2. Mettre à jour le chemin dans le fichier LaTeX correspondant
3. Utiliser des noms descriptifs et cohérents
