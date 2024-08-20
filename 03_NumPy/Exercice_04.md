# Exercice 4 : Algèbre Linéaire avec NumPy

## Introduction

NumPy fournit des outils puissants pour l'algèbre linéaire, qui sont essentiels dans de nombreux domaines de la science des données et du machine learning. Dans cet exercice, nous allons explorer comment utiliser NumPy pour effectuer des opérations d'algèbre linéaire courantes.

Définitions :
- Algèbre linéaire : Branche des mathématiques qui traite des vecteurs, des matrices et des systèmes d'équations linéaires.
- Matrice : Tableau rectangulaire de nombres, symboles ou expressions.
- Vecteur : Liste ordonnée de nombres, qui peut être vue comme une matrice avec une seule colonne.

Dans cet exercice, vous allez apprendre à :
1. Effectuer des opérations matricielles de base
2. Résoudre des systèmes d'équations linéaires
3. Calculer des valeurs propres et vecteurs propres

## Partie 1 : Opérations Matricielles de Base

### Énoncé

Nous allons travailler avec des matrices et effectuer des opérations de base sur celles-ci.

### Indices et explications

- La multiplication matricielle n'est pas la même que la multiplication élément par élément.
- La transposée d'une matrice échange ses lignes et ses colonnes.
- Le déterminant est une valeur scalaire qui peut être calculée à partir des éléments d'une matrice carrée.

### Code à compléter

```python
import numpy as np

# Matrices données
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

# 1. Effectuez la multiplication matricielle de A et B
# Indice : Utilisez np.dot() ou l'opérateur @
C = # Votre code ici

# 2. Calculez la transposée de A
# Indice : Utilisez la méthode .T ou np.transpose()
A_transpose = # Votre code ici

# 3. Calculez le déterminant de A
# Indice : Utilisez np.linalg.det()
det_A = # Votre code ici

# Affichez vos résultats
print("Multiplication matricielle A * B:\n", C)
print("Transposée de A:\n", A_transpose)
print("Déterminant de A:", det_A)
```

### Code de test

```python
def test_partie1():
    assert np.allclose(C, np.array([[19, 22], [43, 50]])), "La multiplication matricielle n'est pas correcte"
    assert np.allclose(A_transpose, np.array([[1, 3], [2, 4]])), "La transposée n'est pas correcte"
    assert np.isclose(det_A, -2), "Le déterminant n'est pas correct"

test_partie1()
print("Tous les tests de la Partie 1 sont passés !")
```

## Partie 2 : Résolution de Systèmes d'Équations Linéaires

### Énoncé

Nous allons résoudre un système d'équations linéaires en utilisant NumPy.

### Indices et explications

- Un système d'équations linéaires peut être représenté sous la forme Ax = b, où A est la matrice des coefficients, x est le vecteur des inconnues, et b est le vecteur des termes constants.
- NumPy fournit np.linalg.solve() pour résoudre directement ces systèmes.

### Code à compléter

```python
# Système d'équations:
# 2x + y = 8
# -3x + y = -11

# Matrice des coefficients
A = np.array([[2, 1], [-3, 1]])
# Vecteur des termes constants
b = np.array([8, -11])

# Résolvez le système d'équations
# Indice : Utilisez np.linalg.solve(A, b)
solution = # Votre code ici

# Affichez la solution
print("Solution du système d'équations:")
print("x =", solution[0])
print("y =", solution[1])

# Vérifiez la solution
# Indice : Utilisez np.allclose() pour comparer Ax et b
verification = # Votre code ici

print("La solution est correcte :", verification)
```

### Code de test

```python
def test_partie2():
    assert np.allclose(solution, [3, 2]), "La solution du système d'équations n'est pas correcte"
    assert verification, "La vérification de la solution a échoué"

test_partie2()
print("Tous les tests de la Partie 2 sont passés !")
```

## Partie 3 : Valeurs Propres et Vecteurs Propres

### Énoncé

Nous allons calculer les valeurs propres et les vecteurs propres d'une matrice.

### Indices et explications

- Une valeur propre d'une matrice A est un scalaire λ tel qu'il existe un vecteur non nul v (appelé vecteur propre) satisfaisant Av = λv.
- Les valeurs propres et vecteurs propres sont importants dans de nombreuses applications, comme l'analyse en composantes principales (PCA).

### Code à compléter

```python
# Matrice donnée
A = np.array([[4, -2], [1, 1]])

# Calculez les valeurs propres et les vecteurs propres de A
# Indice : Utilisez np.linalg.eig()
valeurs_propres, vecteurs_propres = # Votre code ici

# Affichez les résultats
print("Valeurs propres :", valeurs_propres)
print("Vecteurs propres :\n", vecteurs_propres)

# Vérifiez que Av = λv pour le premier vecteur propre
# Indice : Comparez A @ v et λ * v
premier_vecteur_propre = vecteurs_propres[:, 0]
verification = # Votre code ici

print("Vérification Av = λv :", verification)
```

### Code de test

```python
def test_partie3():
    assert np.allclose(valeurs_propres, [3, 2]), "Les valeurs propres ne sont pas correctes"
    assert np.allclose(np.abs(vecteurs_propres), np.array([[0.89442719, 0.70710678], [0.4472136, 0.70710678]])), "Les vecteurs propres ne sont pas corrects"
    assert verification, "La vérification Av = λv a échoué"

test_partie3()
print("Tous les tests de la Partie 3 sont passés !")
```

## Conclusion

Félicitations ! Vous avez terminé l'exercice sur l'algèbre linéaire avec NumPy. Vous avez appris à :
- Effectuer des opérations matricielles de base comme la multiplication et la transposition
- Résoudre des systèmes d'équations linéaires
- Calculer et vérifier les valeurs propres et vecteurs propres d'une matrice

Ces compétences sont cruciales dans de nombreux domaines de la data science, du machine learning et de l'optimisation. Elles forment la base de nombreux algorithmes plus avancés. Continuez à pratiquer ces concepts pour les maîtriser pleinement !