# Exercice : Programmation Orientée Objet en Python

## Introduction

La Programmation Orientée Objet (POO) est un paradigme de programmation qui organise le code en objets, qui sont des instances de classes. Elle permet de créer des programmes plus modulaires, réutilisables et faciles à maintenir.

Définitions :
- Classe : Un modèle pour créer des objets, définissant leurs attributs et méthodes.
- Objet : Une instance d'une classe, avec ses propres valeurs d'attributs.
- Attribut : Une variable appartenant à un objet ou une classe.
- Méthode : Une fonction appartenant à une classe, définissant le comportement des objets.
- Héritage : Un mécanisme permettant à une classe d'hériter des attributs et méthodes d'une autre classe.

Dans cet exercice, vous allez apprendre à :
1. Créer des classes simples avec des attributs et des méthodes
2. Utiliser l'héritage pour créer des hiérarchies de classes
3. Implémenter des méthodes spéciales pour personnaliser le comportement des objets

## Partie 1 : Niveau Facile

### Énoncé

Dans cette première partie, nous allons créer une classe simple représentant un rectangle.

### Indices et explications

- La méthode `__init__` est le constructeur de la classe, appelé lors de la création d'un objet.
- `self` fait référence à l'instance de l'objet en cours.
- Les méthodes de classe prennent toujours `self` comme premier argument.

### Code à compléter

```python
# 1. Créez une classe 'Rectangle' avec les attributs 'longueur' et 'largeur'
# Ajoutez une méthode 'aire' qui retourne l'aire du rectangle
# Ajoutez une méthode 'perimetre' qui retourne le périmètre du rectangle
class Rectangle:
    def __init__(self, longueur, largeur):
        # Indice : Utilisez self.attribut = valeur pour définir les attributs
        # Votre code ici
        pass

    def aire(self):
        # Indice : L'aire d'un rectangle est longueur * largeur
        # Votre code ici
        pass

    def perimetre(self):
        # Indice : Le périmètre d'un rectangle est 2 * (longueur + largeur)
        # Votre code ici
        pass

# Ne modifiez pas le code ci-dessous
rectangle = Rectangle(5, 3)
resultats = {
    "aire": rectangle.aire(),
    "perimetre": rectangle.perimetre()
}
```

### Code de test

```python
def test_exercice_facile(resultats):
    assert resultats["aire"] == 15, "La méthode aire ne fonctionne pas correctement"
    assert resultats["perimetre"] == 16, "La méthode perimetre ne fonctionne pas correctement"
    print("Félicitations ! Vous avez réussi l'exercice de niveau facile.")

test_exercice_facile(resultats)
```

## Partie 2 : Niveau Intermédiaire

### Énoncé

Dans cette partie, nous allons travailler avec l'héritage en créant une hiérarchie de classes pour des véhicules.

### Indices et explications

- Pour créer une classe qui hérite d'une autre, utilisez `class SousClasse(ClasseParente):`.
- `super().__init__()` permet d'appeler le constructeur de la classe parente.
- La surcharge de méthode consiste à redéfinir une méthode dans une sous-classe.

### Code à compléter

```python
# 1. Créez une classe 'Vehicule' avec les attributs 'marque' et 'modele'
# Ajoutez une méthode 'description' qui retourne une chaîne décrivant le véhicule
class Vehicule:
    def __init__(self, marque, modele):
        # Votre code ici
        pass

    def description(self):
        # Indice : Retournez une chaîne formatée avec la marque et le modèle
        # Votre code ici
        pass

# 2. Créez une classe 'Voiture' qui hérite de 'Vehicule'
# Ajoutez un attribut 'nombre_portes'
# Surchargez la méthode 'description' pour inclure le nombre de portes
class Voiture(Vehicule):
    def __init__(self, marque, modele, nombre_portes):
        # Indice : Utilisez super().__init__() pour appeler le constructeur parent
        # Votre code ici
        pass

    def description(self):
        # Indice : Utilisez la méthode description de la classe parente et ajoutez-y le nombre de portes
        # Votre code ici
        pass

# Ne modifiez pas le code ci-dessous
vehicule = Vehicule("Toyota", "Corolla")
voiture = Voiture("Renault", "Clio", 5)
resultats = {
    "description_vehicule": vehicule.description(),
    "description_voiture": voiture.description()
}
```

### Code de test

