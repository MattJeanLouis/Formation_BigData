# Exercice : Fonctions en Python

## Introduction

Les fonctions sont des blocs de code réutilisables qui effectuent une tâche spécifique. Elles sont essentielles pour organiser et structurer votre code, le rendant plus lisible, maintenable et efficace.

Définitions :
- Fonction : Bloc de code nommé qui effectue une tâche spécifique et peut être appelé plusieurs fois.
- Paramètre : Variable utilisée dans la définition d'une fonction pour recevoir des valeurs.
- Argument : Valeur passée à une fonction lors de son appel.
- Valeur de retour : Résultat renvoyé par une fonction après son exécution.

Dans cet exercice, vous allez apprendre à :
1. Créer et utiliser des fonctions simples avec des paramètres
2. Travailler avec des paramètres par défaut et des fonctions lambda
3. Utiliser des fonctions plus avancées avec des arguments variables et des décorateurs

## Partie 1 : Niveau Facile

### Énoncé

Dans cette première partie, nous allons créer des fonctions simples avec des paramètres et des valeurs de retour.

### Indices et explications

- Les fonctions sont définies avec le mot-clé `def`, suivi du nom de la fonction et de ses paramètres entre parenthèses.
- Les paramètres par défaut sont spécifiés dans la définition de la fonction avec une valeur assignée.
- Les fonctions lambda sont des fonctions anonymes courtes, définies avec le mot-clé `lambda`.

### Code à compléter

```python
# 1. Créez une fonction 'saluer' qui prend un nom en paramètre et un paramètre optionnel 'salutation' avec une valeur par défaut de "Bonjour"
# La fonction doit retourner une chaîne de caractères au format "[salutation], [nom]!"
def saluer(nom, salutation="Bonjour"):
    # Indice : Utilisez une f-string pour formater la sortie
    # Votre code ici
    pass

# 2. Créez une fonction 'calculer' qui prend deux nombres et une opération ('+', '-', '*', '/') en paramètres
# La fonction doit retourner le résultat de l'opération sur les deux nombres
def calculer(a, b, operation):
    # Indice : Utilisez un dictionnaire pour associer les opérations aux fonctions correspondantes
    # Votre code ici
    pass

# 3. Créez une fonction lambda 'carre' qui prend un nombre en paramètre et retourne son carré
# Indice : La syntaxe d'une fonction lambda est : lambda paramètres: expression
carre = # Votre code ici

# Ne modifiez pas le code ci-dessous
resultats = {
    "saluer_default": saluer("Alice"),
    "saluer_personnalise": saluer("Bob", "Salut"),
    "calculer_addition": calculer(5, 3, '+'),
    "calculer_multiplication": calculer(4, 7, '*'),
    "carre_5": carre(5)
}
```

### Code de test

```python
def test_exercice_facile(resultats):
    assert resultats["saluer_default"] == "Bonjour, Alice!", "La fonction saluer ne fonctionne pas correctement avec la salutation par défaut"
    assert resultats["saluer_personnalise"] == "Salut, Bob!", "La fonction saluer ne fonctionne pas correctement avec une salutation personnalisée"
    assert resultats["calculer_addition"] == 8, "La fonction calculer ne fonctionne pas correctement pour l'addition"
    assert resultats["calculer_multiplication"] == 28, "La fonction calculer ne fonctionne pas correctement pour la multiplication"
    assert resultats["carre_5"] == 25, "La fonction lambda carre ne fonctionne pas correctement"
    print("Félicitations ! Vous avez réussi l'exercice de niveau facile.")

test_exercice_facile(resultats)
```

## Partie 2 : Niveau Intermédiaire

### Énoncé

Dans cette partie plus avancée, nous allons travailler avec des fonctions plus complexes, y compris des fonctions avec des arguments variables, des décorateurs et des fonctions de haut niveau.

### Indices et explications

- `*args` permet à une fonction d'accepter un nombre variable d'arguments positionnels.
- `**kwargs` permet à une fonction d'accepter un nombre variable d'arguments nommés.
- Un décorateur est une fonction qui modifie le comportement d'une autre fonction sans changer son code.
- Une fonction de haut niveau est une fonction qui prend une ou plusieurs fonctions comme arguments ou qui renvoie une fonction.

### Code à compléter

```python
# 1. Créez une fonction 'moyenne' qui peut prendre un nombre variable d'arguments et retourne leur moyenne
def moyenne(*args):
    # Indice : Utilisez sum() pour calculer la somme et len() pour le nombre d'arguments
    # Votre code ici
    pass

# 2. Créez une fonction 'info_personne' qui prend un nombre variable d'arguments nommés et les affiche sous forme de paires clé-valeur
def info_personne(**kwargs):
    # Indice : Parcourez les items de kwargs avec une boucle for
    # Votre code ici
    pass

# 3. Créez un décorateur 'timer' qui mesure le temps d'exécution d'une fonction
import time

def timer(func):
    def wrapper(*args, **kwargs):
        # Indice : Utilisez time.time() pour mesurer le temps avant et après l'exécution de la fonction
        # Votre code ici
        pass
    return wrapper

# 4. Utilisez le décorateur 'timer' sur une fonction 'attendre' qui attend 2 secondes
@timer
def attendre():
    time.sleep(2)

# 5. Créez une fonction 'appliquer' qui prend une fonction et une liste en paramètres, et applique la fonction à chaque élément de la liste
def appliquer(func, liste):
    # Indice : Utilisez une compréhension de liste ou la fonction map()
    # Votre code ici
    pass

# Ne modifiez pas le code ci-dessous
resultats = {
    "moyenne_3_nombres": moyenne(4, 7, 10),
    "moyenne_5_nombres": moyenne(1, 2, 3, 4, 5),
    "info_personne": info_personne(nom="Alice", age=30, ville="Paris"),
    "temps_attente": attendre(),
    "appliquer_carre": appliquer(lambda x: x**2, [1, 2, 3, 4, 5])
}
```

### Code de test

```python
def test_exercice_intermediaire(resultats):
    assert abs(resultats["moyenne_3_nombres"] - 7) < 0.01, "La fonction moyenne ne fonctionne pas correctement pour 3 nombres"
    assert abs(resultats["moyenne_5_nombres"] - 3) < 0.01, "La fonction moyenne ne fonctionne pas correctement pour 5 nombres"
    assert resultats["info_personne"] == None, "La fonction info_personne devrait retourner None"
    assert 1.9 < resultats["temps_attente"] < 2.1, "Le décorateur timer ne mesure pas correctement le temps d'exécution"
    assert resultats["appliquer_carre"] == [1, 4, 9, 16, 25], "La fonction appliquer ne fonctionne pas correctement"
    print("Félicitations ! Vous avez réussi l'exercice de niveau intermédiaire.")

test_exercice_intermediaire(resultats)
```

## Conclusion

Félicitations ! Vous avez terminé l'exercice sur les fonctions en Python. Vous avez appris à :
- Créer des fonctions simples avec des paramètres et des valeurs de retour
- Utiliser des paramètres par défaut et des fonctions lambda
- Travailler avec des arguments variables (*args et **kwargs)
- Créer et utiliser des décorateurs
- Implémenter des fonctions de haut niveau

Ces compétences sont essentielles pour écrire du code Python propre, modulaire et réutilisable. Continuez à pratiquer en créant vos propres fonctions pour résoudre divers problèmes !