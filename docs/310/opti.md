**FSD310 - Fundamentals of Decision Making**

# Optimisation for Decision Making

Schedule | | |
| --- | --- | --- |
14/09 AM | Continuous Optimization | 3h30 |
16/09 AM | Combinatorial Optimization | 1h30 |
21/09 AM | Combinatorial Optimization| 2h |
22/09 PM | Stochastic Optimization | 2h |
28/09 PM | **Written Exam**  | 1h |
12/10 PM | Auto-differentiation | 3h |


## Optimisation continue

[Diapositives](cours/Optimisation_continue_SD.pdf)

Le BE sera réalisé sur Jupyter-notebook. Voici la suite d'instructions à suivre au début d'un BE :

Démarrer sous Linux
Puis dans un terminal, exécuter :

```
module load gcc/13.2.0 
module load anaconda3/2026
conda activate ma-env
jupyter-notebook &
```

Si vous souhaitez utiliser votre ordinateur personnel, il faut récupérer récupérer le [package casADi](https://web.casadi.org/get/).

[BE Optimisation Continue](TP/BE_opti_continue_SD.zip)


## Optimisation combinatoire

### Diapositives

[Complexité](cours/slidesComplexityTCS3IN.pdf)

[Programmation Linéaire en nombres entiers](cours/CoursPLNE_2A_2026.pdf)

### BE Programmation linéaire en nombres entiers

Le BE est un notebook accessible de la manière suivante :

- Ouvrir une session linux
- Télécharger [l'archive](TP/FIFA.zip) et la sauvegarder sur votre compte puis la décompresser.
- Pour accéder au notebook, taper les commandes suivantes dans un terminal :
```
ml anaconda3/2026
conda activate gurobi-env
jupyter-notebook&
```
- Une fois la page Home ouverte, depuis cette page lancer le notebook **FIFA2.ipynb**


## Optimisation stochastique

[Diapositives](cours/Cours_Optimisation_Stochastique_2026_2027.pdf)

### Notebooks

[Algorithme génétique](TP/Genetic_Algorithm.ipynb) 

[Recherche aléatoire](TP/Random_Search.ipynb) 

[Stratégies Évolutionnaires](TP/Evolutionary_Strategies.ipynb) 

## Auto-differentiation

[BE autodiff/SGD/Adam](TP/control_BE.ipynb) 

