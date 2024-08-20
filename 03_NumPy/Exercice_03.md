# Exercice 3 : Analyse Statistique avec NumPy

## Introduction

NumPy offre de puissantes fonctionnalités pour l'analyse statistique des données. Dans cet exercice, nous allons explorer comment utiliser NumPy pour calculer diverses statistiques descriptives sur un ensemble de données.

Définitions :
- Statistiques descriptives : Mesures qui résument et décrivent les principales caractéristiques d'un ensemble de données.
- Mesures de tendance centrale : Valeurs qui représentent le centre ou la valeur typique d'un ensemble de données (ex : moyenne, médiane).
- Mesures de dispersion : Valeurs qui décrivent la variabilité ou l'étendue des données (ex : écart-type, variance).

Dans cet exercice, vous allez apprendre à :
1. Calculer des mesures de tendance centrale
2. Calculer des mesures de dispersion
3. Effectuer des calculs statistiques sur des axes spécifiques d'un array multidimensionnel

## Partie 1 : Mesures de Tendance Centrale

### Énoncé

Nous allons travailler avec un ensemble de données représentant les notes d'étudiants sur différents examens. Votre tâche est de calculer différentes mesures de tendance centrale.

### Indices et explications

- La moyenne (mean) est la somme de toutes les valeurs divisée par le nombre de valeurs.
- La médiane est la valeur centrale lorsque les données sont ordonnées.
- Le mode est la valeur qui apparaît le plus fréquemment dans l'ensemble de données.

### Code à compléter

```python
import numpy as np

# Données des notes d'étudiants (5 étudiants, 4 examens)
notes = np.array([
    [15, 14, 16, 18],
    [12, 13, 11, 14],
    [18, 17, 19, 20],
    [10, 9, 11, 12],
    [14, 15, 13, 16]
])

# 1. Calculez la moyenne de toutes les notes
# Indice : Utilisez np.mean()
moyenne_globale = # Votre code ici

# 2. Calculez la médiane de toutes les notes
# Indice : Utilisez np.median()
mediane_globale = # Votre code ici

# 3. Trouvez la note la plus fréquente (mode)
# Indice : Utilisez np.bincount() et np.argmax()
mode_global = # Votre code ici

# Affichez vos résultats
print("Moyenne globale des notes:", moyenne_globale)
print("Médiane globale des notes:", mediane_globale)
print("Note la plus fréquente:", mode_global)
```

### Code de test

```python
def test_partie1():
    assert np.isclose(moyenne_globale, 14.25), "La moyenne globale n'est pas correcte"
    assert np.isclose(mediane_globale, 14.0), "La médiane globale n'est pas correcte"
    assert mode_global == 14, "La note la plus fréquente n'est pas correcte"

test_partie1()
print("Tous les tests de la Partie 1 sont passés !")
```

## Partie 2 : Mesures de Dispersion

### Énoncé

Maintenant, nous allons calculer des mesures de dispersion pour comprendre la variabilité des notes.

### Indices et explications

- L'écart-type mesure la dispersion des valeurs autour de la moyenne.
- La variance est le carré de l'écart-type.
- L'intervalle est la différence entre la valeur maximale et la valeur minimale.

### Code à compléter

```python
# 1. Calculez l'écart-type de toutes les notes
# Indice : Utilisez np.std()
ecart_type = # Votre code ici

# 2. Calculez la variance de toutes les notes
# Indice : Utilisez np.var()
variance = # Votre code ici

# 3. Trouvez l'intervalle (différence entre la note max et min)
# Indice : Utilisez np.max() et np.min()
intervalle = # Votre code ici

# Affichez vos résultats
print("Écart-type des notes:", ecart_type)
print("Variance des notes:", variance)
print("Intervalle des notes:", intervalle)
```

### Code de test

```python
def test_partie2():
    assert np.isclose(ecart_type, 2.7786, atol=1e-4), "L'écart-type n'est pas correct"
    assert np.isclose(variance, 7.7188, atol=1e-4), "La variance n'est pas correcte"
    assert intervalle == 11, "L'intervalle n'est pas correct"

test_partie2()
print("Tous les tests de la Partie 2 sont passés !")
```

## Partie 3 : Analyse par Axe

### Énoncé

Enfin, nous allons effectuer des calculs statistiques sur des axes spécifiques de notre array de notes.

### Indices et explications

- NumPy permet de calculer des statistiques le long d'un axe spécifique d'un array multidimensionnel.
- L'axe 0 correspond aux colonnes (dans notre cas, les examens).
- L'axe 1 correspond aux lignes (dans notre cas, les étudiants).

### Code à compléter

```python
# 1. Calculez la moyenne des notes pour chaque examen
# Indice : Utilisez np.mean() avec l'argument axis
moyennes_examens = # Votre code ici

# 2. Calculez la moyenne des notes pour chaque étudiant
# Indice : Utilisez np.mean() avec un axe différent
moyennes_etudiants = # Votre code ici

# 3. Trouvez l'étudiant avec la meilleure moyenne
# Indice : Utilisez np.argmax()
meilleur_etudiant = # Votre code ici

# Affichez vos résultats
print("Moyennes des examens:", moyennes_examens)
print("Moyennes des étudiants:", moyennes_etudiants)
print("Indice du meilleur étudiant:", meilleur_etudiant)
```

### Code de test

```python
def test_partie3():
    assert np.allclose(moyennes_examens, [13.8, 13.6, 14. , 16. ]), "Les moyennes des examens ne sont pas correctes"
    assert np.allclose(moyennes_etudiants, [15.75, 12.5 , 18.5 , 10.5 , 14.5 ]), "Les moyennes des étudiants ne sont pas correctes"
    assert meilleur_etudiant == 2, "L'indice du meilleur étudiant n'est pas correct"

test_partie3()
print("Tous les tests de la Partie 3 sont passés !")
```

## Conclusion

Félicitations ! Vous avez terminé l'exercice sur l'analyse statistique avec NumPy. Vous avez appris à :
- Calculer des mesures de tendance centrale comme la moyenne, la médiane et le mode
- Calculer des mesures de dispersion comme l'écart-type, la variance et l'intervalle
- Effectuer des calculs statistiques sur des axes spécifiques d'un array multidimensionnel

Ces compétences sont essentielles pour l'analyse exploratoire des données et sont fréquemment utilisées dans divers domaines de la data science. Continuez à pratiquer ces concepts pour les maîtriser pleinement !