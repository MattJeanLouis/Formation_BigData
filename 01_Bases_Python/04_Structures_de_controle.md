# Exercice : Structures de Contrôle en Python

## Introduction

Les structures de contrôle sont essentielles en programmation car elles permettent de contrôler le flux d'exécution d'un programme. En Python, les principales structures de contrôle sont les conditions et les boucles.

Définitions :
- Condition (if, elif, else) : Permet d'exécuter différents blocs de code selon que certaines conditions sont vraies ou fausses.
- Boucle for : Permet de répéter un bloc de code un nombre défini de fois.
- Boucle while : Permet de répéter un bloc de code tant qu'une condition est vraie.

Dans cet exercice, vous allez apprendre à :
1. Utiliser des conditions pour prendre des décisions dans votre code
2. Créer des boucles pour répéter des actions
3. Combiner conditions et boucles pour résoudre des problèmes plus complexes

## Partie 1 : Niveau Facile

### Énoncé

Dans cette première partie, nous allons écrire des fonctions simples utilisant des conditions et des boucles.

### Indices et explications

- L'opérateur modulo % retourne le reste de la division. Il est utile pour vérifier si un nombre est pair (x % 2 == 0).
- La boucle for peut être utilisée avec range() pour répéter une action un certain nombre de fois.
- La boucle while continue tant que sa condition est vraie. N'oubliez pas de modifier la condition dans la boucle pour éviter une boucle infinie.

### Code à compléter

```python
# 1. Écrivez une fonction 'est_pair' qui prend un nombre en paramètre et retourne 'pair' s'il est pair, 'impair' sinon
def est_pair(nombre):
    # Indice : Utilisez l'opérateur modulo % et une condition if-else
    # Votre code ici
    pass

# 2. Écrivez une fonction 'salutation' qui prend un nom en paramètre et retourne 'Bonjour [nom]' si le nom est fourni, sinon 'Bonjour invité'
def salutation(nom=None):
    # Indice : Utilisez une condition if-else et l'opérateur de formatage de chaîne f"..."
    # Votre code ici
    pass

# 3. Utilisez une boucle for pour créer une liste 'carres' contenant les carrés des nombres de 1 à 5
carres = []
# Indice : Utilisez range(1, 6) dans votre boucle for
# Votre code ici

# 4. Utilisez une boucle while pour créer une liste 'compte_a_rebours' contenant les nombres de 5 à 1 dans l'ordre décroissant
compte_a_rebours = []
# Indice : Initialisez une variable à 5 et décrémentez-la dans la boucle
# Votre code ici

# Ne modifiez pas le code ci-dessous
resultats = {
    "est_pair_4": est_pair(4),
    "est_pair_7": est_pair(7),
    "salutation_Alice": salutation("Alice"),
    "salutation_sans_nom": salutation(),
    "carres": carres,
    "compte_a_rebours": compte_a_rebours
}
```

### Code de test

```python
def test_exercice_facile(resultats):
    assert resultats["est_pair_4"] == "pair", "La fonction est_pair ne fonctionne pas correctement pour 4"
    assert resultats["est_pair_7"] == "impair", "La fonction est_pair ne fonctionne pas correctement pour 7"
    assert resultats["salutation_Alice"] == "Bonjour Alice", "La fonction salutation ne fonctionne pas correctement avec un nom"
    assert resultats["salutation_sans_nom"] == "Bonjour invité", "La fonction salutation ne fonctionne pas correctement sans nom"
    assert resultats["carres"] == [1, 4, 9, 16, 25], "La liste carres n'est pas correcte"
    assert resultats["compte_a_rebours"] == [5, 4, 3, 2, 1], "La liste compte_a_rebours n'est pas correcte"
    print("Félicitations ! Vous avez réussi l'exercice de niveau facile.")

test_exercice_facile(resultats)
```

## Partie 2 : Niveau Intermédiaire

