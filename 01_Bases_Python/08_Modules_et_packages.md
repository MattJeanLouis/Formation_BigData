# Exercice : Modules et Packages en Python

## Introduction

Les modules et packages sont des éléments essentiels en Python qui permettent d'organiser et de réutiliser le code. Ils offrent un moyen d'accéder à une vaste gamme de fonctionnalités prédéfinies et de structurer vos propres programmes.

Définitions :
- Module : Un fichier Python contenant des définitions et des instructions.
- Package : Un dossier contenant plusieurs modules et un fichier spécial __init__.py.
- Bibliothèque standard : Ensemble de modules intégrés à Python, disponibles sans installation supplémentaire.

Dans cet exercice, vous allez apprendre à :
1. Importer et utiliser différents modules de la bibliothèque standard Python
2. Appliquer les fonctionnalités de ces modules pour résoudre des problèmes spécifiques
3. Comprendre l'utilité et la polyvalence des modules en programmation Python

## Exemple Guidé

Avant de commencer l'exercice, voici un exemple détaillé d'utilisation de modules :

```python
import math
import random
import datetime

# Utilisation du module math
rayon = 5
aire_cercle = math.pi * math.pow(rayon, 2)
print(f"L'aire d'un cercle de rayon {rayon} est {aire_cercle:.2f}")

# Utilisation du module random
nombres = [1, 2, 3, 4, 5]
nombre_aleatoire = random.choice(nombres)
print(f"Nombre aléatoire choisi : {nombre_aleatoire}")

# Utilisation du module datetime
maintenant = datetime.datetime.now()
dans_une_semaine = maintenant + datetime.timedelta(days=7)
print(f"Date actuelle : {maintenant}")
print(f"Date dans une semaine : {dans_une_semaine}")
```

Cet exemple montre comment importer et utiliser différents modules pour effectuer des calculs mathématiques, générer des nombres aléatoires et manipuler des dates.

## Exercice : Utilisation de Modules

### Énoncé

Dans cet exercice, vous allez utiliser plusieurs modules de la bibliothèque standard Python pour résoudre différents problèmes.

### Indices et explications

- Le module `math` fournit des fonctions mathématiques avancées.
- Le module `random` permet de générer des nombres aléatoires et de faire des choix aléatoires.
- Le module `json` est utilisé pour travailler avec des données au format JSON.
- Le module `datetime` offre des classes pour manipuler dates et heures.
- Le module `os` permet d'interagir avec le système d'exploitation.
- Le module `re` fournit des outils pour travailler avec les expressions régulières.

### Code à compléter

