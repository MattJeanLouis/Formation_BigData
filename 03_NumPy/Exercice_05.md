# Exercice 5 : Traitement d'Images avec NumPy

## Introduction

NumPy est souvent utilisé en traitement d'images car les images peuvent être représentées comme des arrays multidimensionnels. Dans cet exercice, nous allons explorer comment utiliser NumPy pour effectuer des opérations de base sur des images.

Définitions :
- Image numérique : Représentation d'une image bidimensionnelle sous forme d'un nombre fini de valeurs numériques, appelées pixels.
- Pixel : Plus petit élément d'une image numérique, caractérisé par sa position et sa valeur (intensité ou couleur).
- Image en niveaux de gris : Image où chaque pixel est représenté par une seule valeur d'intensité, généralement de 0 (noir) à 255 (blanc).

Dans cet exercice, vous allez apprendre à :
1. Créer et manipuler des images simples avec NumPy
2. Appliquer des filtres de base à des images
3. Effectuer des transformations géométriques sur des images

Note : Pour cet exercice, nous utiliserons Matplotlib pour afficher les images, mais toutes les manipulations seront faites avec NumPy.

## Partie 1 : Création et Manipulation d'Images Simples

### Énoncé

Nous allons créer une image simple en niveaux de gris et effectuer quelques manipulations de base.

### Indices et explications

- Une image en niveaux de gris peut être représentée par un array 2D où chaque élément est une valeur entre 0 (noir) et 255 (blanc).
- NumPy permet de créer facilement des patterns avec des fonctions comme np.zeros(), np.ones(), et np.arange().

### Code à compléter

```python
import numpy as np
import matplotlib.pyplot as plt

# Créez une image 8x8 avec un damier (alternance de 0 et 255)
# Indice : Utilisez np.zeros() et l'indexation pour définir les cases blanches
damier = np.zeros((8, 8), dtype=np.uint8)
damier[::2, 1::2] = 255
damier[1::2, ::2] = 255

# Affichez l'image
plt.imshow(damier, cmap='gray')
plt.title("Damier")
plt.show()

# 1. Créez une image 8x8 avec un gradient vertical (de noir en haut à blanc en bas)
# Indice : Utilisez np.linspace() et np.repeat()
gradient_vertical = # Votre code ici

# Affichez l'image du gradient vertical
plt.imshow(gradient_vertical, cmap='gray')
plt.title("Gradient Vertical")
plt.show()

# 2. Inversez les couleurs du damier (les noirs deviennent blancs et vice versa)
# Indice : Utilisez 255 - damier
damier_inverse = # Votre code ici

# Affichez l'image du damier inversé
plt.imshow(damier_inverse, cmap='gray')
plt.title("Damier Inversé")
plt.show()
```

### Code de test

```python
def test_partie1():
    assert gradient_vertical.shape == (8, 8), "La forme du gradient vertical n'est pas correcte"
    assert np.all(gradient_vertical[:, 0] == gradient_vertical[:, 7]), "Le gradient vertical n'est pas correct"
    assert np.all(gradient_vertical[0] < gradient_vertical[-1]), "Le gradient vertical n'est pas dans le bon sens"
    assert np.all(damier_inverse == 255 - damier), "L'inversion du damier n'est pas correcte"

test_partie1()
print("Tous les tests de la Partie 1 sont passés !")
```

## Partie 2 : Application de Filtres Simples

### Énoncé

Nous allons appliquer des filtres simples à notre image en damier pour comprendre comment les convolutions fonctionnent.

### Indices et explications

- Un filtre (ou noyau de convolution) est une petite matrice qui est appliquée à chaque pixel de l'image.
- La convolution consiste à faire glisser ce filtre sur l'image et à calculer la somme pondérée des pixels voisins.
- Nous utiliserons np.convolve() pour appliquer le filtre.

### Code à compléter

