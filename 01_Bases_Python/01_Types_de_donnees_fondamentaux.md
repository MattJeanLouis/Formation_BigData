# Exercice : Types de Données Fondamentaux en Python

## Introduction

En Python, comprendre et manipuler les types de données fondamentaux est essentiel pour tout programmeur. Ces types de base sont les briques avec lesquelles nous construisons des programmes plus complexes.

Définitions :
- Type de données : Catégorie de valeurs que peut prendre une variable.
- Variable : Espace de stockage nommé qui contient une valeur d'un certain type.

Dans cet exercice, vous allez apprendre à :
1. Créer et manipuler des variables de différents types fondamentaux
2. Effectuer des opérations de base sur ces variables
3. Convertir des variables d'un type à un autre

## Partie 1 : Niveau Facile

### Énoncé

Dans cette première partie, nous allons créer des variables de différents types et effectuer quelques opérations simples.

### Indices et explications

- Entier (int) : Nombre entier sans décimale, par exemple 42.
- Flottant (float) : Nombre à virgule flottante, par exemple 3.14.
- Chaîne de caractères (str) : Séquence de caractères entre guillemets, par exemple "Python".
- Booléen (bool) : Valeur logique True (vrai) ou False (faux).
- L'opérateur + peut être utilisé pour concaténer des chaînes de caractères.

### Code à compléter

```python
# 1. Créez une variable 'age' de type entier avec votre âge
age = # Votre code ici

# 2. Créez une variable 'taille' de type float avec votre taille en mètres
taille = # Votre code ici

# 3. Créez une variable 'nom' de type string avec votre nom
nom = # Votre code ici

# 4. Créez une variable 'est_etudiant' de type booléen indiquant si vous êtes étudiant ou non
est_etudiant = # Votre code ici

# 5. Calculez votre année de naissance en soustrayant votre âge de l'année actuelle (2023)
# Indice : Utilisez l'opérateur de soustraction -
annee_naissance = # Votre code ici

# 6. Créez une chaîne de caractères 'presentation' qui dit "Je m'appelle [votre nom] et j'ai [votre âge] ans."
# Indice : Utilisez la f-string (f"...") pour inclure des variables dans une chaîne
presentation = # Votre code ici

# Ne modifiez pas le code ci-dessous
resultats = {
    "age": age,
    "taille": taille,
    "nom": nom,
    "est_etudiant": est_etudiant,
    "annee_naissance": annee_naissance,
    "presentation": presentation
}
```

### Code de test

```python
def test_exercice_facile(resultats):
    assert isinstance(resultats["age"], int), "L'âge doit être un entier"
    assert isinstance(resultats["taille"], float), "La taille doit être un float"
    assert isinstance(resultats["nom"], str), "Le nom doit être une chaîne de caractères"
    assert isinstance(resultats["est_etudiant"], bool), "est_etudiant doit être un booléen"
    assert isinstance(resultats["annee_naissance"], int), "L'année de naissance doit être un entier"
    assert resultats["annee_naissance"] == 2023 - resultats["age"], "L'année de naissance n'est pas correcte"
    assert resultats["presentation"] == f"Je m'appelle {resultats['nom']} et j'ai {resultats['age']} ans.", "La présentation n'est pas correcte"
    print("Félicitations ! Vous avez réussi l'exercice de niveau facile.")

test_exercice_facile(resultats)
```

## Partie 2 : Niveau Intermédiaire

### Énoncé

Dans cette partie plus avancée, nous allons travailler avec des opérations plus complexes sur les types de données fondamentaux, y compris des conversions de types et des manipulations de chaînes de caractères.

### Indices et explications

- La notation avec underscores peut être utilisée pour rendre les grands nombres plus lisibles, par exemple 1_000_000.
- Les fonctions str(), int(), et float() peuvent être utilisées pour convertir entre différents types.
- Les méthodes upper() et lower() peuvent être utilisées pour changer la casse d'une chaîne.
- La fonction len() retourne la longueur d'une séquence, comme une chaîne de caractères.
- L'opérateur in peut être utilisé pour vérifier si une sous-chaîne est présente dans une chaîne.

### Code à compléter

```python
# 1. Créez une variable 'grand_nombre' de type int avec la valeur 1 million, en utilisant la notation avec underscores
grand_nombre = # Votre code ici

# 2. Créez une variable 'pi_approx' de type float avec la valeur approximative de pi (3.14159)
pi_approx = # Votre code ici

# 3. Créez une variable 'message' de type string contenant : Python est "incroyable" !
# Indice : Utilisez des guillemets simples pour entourer toute la chaîne
message = # Votre code ici

# 4. Convertissez 'grand_nombre' en une chaîne de caractères et stockez-le dans 'grand_nombre_str'
# Indice : Utilisez la fonction str()
grand_nombre_str = # Votre code ici

# 5. Convertissez 'pi_approx' en un entier et stockez-le dans 'pi_entier'
# Indice : Utilisez la fonction int()
pi_entier = # Votre code ici

# 6. Créez une variable 'message_uppercase' qui contient 'message' en majuscules
# Indice : Utilisez la méthode upper()
message_uppercase = # Votre code ici

# 7. Calculez la longueur de 'message' et stockez-la dans 'longueur_message'
# Indice : Utilisez la fonction len()
longueur_message = # Votre code ici

# 8. Vérifiez si 'message' contient le mot "Python" et stockez le résultat dans 'contient_python'
# Indice : Utilisez l'opérateur in
contient_python = # Votre code ici

# Ne modifiez pas le code ci-dessous
resultats = {
    "grand_nombre": grand_nombre,
    "pi_approx": pi_approx,
    "message": message,
    "grand_nombre_str": grand_nombre_str,
    "pi_entier": pi_entier,
    "message_uppercase": message_uppercase,
    "longueur_message": longueur_message,
    "contient_python": contient_python
}
```

### Code de test

```python
def test_exercice_intermediaire(resultats):
    assert resultats["grand_nombre"] == 1_000_000, "grand_nombre doit être égal à 1 million"
    assert abs(resultats["pi_approx"] - 3.14159) < 0.00001, "pi_approx doit être approximativement égal à 3.14159"
    assert resultats["message"] == 'Python est "incroyable" !', "Le message n'est pas correct"
    assert resultats["grand_nombre_str"] == "1000000", "La conversion de grand_nombre en string n'est pas correcte"
    assert resultats["pi_entier"] == 3, "La conversion de pi_approx en entier n'est pas correcte"
    assert resultats["message_uppercase"] == 'PYTHON EST "INCROYABLE" !', "La conversion en majuscules n'est pas correcte"
    assert resultats["longueur_message"] == 24, "La longueur du message n'est pas correcte"
    assert resultats["contient_python"] == True, "La vérification de la présence de 'Python' n'est pas correcte"
    print("Félicitations ! Vous avez réussi l'exercice de niveau intermédiaire.")

test_exercice_intermediaire(resultats)
```

## Conclusion

Félicitations ! Vous avez terminé l'exercice sur les types de données fondamentaux en Python. Vous avez appris à :
- Créer et manipuler des variables de différents types (int, float, str, bool)
- Effectuer des opérations de base sur ces variables
- Convertir des variables d'un type à un autre
- Manipuler des chaînes de caractères (mise en majuscules, calcul de longueur, recherche de sous-chaîne)

Ces compétences sont essentielles pour tout programmeur Python et forment la base sur laquelle vous construirez des programmes plus complexes. Continuez à pratiquer et à explorer ces concepts !