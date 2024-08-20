# Exercice 6 : Simulation Monte Carlo avec NumPy

## Introduction

La méthode Monte Carlo est une technique puissante utilisée pour estimer des valeurs numériques en utilisant des échantillonnages aléatoires répétés. Elle est particulièrement utile pour résoudre des problèmes complexes en mathématiques, en physique, et en finance.

Définitions :
- Simulation Monte Carlo : Méthode algorithmique visant à calculer une valeur numérique en utilisant des procédés aléatoires.
- Échantillonnage aléatoire : Processus de sélection d'un sous-ensemble d'individus à partir d'une population plus large.
- Convergence : Tendance d'une série de résultats à se rapprocher d'une valeur spécifique à mesure que le nombre d'essais augmente.

Dans cet exercice, vous allez apprendre à :
1. Estimer la valeur de π (pi) en utilisant la méthode Monte Carlo
2. Simuler le lancer de dés pour estimer des probabilités
3. Calculer une intégrale définie en utilisant la méthode Monte Carlo

## Partie 1 : Estimation de π

### Énoncé

Nous allons estimer la valeur de π en utilisant la méthode Monte Carlo. L'idée est de générer des points aléatoires dans un carré de côté 1, et de déterminer la proportion de ces points qui tombent à l'intérieur d'un quart de cercle inscrit dans ce carré.

### Indices et explications

- L'aire du carré est 1, l'aire du quart de cercle est π/4.
- Le rapport entre le nombre de points dans le cercle et le nombre total de points devrait être proche de π/4.
- Utilisez np.random.random() pour générer des coordonnées aléatoires.

### Code à compléter

```python
import numpy as np

def estimate_pi(n_points):
    # Générez n_points coordonnées x et y aléatoires entre 0 et 1
    x = np.random.random(n_points)
    y = np.random.random(n_points)
    
    # Calculez la distance de chaque point par rapport à l'origine (0, 0)
    distance = np.sqrt(x**2 + y**2)
    
    # Comptez le nombre de points à l'intérieur du cercle (distance <= 1)
    points_inside = np.sum(distance <= 1)
    
    # Estimez pi
    pi_estimate = 4 * points_inside / n_points
    
    return pi_estimate

# Estimez pi avec différents nombres de points
n_points_list = [1000, 10000, 100000, 1000000]

for n in n_points_list:
    pi_approx = estimate_pi(n)
    print(f"Estimation de π avec {n} points : {pi_approx}")
    print(f"Erreur relative : {abs(pi_approx - np.pi) / np.pi * 100:.4f}%")
    print()
```

### Code de test

```python
def test_partie1():
    np.random.seed(42)  # Pour la reproductibilité
    pi_estimate = estimate_pi(1000000)
    assert abs(pi_estimate - np.pi) < 0.01, "L'estimation de π n'est pas assez précise"

test_partie1()
print("Le test de la Partie 1 est passé !")
```

## Partie 2 : Simulation de Lancers de Dés

### Énoncé

Nous allons simuler le lancer de deux dés et estimer la probabilité d'obtenir une somme spécifique.

### Indices et explications

- Utilisez np.random.randint() pour simuler le lancer d'un dé.
- La somme des deux dés peut varier de 2 à 12.
- La probabilité théorique d'obtenir une somme de 7 est 1/6.

### Code à compléter

```python
def simulate_dice_rolls(n_rolls):
    # Simulez n_rolls lancers de deux dés
    # Indice : Utilisez np.random.randint(1, 7, size=(n_rolls, 2))
    dice_rolls = # Votre code ici
    
    # Calculez la somme des deux dés pour chaque lancer
    sums = np.sum(dice_rolls, axis=1)
    
    # Calculez la probabilité d'obtenir chaque somme possible (de 2 à 12)
    probabilities = # Votre code ici
    
    return probabilities

# Simulez 100000 lancers de dés
probs = simulate_dice_rolls(100000)

# Affichez les probabilités
for sum_value, prob in enumerate(probs, start=2):
    print(f"Probabilité de la somme {sum_value}: {prob:.4f}")

# Comparez la probabilité obtenue pour une somme de 7 avec la valeur théorique
print(f"\nProbabilité simulée pour une somme de 7: {probs[5]:.4f}")
print(f"Probabilité théorique pour une somme de 7: {1/6:.4f}")
```

### Code de test

```python
def test_partie2():
    np.random.seed(42)  # Pour la reproductibilité
    probs = simulate_dice_rolls(1000000)
    assert abs(probs[5] - 1/6) < 0.001, "La probabilité simulée pour une somme de 7 n'est pas assez précise"
    assert np.isclose(np.sum(probs), 1), "La somme des probabilités devrait être égale à 1"

test_partie2()
print("Le test de la Partie 2 est passé !")
```

## Partie 3 : Calcul d'Intégrale par Méthode Monte Carlo

### Énoncé

Nous allons utiliser la méthode Monte Carlo pour calculer l'intégrale définie de la fonction f(x) = x^2 sur l'intervalle [0, 1].

### Indices et explications

- L'intégrale de x^2 de 0 à 1 est égale à 1/3.
- La méthode consiste à générer des points aléatoires dans le rectangle [0,1] x [0,1] et à compter la proportion de points sous la courbe de f(x).
- Cette proportion, multipliée par l'aire du rectangle, donne une estimation de l'intégrale.

### Code à compléter

```python
def monte_carlo_integral(n_points):
    # Générez n_points coordonnées x et y aléatoires entre 0 et 1
    x = np.random.random(n_points)
    y = np.random.random(n_points)
    
    # Calculez f(x) = x^2
    f_x = x**2
    
    # Comptez les points sous la courbe (y <= f(x))
    points_under_curve = np.sum(y <= f_x)
    
    # Estimez l'intégrale
    integral_estimate = points_under_curve / n_points
    
    return integral_estimate

# Estimez l'intégrale avec différents nombres de points
n_points_list = [1000, 10000, 100000, 1000000]

for n in n_points_list:
    integral_approx = monte_carlo_integral(n)
    print(f"Estimation de l'intégrale avec {n} points : {integral_approx:.6f}")
    print(f"Erreur relative : {abs(integral_approx - 1/3) / (1/3) * 100:.4f}%")
    print()
```

### Code de test

```python
def test_partie3():
    np.random.seed(42)  # Pour la reproductibilité
    integral_estimate = monte_carlo_integral(1000000)
    assert abs(integral_estimate - 1/3) < 0.001, "L'estimation de l'intégrale n'est pas assez précise"

test_partie3()
print("Le test de la Partie 3 est passé !")
```

## Conclusion

Félicitations ! Vous avez terminé l'exercice sur la simulation Monte Carlo avec NumPy. Vous avez appris à :
- Estimer la valeur de π en utilisant une méthode géométrique
- Simuler des lancers de dés pour estimer des probabilités
- Calculer une intégrale définie en utilisant l'échantillonnage aléatoire

Ces techniques sont largement utilisées dans divers domaines, notamment en finance pour l'évaluation des risques, en physique pour la modélisation de systèmes complexes, et en intelligence artificielle pour l'optimisation d'algorithmes. La méthode Monte Carlo est un outil puissant qui peut être appliqué à une grande variété de problèmes difficiles à résoudre analytiquement.