```python
# Fonction pour appliquer un filtre 2D
def appliquer_filtre(image, filtre):
    return np.convolve(image.flatten(), filtre.flatten(), mode='same').reshape(image.shape)

# 1. Créez un filtre de flou (moyenne 3x3)
# Indice : Un filtre de flou est une matrice 3x3 remplie de 1/9
filtre_flou = # Votre code ici

# Appliquez le filtre de flou au damier
damier_flou = appliquer_filtre(damier, filtre_flou)

# Affichez l'image floutée
plt.imshow(damier_flou, cmap='gray')
plt.title("Damier Flouté")
plt.show()

# 2. Créez un filtre de détection de contours (Sobel vertical)
# Indice : Le filtre de Sobel vertical est [[-1, 0, 1], [-2, 0, 2], [-1, 0, 1]]
filtre_sobel = # Votre code ici

# Appliquez le filtre de Sobel au damier
damier_contours = appliquer_filtre(damier, filtre_sobel)

# Affichez l'image des contours
plt.imshow(damier_contours, cmap='gray')
plt.title("Contours du Damier")
plt.show()
```

### Code de test

```python
def test_partie2():
    assert filtre_flou.shape == (3, 3), "La forme du filtre de flou n'est pas correcte"
    assert np.isclose(np.sum(filtre_flou), 1), "La somme des éléments du filtre de flou devrait être 1"
    assert filtre_sobel.shape == (3, 3), "La forme du filtre de Sobel n'est pas correcte"
    assert np.all(filtre_sobel == np.array([[-1, 0, 1], [-2, 0, 2], [-1, 0, 1]])), "Le filtre de Sobel n'est pas correct"

test_partie2()
print("Tous les tests de la Partie 2 sont passés !")
```

## Partie 3 : Transformations Géométriques

### Énoncé

Enfin, nous allons effectuer des transformations géométriques simples sur notre image en damier.

### Indices et explications

- La rotation d'une image peut être réalisée en utilisant des fonctions trigonométriques pour calculer les nouvelles coordonnées de chaque pixel.
- Le redimensionnement peut être effectué en utilisant l'indexation avec des pas fractionnaires.

### Code à compléter

```python
# 1. Effectuez une rotation de 45 degrés du damier
# Indice : Utilisez np.rot90() deux fois pour une rotation de 90 degrés, puis trouvez comment faire 45 degrés
damier_45 = # Votre code ici

# Affichez l'image pivotée
plt.imshow(damier_45, cmap='gray')
plt.title("Damier pivoté de 45 degrés")
plt.show()

# 2. Redimensionnez le damier pour le faire passer de 8x8 à 16x16
# Indice : Utilisez l'indexation avec np.repeat()
damier_16x16 = # Votre code ici

# Affichez l'image redimensionnée
plt.imshow(damier_16x16, cmap='gray')
plt.title("Damier 16x16")
plt.show()
```

### Code de test

```python
def test_partie3():
    assert damier_45.shape == (8, 8), "La forme du damier pivoté n'est pas correcte"
    assert not np.all(damier_45 == damier), "Le damier ne semble pas avoir été pivoté"
    assert damier_16x16.shape == (16, 16), "La forme du damier redimensionné n'est pas correcte"
    assert np.all(damier_16x16[::2, ::2] == damier), "Le redimensionnement n'est pas correct"

test_partie3()
print("Tous les tests de la Partie 3 sont passés !")
```

## Conclusion

Félicitations ! Vous avez terminé l'exercice sur le traitement d'images avec NumPy. Vous avez appris à :
- Créer et manipuler des images simples en utilisant des arrays NumPy
- Appliquer des filtres de base comme le flou et la détection de contours
- Effectuer des transformations géométriques comme la rotation et le redimensionnement

Ces compétences sont fondamentales dans le domaine du traitement d'images et de la vision par ordinateur. Elles peuvent être appliquées à des tâches plus complexes comme la reconnaissance d'objets, la segmentation d'images, et bien plus encore. Continuez à explorer et à expérimenter avec ces concepts !