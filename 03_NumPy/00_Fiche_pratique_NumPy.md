# Fiche Pratique NumPy : Blocs Réutilisables

## 1. Importer NumPy
```python
import numpy as np
```
Toujours commencer par importer NumPy. La convention est de l'appeler 'np' pour plus de concision.

## 2. Créer des Arrays

### Array à partir d'une liste
```python
arr = np.array([1, 2, 3, 4, 5])
```
Crée un array 1D à partir d'une liste Python.

### Arrays spéciaux
```python
zeros = np.zeros((3, 3))  # Array 3x3 de zéros
ones = np.ones((2, 2))    # Array 2x2 de uns
arange = np.arange(0, 10, 2)  # Array de 0 à 8 par pas de 2
```
Utile pour initialiser rapidement des arrays avec des valeurs spécifiques.

### Arrays aléatoires
```python
random = np.random.rand(3, 3)  # Array 3x3 de nombres aléatoires entre 0 et 1
```
Parfait pour la simulation ou l'initialisation de poids en machine learning.

## 3. Opérations de Base

### Opérations arithmétiques
```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

sum_arr = a + b  # Addition élément par élément
prod_arr = a * b  # Multiplication élément par élément
squared = a ** 2  # Élévation au carré de chaque élément
```
Ces opérations sont vectorisées, donc très rapides même sur de grands arrays.

### Fonctions mathématiques
```python
sqrt_arr = np.sqrt(a)  # Racine carrée de chaque élément
exp_arr = np.exp(a)    # Exponentielle de chaque élément
log_arr = np.log(a)    # Logarithme naturel de chaque élément
```
NumPy offre une large gamme de fonctions mathématiques optimisées.

## 4. Indexation et Découpage

### Indexation de base
```python
arr = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
element = arr[0, 1]  # Élément de la première ligne, deuxième colonne
row = arr[1]         # Deuxième ligne entière
```
Permet d'accéder à des éléments spécifiques ou des sous-arrays.

### Découpage (Slicing)
```python
sub_arr = arr[:2, 1:]  # Deux premières lignes, à partir de la deuxième colonne
```
Utile pour extraire des sous-ensembles de données.

### Indexation booléenne
```python
mask = arr > 5
filtered = arr[mask]  # Tous les éléments supérieurs à 5
```
Permet de filtrer les données selon des conditions complexes.

## 5. Statistiques Descriptives

### Mesures de tendance centrale
```python
mean = np.mean(arr)    # Moyenne
median = np.median(arr)  # Médiane
```
Donne un aperçu rapide de la distribution des données.

### Mesures de dispersion
```python
std = np.std(arr)   # Écart-type
var = np.var(arr)   # Variance
min_val = np.min(arr)  # Minimum
max_val = np.max(arr)  # Maximum
```
Utile pour comprendre la variabilité des données.

## 6. Algèbre Linéaire

### Opérations matricielles
```python
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

dot_product = np.dot(A, B)  # Produit matriciel
transpose = A.T  # Transposée de A
inverse = np.linalg.inv(A)  # Inverse de A
```
Essentielles pour de nombreuses applications en science des données et machine learning.

### Décompositions matricielles
```python
U, s, V = np.linalg.svd(A)  # Décomposition en valeurs singulières
```
Utile pour la réduction de dimensionnalité et d'autres applications avancées.

## 7. Reshaping et Manipulation d'Arrays

### Changer la forme d'un array
```python
arr = np.array([1, 2, 3, 4, 5, 6])
reshaped = arr.reshape((2, 3))  # Transforme en array 2x3
```
Permet de restructurer vos données sans modifier leur contenu.

### Concaténation d'arrays
```python
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])
concatenated = np.concatenate((arr1, arr2))
```
Utile pour combiner plusieurs arrays.

Chaque bloc de cette fiche pratique est conçu pour être facilement copié-collé et adapté à vos besoins spécifiques. N'hésitez pas à les combiner pour créer des analyses plus complexes !