```python
def test_exercice_intermediaire(resultats):
    assert resultats["description_vehicule"] == "Toyota Corolla", "La méthode description de Vehicule ne fonctionne pas correctement"
    assert resultats["description_voiture"] == "Renault Clio avec 5 portes", "La méthode description de Voiture ne fonctionne pas correctement"
    print("Félicitations ! Vous avez réussi l'exercice de niveau intermédiaire.")

test_exercice_intermediaire(resultats)
```

## Partie 3 : Niveau Avancé

### Énoncé

Dans cette partie avancée, nous allons travailler avec des méthodes spéciales et créer une hiérarchie de classes plus complexe pour représenter des comptes bancaires.

### Indices et explications

- Les méthodes spéciales (ou "dunder methods") sont entourées de doubles underscores, comme `__str__`.
- `__str__` est appelée quand on utilise `str(objet)` ou `print(objet)`.
- `__add__` et `__sub__` permettent de définir le comportement des opérateurs + et - pour vos objets.

### Code à compléter

```python
# 1. Créez une classe 'Compte' avec un attribut 'solde'
# Implémentez les méthodes spéciales __str__, __add__, et __sub__
class Compte:
    def __init__(self, solde=0):
        self.solde = solde

    def __str__(self):
        # Retourne une chaîne formatée du solde avec 2 décimales
        # Indice : Utilisez f"Solde: {self.solde:.2f}"
        # Votre code ici
        pass

    def __add__(self, other):
        # Permet d'additionner deux comptes ou un compte et un nombre
        # Indice : Vérifiez le type de 'other' et ajoutez au solde en conséquence
        # Votre code ici
        pass

    def __sub__(self, other):
        # Permet de soustraire deux comptes ou un nombre d'un compte
        # Indice : Similaire à __add__, mais avec une soustraction
        # Votre code ici
        pass

# 2. Créez une classe 'CompteEpargne' qui hérite de 'Compte'
# Ajoutez un attribut 'taux_interet' et une méthode 'appliquer_interet'
class CompteEpargne(Compte):
    def __init__(self, solde=0, taux_interet=0.01):
        # Indice : Utilisez super().__init__() et ajoutez l'attribut taux_interet
        # Votre code ici
        pass

    def appliquer_interet(self):
        # Applique le taux d'intérêt au solde
        # Indice : Augmentez le solde en fonction du taux d'intérêt
        # Votre code ici
        pass

# Ne modifiez pas le code ci-dessous
compte1 = Compte(100)
compte2 = Compte(50)
compte_epargne = CompteEpargne(1000, 0.05)

resultats = {
    "str_compte": str(compte1),
    "addition_comptes": str(compte1 + compte2),
    "soustraction_comptes": str(compte1 - 30),
    "str_compte_epargne": str(compte_epargne),
}

compte_epargne.appliquer_interet()
resultats["compte_epargne_avec_interet"] = str(compte_epargne)
```

### Code de test

```python
def test_exercice_avance(resultats):
    assert resultats["str_compte"] == "Solde: 100.00", "La méthode __str__ de Compte ne fonctionne pas correctement"
    assert resultats["addition_comptes"] == "Solde: 150.00", "La méthode __add__ de Compte ne fonctionne pas correctement"
    assert resultats["soustraction_comptes"] == "Solde: 70.00", "La méthode __sub__ de Compte ne fonctionne pas correctement"
    assert resultats["str_compte_epargne"] == "Solde: 1000.00", "La méthode __str__ de CompteEpargne ne fonctionne pas correctement"
    assert resultats["compte_epargne_avec_interet"] == "Solde: 1050.00", "La méthode appliquer_interet de CompteEpargne ne fonctionne pas correctement"
    print("Félicitations ! Vous avez réussi l'exercice de niveau avancé.")

test_exercice_avance(resultats)
```

## Conclusion

Félicitations ! Vous avez terminé l'exercice sur la Programmation Orientée Objet en Python. Vous avez appris à :
- Créer des classes avec des attributs et des méthodes
- Utiliser l'héritage pour créer des hiérarchies de classes
- Implémenter des méthodes spéciales pour personnaliser le comportement des objets

Ces compétences sont essentielles pour créer des programmes bien structurés et réutilisables en Python. La POO est largement utilisée dans le développement de logiciels complexes et constitue une base importante pour de nombreux frameworks et bibliothèques Python. Continuez à pratiquer ces concepts en les appliquant à vos propres projets !