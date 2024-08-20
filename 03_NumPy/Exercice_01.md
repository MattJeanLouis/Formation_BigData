# Exercice 1 : Manipulation de base des arrays NumPy

## Introduction

NumPy est une bibliothèque Python essentielle pour le calcul scientifique. Son objet principal est le `ndarray` (n-dimensional array), que nous appellerons simplement "array" dans cet exercice.

Définition : Un array NumPy est une grille de valeurs, toutes du même type, indexée par un tuple d'entiers non négatifs.

Dans cet exercice, vous allez apprendre à :
1. Créer différents types d'arrays
2. Effectuer des opérations arithmétiques sur ces arrays
3. Appliquer des fonctions mathématiques aux arrays

## Partie 1 : Création d'arrays

### Énoncé

Nous allons créer trois types d'arrays différents :

1. Un array 1D (unidimensionnel) contenant les nombres de 0 à 9
2. Un array 2D (bidimensionnel) de taille 3x3 rempli de zéros
3. Un array 1D de 5 nombres aléatoires entre 0 et 1

### Indices et explications

- Pour créer un array de 0 à 9, utilisez `np.arange()`. Cette fonction génère des valeurs dans un intervalle donné.
- Pour un array 2D de zéros, utilisez `np.zeros()`. Cette fonction crée un array rempli de zéros.
- Pour des nombres aléatoires, utilisez `np.random.rand()`. Cette fonction génère des nombres aléatoires uniformément distribués entre 0 et 1.

### Code à compléter

```python
import numpy as np

# a) Array 1D de 0 à 9
# Indice : np.arange(start, stop)
array_1d = # Votre code ici

# b) Array 2D 3x3 de zéros
# Indice : np.zeros((lignes, colonnes))
array_2d = # Votre code ici

# c) Array 1D de 5 nombres aléatoires entre 0 et 1
# Indice : np.random.rand(nombre_d_elements)
array_random = # Votre code ici

# Affichez vos résultats
print("Array 1D:", array_1d)
print("Array 2D:\n", array_2d)
print("Array aléatoire:", array_random)
```

### Code de test

```python
def test_partie1():
    assert array_1d.shape == (10,), "L'array 1D devrait avoir 10 éléments"
    assert np.all(array_1d == np.arange(10)), "L'array 1D devrait contenir les nombres de 0 à 9"
    
    assert array_2d.shape == (3, 3), "L'array 2D devrait être de taille 3x3"
    assert np.all(array_2d == 0), "L'array 2D devrait être rempli de zéros"
    
    assert array_random.shape == (5,), "L'array aléatoire devrait avoir 5 éléments"
    assert np.all((0 <= array_random) & (array_random < 1)), "L'array aléatoire devrait contenir des nombres entre 0 et 1"

test_partie1()
print("Tous les tests de la Partie 1 sont passés !")
```

## Partie 2 : Opérations arithmétiques

### Énoncé

Maintenant, nous allons effectuer des opérations arithmétiques sur les arrays que nous avons créés :

1. Ajouter 5 à chaque élément de `array_1d`
2. Multiplier chaque élément de `array_2d` par 2
3. Calculer la racine carrée de chaque élément de `array_random`

### Indices et explications

- NumPy permet d'effectuer des opérations "vectorisées" : une seule opération s'applique à tous les éléments de l'array.
- Pour la racine carrée, utilisez `np.sqrt()`. Cette fonction calcule la racine carrée de chaque élément de l'array.

### Code à compléter

```python
# 1. Ajouter 5 à array_1d
# Indice : Utilisez simplement l'opérateur +
array_1d_plus5 = # Votre code ici

# 2. Multiplier array_2d par 2
# Indice : Utilisez simplement l'opérateur *
array_2d_fois2 = # Votre code ici

# 3. Racine carrée de array_random
# Indice : Utilisez np.sqrt()
array_random_sqrt = # Votre code ici

# Affichez vos résultats
print("Array 1D + 5:", array_1d_plus5)
print("Array 2D * 2:\n", array_2d_fois2)
print("Racine carrée de l'array aléatoire:", array_random_sqrt)
```

### Code de test

```python
def test_partie2():
    assert np.all(array_1d_plus5 == array_1d + 5), "L'addition de 5 à array_1d n'est pas correcte"
    assert np.all(array_2d_fois2 == array_2d * 2), "La multiplication de array_2d par 2 n'est pas correcte"
    assert np.allclose(array_random_sqrt, np.sqrt(array_random)), "Le calcul de la racine carrée de array_random n'est pas correct"

test_partie2()
print("Tous les tests de la Partie 2 sont passés !")
```

## Partie 3 : Fonctions mathématiques

### Énoncé

Enfin, nous allons appliquer des fonctions mathématiques à `array_1d` :

1. Calculer le sinus de chaque élément
2. Calculer l'exponentielle de chaque élément
3. Arrondir chaque élément à l'entier le plus proche

### Indices et explications

- Le sinus est calculé avec `np.sin()`. Cette fonction trigonométrique prend des angles en radians.
- L'exponentielle (e^x) est calculée avec `np.exp()`.
- Pour arrondir à l'entier le plus proche, utilisez `np.round()`.

### Code à compléter

```python
# 1. Sinus de array_1d
# Indice : Utilisez np.sin()
array_1d_sin = # Votre code ici

# 2. Exponentielle de array_1d
# Indice : Utilisez np.exp()
array_1d_exp = # Votre code ici

# 3. Arrondi de array_1d
# Indice : Utilisez np.round()
array_1d_round = # Votre code ici

# Affichez vos résultats
print("Sinus de array_1d:", array_1d_sin)
print("Exponentielle de array_1d:", array_1d_exp)
print("Arrondi de array_1d:", array_1d_round)
```

### Code de test

```python
def test_partie3():
    assert np.allclose(array_1d_sin, np.sin(array_1d)), "Le calcul du sinus n'est pas correct"
    assert np.allclose(array_1d_exp, np.exp(array_1d)), "Le calcul de l'exponentielle n'est pas correct"
    assert np.all(array_1d_round == np.round(array_1d)), "L'arrondi n'est pas correct"

test_partie3()
print("Tous les tests de la Partie 3 sont passés !")
```

## Conclusion

Félicitations ! Vous avez terminé l'exercice sur la manipulation de base des arrays NumPy. Vous avez appris à :
- Créer différents types d'arrays (1D, 2D, avec des valeurs spécifiques ou aléatoires)
- Effectuer des opérations arithmétiques vectorisées sur ces arrays
- Appliquer des fonctions mathématiques courantes aux arrays

Ces compétences sont fondamentales pour l'analyse de données et le calcul scientifique avec Python. N'hésitez pas à expérimenter davantage avec ces fonctions et à explorer la documentation NumPy pour découvrir d'autres fonctionnalités utiles !