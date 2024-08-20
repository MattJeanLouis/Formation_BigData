# Exercice : Opérations et Expressions en Python

## Introduction

Les opérations et expressions sont au cœur de la programmation en Python. Elles permettent de manipuler des données, effectuer des calculs et prendre des décisions dans vos programmes.

Définitions :
- Opération arithmétique : Calcul mathématique sur des nombres (addition, soustraction, etc.).
- Opération de comparaison : Comparaison de valeurs (égal, supérieur, inférieur, etc.).
- Opération logique : Combinaison de conditions (ET, OU, NON).
- Expression : Combinaison d'opérandes et d'opérateurs qui produit une valeur.

Dans cet exercice, vous allez apprendre à :
1. Effectuer des opérations arithmétiques de base
2. Utiliser des opérateurs de comparaison et logiques
3. Manipuler des chaînes de caractères et des listes avec des expressions

## Partie 1 : Niveau Facile

### Énoncé

Dans cette première partie, nous allons effectuer des calculs simples et des comparaisons de base.

### Indices et explications

- Les opérateurs arithmétiques de base sont : + (addition), - (soustraction), * (multiplication), / (division), % (modulo ou reste de la division).
- Les opérateurs de comparaison incluent : > (supérieur), < (inférieur), == (égal), != (différent).
- Les opérateurs logiques sont : and (ET), or (OU), not (NON).
- L'opérateur 'in' vérifie l'appartenance d'un élément à une séquence.

### Code à compléter

```python
# Utilisez a = 10 et b = 3 pour les calculs suivants
a, b = 10, 3

# 1. Calculez la somme de a et b
somme = # Votre code ici

# 2. Calculez la différence entre a et b
difference = # Votre code ici

# 3. Calculez le produit de a et b
produit = # Votre code ici

# 4. Calculez le quotient (division flottante) de a par b
quotient = # Votre code ici

# 5. Calculez le reste de la division de a par b
# Indice : Utilisez l'opérateur %
reste = # Votre code ici

# 6. Vérifiez si a est supérieur à b
a_superieur_b = # Votre code ici

# 7. Vérifiez si a est égal à 10 ET b est égal à 3
# Indice : Utilisez l'opérateur 'and'
condition_et = # Votre code ici

# 8. Vérifiez si la lettre 'p' est dans le mot 'Python'
# Indice : Utilisez l'opérateur 'in'
p_dans_python = # Votre code ici

# Ne modifiez pas le code ci-dessous
resultats = {
    "somme": somme,
    "difference": difference,
    "produit": produit,
    "quotient": quotient,
    "reste": reste,
    "a_superieur_b": a_superieur_b,
    "condition_et": condition_et,
    "p_dans_python": p_dans_python
}
```

### Code de test

```python
def test_exercice_facile(resultats):
    assert resultats["somme"] == 13, "La somme n'est pas correcte"
    assert resultats["difference"] == 7, "La différence n'est pas correcte"
    assert resultats["produit"] == 30, "Le produit n'est pas correct"
    assert abs(resultats["quotient"] - 3.3333) < 0.0001, "Le quotient n'est pas correct"
    assert resultats["reste"] == 1, "Le reste n'est pas correct"
    assert resultats["a_superieur_b"] == True, "La comparaison n'est pas correcte"
    assert resultats["condition_et"] == True, "La condition ET n'est pas correcte"
    assert resultats["p_dans_python"] == True, "La vérification d'appartenance n'est pas correcte"
    print("Félicitations ! Vous avez réussi l'exercice de niveau facile.")

test_exercice_facile(resultats)
```

## Partie 2 : Niveau Intermédiaire

### Énoncé

Dans cette partie plus avancée, nous allons combiner différentes opérations et expressions pour résoudre des problèmes plus complexes.

### Indices et explications

- Les opérations peuvent être combinées dans des expressions complexes. L'ordre des opérations suit les règles mathématiques standard.
- Les compréhensions de liste permettent de créer des listes en une seule ligne de code.
- Les méthodes de chaînes comme lower() et count() sont utiles pour manipuler et analyser du texte.
- Les expressions conditionnelles (ternaires) permettent d'écrire des if-else en une seule ligne.

### Code à compléter

```python
# 1. Calculez le résultat de l'expression : (a + b) * (a - b) / (a % b), où a = 17 et b = 5
a, b = 17, 5
resultat_complexe = # Votre code ici

# 2. Créez une liste 'nombres' contenant les carrés des nombres de 1 à 5
# Indice : Utilisez une compréhension de liste
nombres = # Votre code ici

# 3. Vérifiez si la somme des éléments de 'nombres' est supérieure à 50 ET si le dernier élément est pair
# Indice : Utilisez sum() pour la somme et % pour vérifier si un nombre est pair
condition_complexe = # Votre code ici

# 4. Créez une chaîne 'phrase' contenant : "Python est un langage de programmation puissant"
phrase = # Votre code ici

# 5. Comptez le nombre de fois où la lettre 'a' apparaît dans 'phrase' (sans tenir compte de la casse)
# Indice : Utilisez lower() et count()
compte_a = # Votre code ici

# 6. Vérifiez si 'phrase' contient le mot "langage" OU le mot "code" (sans tenir compte de la casse)
# Indice : Utilisez lower() et in
contient_mot = # Votre code ici

# 7. Créez une nouvelle liste 'nouveaux_nombres' contenant les éléments de 'nombres' multipliés par 2 si l'élément est pair, sinon divisés par 2
# Indice : Utilisez une compréhension de liste avec une expression conditionnelle
nouveaux_nombres = # Votre code ici

# Ne modifiez pas le code ci-dessous
resultats = {
    "resultat_complexe": resultat_complexe,
    "nombres": nombres,
    "condition_complexe": condition_complexe,
    "phrase": phrase,
    "compte_a": compte_a,
    "contient_mot": contient_mot,
    "nouveaux_nombres": nouveaux_nombres
}
```

### Code de test

```python
def test_exercice_intermediaire(resultats):
    assert abs(resultats["resultat_complexe"] - 132.8) < 0.01, "Le résultat complexe n'est pas correct"
    assert resultats["nombres"] == [1, 4, 9, 16, 25], "La liste 'nombres' n'est pas correcte"
    assert resultats["condition_complexe"] == True, "La condition complexe n'est pas correcte"
    assert resultats["phrase"] == "Python est un langage de programmation puissant", "La phrase n'est pas correcte"
    assert resultats["compte_a"] == 4, "Le compte de 'a' n'est pas correct"
    assert resultats["contient_mot"] == True, "La vérification de présence de mot n'est pas correcte"
    assert resultats["nouveaux_nombres"] == [0.5, 8, 4.5, 32, 12.5], "La liste 'nouveaux_nombres' n'est pas correcte"
    print("Félicitations ! Vous avez réussi l'exercice de niveau intermédiaire.")

test_exercice_intermediaire(resultats)
```

## Conclusion

Félicitations ! Vous avez terminé l'exercice sur les opérations et expressions en Python. Vous avez appris à :
- Effectuer des opérations arithmétiques de base et complexes
- Utiliser des opérateurs de comparaison et logiques
- Manipuler des chaînes de caractères avec des méthodes spécifiques
- Créer et transformer des listes avec des compréhensions et des expressions conditionnelles

Ces compétences sont fondamentales en programmation Python et vous permettront de résoudre une grande variété de problèmes. Continuez à pratiquer ces concepts pour les maîtriser pleinement et les appliquer dans des situations plus complexes !