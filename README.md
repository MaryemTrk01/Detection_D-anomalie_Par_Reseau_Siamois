# Detection d'anomalies par reseaux siamois

Projet de detection d'anomalies sur des signaux de roulements a partir du dataset SUBF bearing faults.

## Objectif

Le projet compare deux approches de classification/detection :

- **Approche 1D** : apprentissage sur les signaux temporels bruts normalises.
- **Approche 2D** : transformation des signaux en images GAF, puis apprentissage par Conv2D.

Les classes considerees sont :

- `Normal`
- `Inner Race Fault`
- `Outer Race Fault`

## Contenu

- `main.ipynb` : notebook principal avec les modeles finaux :
  - Conv1D sur signaux 1D
  - Conv2D sur images GASF 1024x1024
  - Conv2D sur images GADF 1024x1024
  - comparaison finale des performances
- `Ps3 (3).ipynb` : premiere partie du projet, generation et visualisation des images GASF/GADF.

## Resultats obtenus

| Modele | Donnees | Accuracy |
|---|---|---:|
| Conv1D | Signaux temporels | ~90.05% |
| Conv2D | Images GASF 1024x1024 | ~91.51% |
| Conv2D | Images GADF 1024x1024 | ~90.28% |

## Donnees et fichiers lourds

Les donnees locales et caches generes ne sont pas versionnes :

- `Dataset/`
- `gaf_1024_cache/`
- fichiers `.dat`, `.npy`, `.npz`
- CSV normalises generes

Pour executer les notebooks, placer le dataset local dans :

```text
C:\Users\trkma\Downloads\archive\Dataset
```

ou modifier la variable `DATASET_DIR` dans les notebooks.

## Dependances principales

- Python
- NumPy
- Pandas
- Scikit-learn
- TensorFlow / Keras
- PyTS
- Matplotlib
- Seaborn

## Notes

Chaque signal est normalise ligne par ligne. Pour l'approche image, chaque signal complet de 5000 echantillons est transforme en image GASF/GADF 1024x1024.