```python
# Importez les modules nécessaires ici
import math
import random
import json
import datetime
import os
import re

# 1. Utilisez le module 'math' pour calculer la racine carrée de 16 et le cosinus de π/2
def calculs_mathematiques():
    # Indice : Utilisez math.sqrt() pour la racine carrée et math.cos() pour le cosinus
    racine_carree = # Votre code ici
    cosinus = # Votre code ici
    return racine_carree, cosinus

# 2. Utilisez le module 'random' pour générer un nombre aléatoire entre 1 et 100, et pour choisir un élément au hasard dans une liste
def operations_aleatoires():
    # Indice : Utilisez random.randint() pour le nombre et random.choice() pour le choix dans la liste
    nombre_aleatoire = # Votre code ici
    liste = ["python", "java", "c++", "javascript", "ruby"]
    choix_aleatoire = # Votre code ici
    return nombre_aleatoire, choix_aleatoire

# 3. Utilisez le module 'json' pour convertir un dictionnaire en chaîne JSON et vice versa
def manipulation_json():
    # Indice : Utilisez json.dumps() pour convertir en JSON et json.loads() pour convertir de JSON
    dictionnaire = {"nom": "Alice", "age": 30, "ville": "Paris"}
    chaine_json = # Votre code ici
    retour_dictionnaire = # Votre code ici
    return chaine_json, retour_dictionnaire

# 4. Utilisez le module 'datetime' pour obtenir la date et l'heure actuelles, et pour calculer la différence entre deux dates
def operations_dates():
    # Indice : Utilisez datetime.datetime.now() pour la date actuelle et soustrayez les dates pour la différence
    date_actuelle = # Votre code ici
    date_future = datetime.datetime(2025, 1, 1)
    difference = # Votre code ici
    return date_actuelle, difference.days

# 5. Utilisez le module 'os' pour obtenir le répertoire de travail actuel et lister les fichiers qu'il contient
def operations_systeme():
    # Indice : Utilisez os.getcwd() pour le répertoire actuel et os.listdir() pour lister les fichiers
    repertoire_actuel = # Votre code ici
    liste_fichiers = # Votre code ici
    return repertoire_actuel, liste_fichiers

# 6. Utilisez le module 're' pour trouver tous les nombres dans une chaîne de caractères
def extraction_nombres():
    # Indice : Utilisez re.findall() avec une expression régulière pour les chiffres
    texte = "Il y a 3 pommes, 2 oranges et 5 bananes dans le panier."
    nombres = # Votre code ici
    return nombres

# Ne modifiez pas le code ci-dessous
resultats = {
    "calculs_mathematiques": calculs_mathematiques(),
    "operations_aleatoires": operations_aleatoires(),
    "manipulation_json": manipulation_json(),
    "operations_dates": operations_dates(),
    "operations_systeme": operations_systeme(),
    "extraction_nombres": extraction_nombres()
}
```

### Code de test

```python
def test_exercice_modules(resultats):
    assert resultats["calculs_mathematiques"][0] == 4.0, "Le calcul de la racine carrée n'est pas correct"
    assert abs(resultats["calculs_mathematiques"][1]) < 1e-10, "Le calcul du cosinus n'est pas correct"
    
    assert 1 <= resultats["operations_aleatoires"][0] <= 100, "Le nombre aléatoire n'est pas dans la plage correcte"
    assert resultats["operations_aleatoires"][1] in ["python", "java", "c++", "javascript", "ruby"], "Le choix aléatoire n'est pas correct"
    
    assert isinstance(resultats["manipulation_json"][0], str), "La conversion en JSON n'est pas correcte"
    assert resultats["manipulation_json"][1] == {"nom": "Alice", "age": 30, "ville": "Paris"}, "La conversion de JSON en dictionnaire n'est pas correcte"
    
    assert isinstance(resultats["operations_dates"][0], datetime.datetime), "La date actuelle n'est pas correcte"
    assert isinstance(resultats["operations_dates"][1], int) and resultats["operations_dates"][1] > 0, "Le calcul de la différence de dates n'est pas correct"
    
    assert os.path.exists(resultats["operations_systeme"][0]), "Le répertoire actuel n'est pas correct"
    assert isinstance(resultats["operations_systeme"][1], list), "La liste des fichiers n'est pas correcte"
    
    assert resultats["extraction_nombres"] == ['3', '2', '5'], "L'extraction des nombres n'est pas correcte"
    
    print("Félicitations ! Vous avez réussi l'exercice sur les modules et packages.")

test_exercice_modules(resultats)
```

## Conclusion

Félicitations ! Vous avez terminé l'exercice sur les modules et packages en Python. Vous avez appris à :
- Importer et utiliser divers modules de la bibliothèque standard Python
- Effectuer des opérations mathématiques avancées avec le module `math`
- Générer des nombres et faire des choix aléatoires avec le module `random`
- Manipuler des données JSON avec le module `json`
- Travailler avec des dates et des heures en utilisant le module `datetime`
- Interagir avec le système de fichiers grâce au module `os`
- Utiliser des expressions régulières avec le module `re`

Ces compétences sont essentielles pour développer des applications Python plus complexes et efficaces. Les modules de la bibliothèque standard vous offrent une vaste gamme d'outils pour résoudre divers problèmes de programmation. Continuez à explorer d'autres modules et à les intégrer dans vos projets pour tirer pleinement parti de la puissance de Python !