# Exercice : Manipulation de Fichiers CSV en Python

## Introduction

Les fichiers CSV (Comma-Separated Values) sont largement utilisés pour stocker des données tabulaires. Python offre des outils puissants pour manipuler ces fichiers, notamment à travers le module `csv`.

Définitions :
- CSV : Format de fichier texte où les valeurs sont séparées par des virgules (ou d'autres délimiteurs).
- En-tête : Première ligne d'un fichier CSV qui contient généralement les noms des colonnes.
- Délimiteur : Caractère utilisé pour séparer les valeurs dans un fichier CSV (souvent une virgule).

Dans cet exercice, vous allez apprendre à :
1. Créer et écrire dans des fichiers CSV
2. Lire des fichiers CSV de différentes manières
3. Manipuler et filtrer des données CSV

## Exemple Guidé

Avant de commencer l'exercice, voici un exemple simple de manipulation de fichier CSV :

```python
import csv

# Écriture dans un fichier CSV
with open('exemple.csv', 'w', newline='') as file:
    writer = csv.writer(file)
    writer.writerow(['Nom', 'Age'])
    writer.writerow(['Alice', 30])
    writer.writerow(['Bob', 25])

# Lecture d'un fichier CSV
with open('exemple.csv', 'r') as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)
```

Cet exemple montre comment écrire des données dans un fichier CSV et les lire ensuite.

## Exercice

### Préparation

Commencez par importer les modules nécessaires :

```python
import csv
import os
```

### Tâches

1. Création d'un fichier CSV de test

Créez une fonction `creer_csv_test(nom_fichier, donnees)` qui écrit les données fournies dans un fichier CSV.

Indice : Utilisez `csv.writer()` et sa méthode `writerows()`.

```python
def creer_csv_test(nom_fichier, donnees):
    # Votre code ici
    pass

# Utilisez ces données de test
donnees_test = [
    ['Nom', 'Age', 'Ville'],
    ['Alice', '30', 'Paris'],
    ['Bob', '25', 'Lyon'],
    ['Charlie', '35', 'Marseille']
]
creer_csv_test('test.csv', donnees_test)
```

2. Lecture d'un fichier CSV en liste de listes

Créez une fonction `lire_csv(nom_fichier)` qui lit un fichier CSV et retourne son contenu sous forme de liste de listes.

Indice : Utilisez `csv.reader()` et convertissez le résultat en liste.

```python
def lire_csv(nom_fichier):
    # Votre code ici
    pass
```

3. Lecture d'un fichier CSV en liste de dictionnaires

Créez une fonction `lire_csv_dict(nom_fichier)` qui lit un fichier CSV et retourne son contenu sous forme de liste de dictionnaires.

Indice : Utilisez `csv.DictReader()`.

```python
def lire_csv_dict(nom_fichier):
    # Votre code ici
    pass
```

4. Écriture dans un fichier CSV

Créez une fonction `ecrire_csv(nom_fichier, donnees)` qui écrit une liste de listes dans un fichier CSV.

Indice : Similaire à `creer_csv_test`, mais assurez-vous de gérer le cas où le fichier existe déjà.

```python
def ecrire_csv(nom_fichier, donnees):
    # Votre code ici
    pass
```

5. Ajout d'une ligne à un fichier CSV existant

Créez une fonction `ajouter_ligne_csv(nom_fichier, nouvelle_ligne)` qui ajoute une ligne à la fin d'un fichier CSV existant.

Indice : Ouvrez le fichier en mode 'a' (append) et utilisez `csv.writer().writerow()`.

```python
def ajouter_ligne_csv(nom_fichier, nouvelle_ligne):
    # Votre code ici
    pass
```

6. Filtrage d'un fichier CSV

Créez une fonction `filtrer_csv(nom_fichier_entree, nom_fichier_sortie, fonction_filtre)` qui lit un fichier CSV, filtre les lignes selon un critère, et écrit le résultat dans un nouveau fichier CSV.

Indice : Utilisez `csv.DictReader()` pour lire, appliquez la fonction de filtre, puis utilisez `csv.DictWriter()` pour écrire les lignes filtrées.

```python
def filtrer_csv(nom_fichier_entree, nom_fichier_sortie, fonction_filtre):
    # Votre code ici
    pass
```

### Test

Utilisez le code suivant pour tester vos fonctions :

```python
resultats = {
    "contenu_initial": lire_csv('test.csv'),
    "contenu_dict": lire_csv_dict('test.csv')
}

nouvelles_donnees = [
    ['Nom', 'Age', 'Ville'],
    ['David', '40', 'Lille'],
    ['Eve', '28', 'Bordeaux']
]
ecrire_csv('nouveau.csv', nouvelles_donnees)
resultats["nouveau_contenu"] = lire_csv('nouveau.csv')

ajouter_ligne_csv('test.csv', ['Frank', '45', 'Nice'])
resultats["contenu_apres_ajout"] = lire_csv('test.csv')

filtrer_csv('test.csv', 'filtre.csv', lambda x: int(x['Age']) > 30)
resultats["contenu_filtre"] = lire_csv('filtre.csv')

# Fonction de test (fournie)
def test_exercice_csv(resultats):
    assert resultats["contenu_initial"] == donnees_test, "La lecture du fichier CSV initial n'est pas correcte"
    assert resultats["contenu_dict"][0] == {'Nom': 'Alice', 'Age': '30', 'Ville': 'Paris'}, "La lecture du fichier CSV en tant que dictionnaire n'est pas correcte"
    assert resultats["nouveau_contenu"] == nouvelles_donnees, "L'écriture dans un nouveau fichier CSV n'est pas correcte"
    assert resultats["contenu_apres_ajout"][-1] == ['Frank', '45', 'Nice'], "L'ajout d'une ligne au fichier CSV n'est pas correct"
    assert len(resultats["contenu_filtre"]) == 3 and resultats["contenu_filtre"][1][1] > '30', "Le filtrage du fichier CSV n'est pas correct"
    print("Félicitations ! Vous avez réussi l'exercice sur la manipulation de fichiers CSV.")

# Exécution du test
test_exercice_csv(resultats)

# Nettoyage des fichiers créés
for fichier in ['test.csv', 'nouveau.csv', 'filtre.csv']:
    if os.path.exists(fichier):
        os.remove(fichier)
```

## Conclusion

Cet exercice vous a permis de pratiquer les opérations fondamentales sur les fichiers CSV en Python. Ces compétences sont essentielles pour le traitement et l'analyse de données dans de nombreux domaines. N'hésitez pas à expérimenter davantage avec différents types de données et des opérations plus complexes !