### Énoncé

Dans cette partie plus avancée, nous allons utiliser des structures de contrôle plus complexes et résoudre des problèmes mathématiques.

### Indices et explications

- La suite de Fibonacci commence par 0 et 1, puis chaque nombre suivant est la somme des deux précédents.
- Un nombre premier est un nombre naturel supérieur à 1 qui n'est divisible que par 1 et par lui-même.
- L'instruction break permet de sortir immédiatement d'une boucle.
- L'instruction continue permet de passer directement à l'itération suivante d'une boucle.

### Code à compléter

```python
# 1. Écrivez une fonction 'fibonacci' qui prend un nombre n en paramètre et retourne une liste des n premiers nombres de la suite de Fibonacci
def fibonacci(n):
    # Indice : Initialisez la liste avec [0, 1] et utilisez une boucle pour ajouter les nombres suivants
    # Votre code ici
    pass

# 2. Écrivez une fonction 'premier' qui prend un nombre en paramètre et retourne True s'il est premier, False sinon
def premier(nombre):
    # Indice : Un nombre est premier s'il n'est divisible que par 1 et lui-même
    # Votre code ici
    pass

# 3. Utilisez une boucle et la fonction 'premier' pour créer une liste 'nombres_premiers' contenant tous les nombres premiers inférieurs à 50
nombres_premiers = []
# Indice : Utilisez une boucle for avec range() et la fonction premier()
# Votre code ici

# 4. Écrivez une fonction 'somme_pairs' qui prend une liste de nombres en paramètre et retourne la somme de tous les nombres pairs de la liste
def somme_pairs(nombres):
    # Indice : Utilisez une boucle for et une condition pour vérifier si chaque nombre est pair
    # Votre code ici
    pass

# 5. Utilisez une boucle for avec 'break' pour trouver le premier nombre divisible par 7 et 3 entre 1 et 100
premier_divisible = None
# Indice : Utilisez une boucle for avec range(1, 101) et une condition avec break
# Votre code ici

# Ne modifiez pas le code ci-dessous
resultats = {
    "fibonacci_7": fibonacci(7),
    "premier_17": premier(17),
    "premier_24": premier(24),
    "nombres_premiers": nombres_premiers,
    "somme_pairs": somme_pairs([1, 2, 3, 4, 5, 6, 7, 8, 9, 10]),
    "premier_divisible": premier_divisible
}
```

### Code de test

```python
def test_exercice_intermediaire(resultats):
    assert resultats["fibonacci_7"] == [0, 1, 1, 2, 3, 5, 8], "La fonction fibonacci ne fonctionne pas correctement"
    assert resultats["premier_17"] == True, "La fonction premier ne fonctionne pas correctement pour 17"
    assert resultats["premier_24"] == False, "La fonction premier ne fonctionne pas correctement pour 24"
    assert resultats["nombres_premiers"] == [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47], "La liste nombres_premiers n'est pas correcte"
    assert resultats["somme_pairs"] == 30, "La fonction somme_pairs ne fonctionne pas correctement"
    assert resultats["premier_divisible"] == 21, "Le premier nombre divisible par 7 et 3 n'est pas correct"
    print("Félicitations ! Vous avez réussi l'exercice de niveau intermédiaire.")

test_exercice_intermediaire(resultats)
```

## Conclusion

Félicitations ! Vous avez terminé l'exercice sur les structures de contrôle en Python. Vous avez appris à :
- Utiliser des conditions if-elif-else pour prendre des décisions dans votre code
- Créer des boucles for et while pour répéter des actions
- Résoudre des problèmes mathématiques en utilisant des structures de contrôle
- Utiliser break pour sortir d'une boucle prématurément

Ces compétences sont fondamentales en programmation et vous permettront de créer des programmes plus complexes et flexibles. Continuez à pratiquer ces concepts en les appliquant à différents problèmes pour les maîtriser pleinement !