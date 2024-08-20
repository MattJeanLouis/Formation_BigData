# Exercice 2 : Indexation et Découpage des Arrays NumPy

## Introduction

L'indexation et le découpage sont des opérations fondamentales pour travailler avec des arrays NumPy. Elles vous permettent d'accéder à des éléments spécifiques ou à des sous-ensembles d'un array.

Définitions :
- Indexation : Accéder à un élément spécifique d'un array en utilisant sa position.
- Découpage (Slicing) : Extraire un sous-ensemble d'un array en spécifiant un intervalle.

Dans cet exercice, vous allez apprendre à :
1. Accéder à des éléments spécifiques d'un array 1D et 2D
2. Extraire des sous-arrays en utilisant le découpage
3. Utiliser l'indexation booléenne pour filtrer des données

## Partie 1 : Indexation de base

### Énoncé

Nous allons travailler avec deux arrays : un 1D et un 2D. Votre tâche est d'accéder à des éléments spécifiques de ces arrays.

### Indices et explications

- Pour un array 1D, utilisez un seul index : `array[index]`
- Pour un array 2D, utilisez deux index : `array[ligne, colonne]`
- Les index en Python commencent à 0
- Utilisez des index négatifs pour compter à partir de la fin (-1 est le dernier élément)

### Code à compléter

```python
import numpy as np

# Arrays donnés
array_1d = np.array([1, 2, 3, 4, 5])
array_2d = np.array([[1, 2, 3],
                     [4, 5, 6],
                     [7, 8, 9]])

# 1. Accédez au 3ème élément de array_1d
# Indice : Les indices commencent à 0
element_3 = # Votre code ici

# 2. Accédez au dernier élément de array_1d
# Indice : Utilisez un index négatif
dernier_element = # Votre code ici

# 3. Accédez à l'élément de la 2ème ligne et 3ème colonne de array_2d
# Indice : Rappelez-vous, les indices commencent à 0
element_2_3 = # Votre code ici

# Affichez vos résultats
print("3ème élément de array_1d:", element_3)
print("Dernier élément de array_1d:", dernier_element)
print("Élément de la 2ème ligne et 3ème colonne de array_2d:", element_2_3)
```

### Code de test

```python
def test_partie1():
    assert element_3 == 3, "Le 3ème élément de array_1d devrait être 3"
    assert dernier_element == 5, "Le dernier élément de array_1d devrait être 5"
    assert element_2_3 == 6, "L'élément de la 2ème ligne et 3ème colonne de array_2d devrait être 6"

test_partie1()
print("Tous les tests de la Partie 1 sont passés !")
```

## Partie 2 : Découpage (Slicing)

### Énoncé

Maintenant, nous allons extraire des sous-ensembles de nos arrays en utilisant le découpage.

### Indices et explications

- La syntaxe générale du découpage est `array[start:stop:step]`
- Si `start` est omis, le découpage commence au début de l'array
- Si `stop` est omis, le découpage va jusqu'à la fin de l'array
- Si `step` est omis, il est par défaut 1
- Pour un array 2D, vous pouvez découper sur les deux dimensions : `array[row_start:row_stop, col_start:col_stop]`

### Code à compléter

```python
# 1. Extrayez les 3 premiers éléments de array_1d
# Indice : Utilisez array_1d[:3]
trois_premiers = # Votre code ici

# 2. Extrayez tous les éléments pairs de array_1d (indices 1, 3)
# Indice : Utilisez un pas de 2, en commençant à l'index 1
elements_pairs = # Votre code ici

# 3. Extrayez la première colonne de array_2d
# Indice : Utilisez : pour toutes les lignes, et 0 pour la première colonne
premiere_colonne = # Votre code ici

# 4. Extrayez une sous-matrice 2x2 du coin inférieur droit de array_2d
# Indice : Utilisez le découpage sur les deux dimensions
sous_matrice = # Votre code ici

# Affichez vos résultats
print("Trois premiers éléments de array_1d:", trois_premiers)
print("Éléments pairs de array_1d:", elements_pairs)
print("Première colonne de array_2d:", premiere_colonne)
print("Sous-matrice 2x2 du coin inférieur droit de array_2d:\n", sous_matrice)
```

### Code de test

```python
def test_partie2():
    assert np.all(trois_premiers == [1, 2, 3]), "Les trois premiers éléments de array_1d devraient être [1, 2, 3]"
    assert np.all(elements_pairs == [2, 4]), "Les éléments pairs de array_1d devraient être [2, 4]"
    assert np.all(premiere_colonne == [1, 4, 7]), "La première colonne de array_2d devrait être [1, 4, 7]"
    assert np.all(sous_matrice == [[5, 6], [8, 9]]), "La sous-matrice 2x2 du coin inférieur droit de array_2d devrait être [[5, 6], [8, 9]]"

test_partie2()
print("Tous les tests de la Partie 2 sont passés !")
```

## Partie 3 : Indexation booléenne

### Énoncé

L'indexation booléenne permet de sélectionner des éléments d'un array basés sur une condition.

### Indices et explications

- Créez un masque booléen en appliquant une condition à l'array
- Utilisez ce masque pour indexer l'array original
- Cela retourne un nouvel array contenant uniquement les éléments qui satisfont la condition

### Code à compléter

```python
# Nouvel array pour cette partie
array_data = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])

# 1. Créez un masque booléen pour les éléments supérieurs à 5
# Indice : Utilisez une comparaison (array_data > 5)
masque = # Votre code ici

# 2. Utilisez ce masque pour extraire les éléments supérieurs à 5
# Indice : Utilisez l'indexation avec le masque booléen
elements_sup_5 = # Votre code ici

# 3. Extrayez les éléments pairs de array_data
# Indice : Utilisez l'opérateur modulo % pour tester la parité
elements_pairs = # Votre code ici

# Affichez vos résultats
print("Masque booléen:", masque)
print("Éléments supérieurs à 5:", elements_sup_5)
print("Éléments pairs:", elements_pairs)
```

### Code de test

```python
def test_partie3():
    assert np.all(masque == [False, False, False, False, False, True, True, True, True, True]), "Le masque booléen n'est pas correct"
    assert np.all(elements_sup_5 == [6, 7, 8, 9, 10]), "Les éléments supérieurs à 5 ne sont pas correctement extraits"
    assert np.all(elements_pairs == [2, 4, 6, 8, 10]), "Les éléments pairs ne sont pas correctement extraits"

test_partie3()
print("Tous les tests de la Partie 3 sont passés !")
```

## Conclusion

Félicitations ! Vous avez terminé l'exercice sur l'indexation et le découpage des arrays NumPy. Vous avez appris à :
- Accéder à des éléments spécifiques dans des arrays 1D et 2D
- Extraire des sous-ensembles d'arrays en utilisant le découpage
- Utiliser l'indexation booléenne pour filtrer des données basées sur des conditions

Ces techniques sont essentielles pour manipuler efficacement les données dans NumPy et sont fréquemment utilisées dans l'analyse de données et le machine learning. Continuez à pratiquer ces concepts pour les maîtriser pleinement !