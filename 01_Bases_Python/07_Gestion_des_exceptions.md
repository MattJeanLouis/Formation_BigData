# Exercice : Gestion des Exceptions en Python

## Introduction

La gestion des exceptions est une partie cruciale de la programmation en Python. Elle permet de gérer les erreurs de manière élégante, rendant vos programmes plus robustes et conviviaux.

Définitions :
- Exception : Un événement qui se produit pendant l'exécution d'un programme et qui perturbe le flux normal des instructions.
- Try-Except : Structure de code permettant de gérer les exceptions.
- Raise : Mot-clé utilisé pour lever manuellement une exception.
- Exception personnalisée : Une nouvelle classe d'exception créée par le programmeur.

Dans cet exercice, vous allez apprendre à :
1. Gérer différents types d'exceptions courantes
2. Utiliser des blocs try-except pour capturer et traiter les exceptions
3. Créer et lever vos propres exceptions personnalisées

## Partie 1 : Gestion des Exceptions de Base

### Énoncé

Dans cette partie, nous allons créer plusieurs fonctions qui gèrent différents types d'exceptions courantes.

### Indices et explications

- Utilisez un bloc try-except pour capturer les exceptions.
- La structure de base est : 
  ```python
  try:
      # Code susceptible de lever une exception
  except TypeException:
      # Code à exécuter si l'exception est levée
  ```
- Pour lire un fichier, utilisez `with open(nom_fichier, 'r') as f:`.

### Code à compléter

```python
# 1. Créez une fonction 'diviser' qui prend deux nombres en paramètres et retourne leur quotient.
# Gérez l'exception ZeroDivisionError et retournez "Division par zéro impossible" dans ce cas.
def diviser(a, b):
    # Indice : Utilisez un bloc try-except avec ZeroDivisionError
    # Votre code ici
    pass

# 2. Créez une fonction 'lire_fichier' qui prend un nom de fichier en paramètre et affiche son contenu.
# Gérez l'exception FileNotFoundError et retournez "Fichier non trouvé" dans ce cas.
def lire_fichier(nom_fichier):
    # Indice : Utilisez 'with open()' dans un bloc try-except
    # Votre code ici
    pass

# 3. Créez une fonction 'convertir_en_entier' qui prend une chaîne de caractères en paramètre et la convertit en entier.
# Gérez l'exception ValueError et retournez "Conversion impossible" dans ce cas.
def convertir_en_entier(chaine):
    # Indice : Utilisez int() dans un bloc try-except
    # Votre code ici
    pass

# 4. Créez une fonction 'acceder_element' qui prend une liste et un index en paramètres et retourne l'élément à cet index.
# Gérez l'exception IndexError et retournez "Index hors limites" dans ce cas.
def acceder_element(liste, index):
    # Indice : Accédez à l'élément avec liste[index] dans un bloc try-except
    # Votre code ici
    pass

# Ne modifiez pas le code ci-dessous
resultats = {
    "diviser": [
        diviser(10, 2),
        diviser(10, 0)
    ],
    "lire_fichier": [
        lire_fichier("fichier_existant.txt"),
        lire_fichier("fichier_inexistant.txt")
    ],
    "convertir_en_entier": [
        convertir_en_entier("42"),
        convertir_en_entier("abc")
    ],
    "acceder_element": [
        acceder_element([1, 2, 3], 1),
        acceder_element([1, 2, 3], 5)
    ]
}
```

## Partie 2 : Exceptions Personnalisées

### Énoncé

Dans cette partie, nous allons créer une fonction qui utilise une exception personnalisée.

### Indices et explications

- Pour créer une exception personnalisée, définissez une nouvelle classe qui hérite de `Exception`.
- Utilisez `raise` pour lever manuellement une exception.
- Vous pouvez avoir plusieurs blocs `except` pour gérer différents types d'exceptions.

### Code à compléter

```python
# 5. Créez une fonction 'effectuer_operation' qui prend deux nombres et une opération ('+', '-', '*', '/') en paramètres.
# Effectuez l'opération demandée et gérez toutes les exceptions possibles.
# Si l'opération n'est pas reconnue, levez une exception personnalisée OperationInvalideError.
class OperationInvalideError(Exception):
    pass

def effectuer_operation(a, b, operation):
    # Indice : Utilisez un dictionnaire pour mapper les opérations aux fonctions correspondantes
    # N'oubliez pas de gérer ZeroDivisionError pour la division
    # Votre code ici
    pass

# Ne modifiez pas le code ci-dessous
resultats["effectuer_operation"] = [
    effectuer_operation(10, 5, "+"),
    effectuer_operation(10, 0, "/"),
    effectuer_operation(10, 5, "%")
]
```

### Code de test

```python
def test_exercice_exceptions(resultats):
    assert resultats["diviser"] == [5.0, "Division par zéro impossible"], "La fonction diviser ne gère pas correctement les exceptions"
    assert resultats["lire_fichier"][1] == "Fichier non trouvé", "La fonction lire_fichier ne gère pas correctement l'exception FileNotFoundError"
    assert resultats["convertir_en_entier"] == [42, "Conversion impossible"], "La fonction convertir_en_entier ne gère pas correctement les exceptions"
    assert resultats["acceder_element"] == [2, "Index hors limites"], "La fonction acceder_element ne gère pas correctement les exceptions"
    assert resultats["effectuer_operation"][:2] == [15, "Division par zéro impossible"], "La fonction effectuer_operation ne gère pas correctement les exceptions de base"
    try:
        resultats["effectuer_operation"][2]
    except OperationInvalideError:
        print("Félicitations ! Vous avez réussi l'exercice sur la gestion des exceptions.")
    else:
        raise AssertionError("La fonction effectuer_operation ne lève pas correctement l'exception OperationInvalideError")

test_exercice_exceptions(resultats)
```

## Conclusion

Félicitations ! Vous avez terminé l'exercice sur la gestion des exceptions en Python. Vous avez appris à :
- Gérer différents types d'exceptions courantes comme ZeroDivisionError, FileNotFoundError, ValueError, et IndexError
- Utiliser des blocs try-except pour capturer et traiter les exceptions
- Créer et lever vos propres exceptions personnalisées

Ces compétences sont essentielles pour écrire des programmes Python robustes qui peuvent gérer élégamment les situations d'erreur. La gestion des exceptions vous permet de créer des applications plus fiables et conviviales. Continuez à pratiquer en intégrant la gestion des exceptions dans vos futurs projets Python !