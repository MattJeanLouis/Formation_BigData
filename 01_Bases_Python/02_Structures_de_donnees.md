# Exercice : Structures de Données en Python

## Introduction

Les structures de données sont des moyens d'organiser et de stocker des données en programmation. Python offre plusieurs structures de données intégrées qui sont essentielles pour écrire des programmes efficaces et bien organisés.

Définitions :
- Liste : Séquence ordonnée et modifiable d'éléments.
- Tuple : Séquence ordonnée et immuable d'éléments.
- Dictionnaire : Collection non ordonnée de paires clé-valeur.
- Ensemble : Collection non ordonnée d'éléments uniques.

Dans cet exercice, vous allez apprendre à :
1. Créer et manipuler différentes structures de données
2. Effectuer des opérations courantes sur ces structures
3. Utiliser des compréhensions et des opérations ensemblistes

## Partie 1 : Niveau Facile

### Énoncé

Dans cette première partie, nous allons créer et manipuler des listes, des tuples, des dictionnaires et des ensembles.

### Indices et explications

- Les listes sont créées avec des crochets [] et peuvent être modifiées.
- Les tuples sont créés avec des parenthèses () et ne peuvent pas être modifiés après création.
- Les dictionnaires sont créés avec des accolades {} et contiennent des paires clé: valeur.
- Les ensembles sont créés avec des accolades {} ou la fonction set() et contiennent des éléments uniques.

### Code à compléter

```python
# 1. Créez une liste 'fruits' contenant 5 noms de fruits différents
fruits = # Votre code ici

# 2. Ajoutez un fruit à la fin de la liste
# Indice : Utilisez la méthode append()
# Votre code ici

# 3. Créez un tuple 'coordonnees' contenant deux valeurs : latitude et longitude
coordonnees = # Votre code ici

# 4. Créez un dictionnaire 'personne' avec les clés 'nom', 'age' et 'ville'
personne = # Votre code ici

# 5. Ajoutez une nouvelle clé 'profession' au dictionnaire 'personne'
# Indice : Utilisez la notation personne['profession'] = ...
# Votre code ici

# 6. Créez un ensemble 'couleurs' contenant 4 noms de couleurs
couleurs = # Votre code ici

# 7. Ajoutez une nouvelle couleur à l'ensemble 'couleurs'
# Indice : Utilisez la méthode add()
# Votre code ici

# Ne modifiez pas le code ci-dessous
resultats = {
    "fruits": fruits,
    "coordonnees": coordonnees,
    "personne": personne,
    "couleurs": couleurs
}
```

### Code de test

```python
def test_exercice_facile(resultats):
    assert len(resultats["fruits"]) == 6, "La liste fruits doit contenir 6 éléments"
    assert isinstance(resultats["coordonnees"], tuple) and len(resultats["coordonnees"]) == 2, "coordonnees doit être un tuple de 2 éléments"
    assert set(resultats["personne"].keys()) == {"nom", "age", "ville", "profession"}, "Le dictionnaire personne doit avoir les clés 'nom', 'age', 'ville' et 'profession'"
    assert len(resultats["couleurs"]) == 5, "L'ensemble couleurs doit contenir 5 éléments"
    print("Félicitations ! Vous avez réussi l'exercice de niveau facile.")

test_exercice_facile(resultats)
```

## Partie 2 : Niveau Intermédiaire

### Énoncé

Dans cette partie plus avancée, nous allons effectuer des opérations plus complexes sur les structures de données, y compris des compréhensions et des opérations ensemblistes.

### Indices et explications

- La compréhension de liste permet de créer une nouvelle liste basée sur une liste existante en une seule ligne.
- Les opérations ensemblistes incluent l'union (|), l'intersection (&) et la différence (-).
- La méthode sorted() peut être utilisée pour trier une liste.

### Code à compléter

```python
# 1. Créez une liste 'nombres' contenant les nombres de 1 à 10
# Indice : Utilisez la fonction range()
nombres = # Votre code ici

# 2. Utilisez une compréhension de liste pour créer 'nombres_pairs' contenant les nombres pairs de 'nombres'
# Indice : [x for x in nombres if ...]
nombres_pairs = # Votre code ici

# 3. Créez un dictionnaire 'carre_nombres' où les clés sont les nombres de 1 à 5 et les valeurs sont leurs carrés
# Indice : Utilisez une compréhension de dictionnaire {x: x**2 for x in ...}
carre_nombres = # Votre code ici

# 4. Créez deux ensembles : 'ensemble1' contenant les nombres de 1 à 5, et 'ensemble2' contenant les nombres de 4 à 8
ensemble1 = # Votre code ici
ensemble2 = # Votre code ici

# 5. Calculez l'union de 'ensemble1' et 'ensemble2'
# Indice : Utilisez l'opérateur |
union = # Votre code ici

# 6. Calculez l'intersection de 'ensemble1' et 'ensemble2'
# Indice : Utilisez l'opérateur &
intersection = # Votre code ici

# 7. Calculez la différence entre 'ensemble1' et 'ensemble2'
# Indice : Utilisez l'opérateur -
difference = # Votre code ici

# 8. Créez une liste 'mots' contenant 5 mots de votre choix, puis triez-la par ordre alphabétique
# Indice : Utilisez la fonction sorted()
mots = # Votre code ici

# Ne modifiez pas le code ci-dessous
resultats = {
    "nombres": nombres,
    "nombres_pairs": nombres_pairs,
    "carre_nombres": carre_nombres,
    "ensemble1": ensemble1,
    "ensemble2": ensemble2,
    "union": union,
    "intersection": intersection,
    "difference": difference,
    "mots": mots
}
```

### Code de test

```python
def test_exercice_intermediaire(resultats):
    assert resultats["nombres"] == list(range(1, 11)), "La liste nombres doit contenir les nombres de 1 à 10"
    assert resultats["nombres_pairs"] == [2, 4, 6, 8, 10], "nombres_pairs doit contenir les nombres pairs de 1 à 10"
    assert resultats["carre_nombres"] == {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}, "carre_nombres n'est pas correct"
    assert resultats["ensemble1"] == set(range(1, 6)) and resultats["ensemble2"] == set(range(4, 9)), "ensemble1 ou ensemble2 n'est pas correct"
    assert resultats["union"] == set(range(1, 9)), "L'union n'est pas correcte"
    assert resultats["intersection"] == {4, 5}, "L'intersection n'est pas correcte"
    assert resultats["difference"] == {1, 2, 3}, "La différence n'est pas correcte"
    assert len(resultats["mots"]) == 5 and resultats["mots"] == sorted(resultats["mots"]), "La liste mots doit contenir 5 mots triés par ordre alphabétique"
    print("Félicitations ! Vous avez réussi l'exercice de niveau intermédiaire.")

test_exercice_intermediaire(resultats)
```

## Conclusion

Félicitations ! Vous avez terminé l'exercice sur les structures de données en Python. Vous avez appris à :
- Créer et manipuler des listes, tuples, dictionnaires et ensembles
- Utiliser des compréhensions de liste et de dictionnaire
- Effectuer des opérations ensemblistes
- Trier des listes

Ces compétences sont essentielles pour travailler efficacement avec des données en Python. Elles vous permettront de structurer vos données de manière appropriée et d'effectuer des opérations complexes de manière concise et efficace. Continuez à pratiquer ces concepts pour les maîtriser pleinement !