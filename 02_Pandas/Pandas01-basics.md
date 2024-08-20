# Cours Interactif : Les Bases de Pandas

## Introduction

Pandas est une bibliothèque Python essentielle pour la manipulation et l'analyse de données. Elle offre des structures de données puissantes et flexibles qui simplifient grandement le travail avec des données structurées.

Définitions :
- Pandas : Bibliothèque Python pour l'analyse et la manipulation de données.
- Series : Structure de données unidimensionnelle dans Pandas, similaire à une colonne dans un tableur.
- DataFrame : Structure de données bidimensionnelle dans Pandas, similaire à une feuille de calcul ou une table SQL.

Dans ce cours, vous allez apprendre à :
1. Créer et manipuler des Series Pandas
2. Construire et explorer des DataFrames
3. Accéder et modifier des données dans un DataFrame
4. Effectuer des opérations de base sur les données

```python
import pandas as pd
import numpy as np

print("Bibliothèques importées avec succès!")
```

## Partie 1 : Création d'une Series Simple

Une Series Pandas est comme une colonne dans un tableur. C'est une série unidimensionnelle de données avec des étiquettes.

### Exemple et Explications

```python
# Création d'une Series à partir d'une liste
fruits = ['pomme', 'banane', 'cerise', 'date']
s = pd.Series(fruits)
print(s)
```

Explication :
- `pd.Series()` crée une Series Pandas.
- Par défaut, Pandas attribue un index numérique commençant par 0.

### Exercice

Créez une Series de nombres de 1 à 5 et affichez-la.

Indice : Vous pouvez utiliser `pd.Series()` avec une liste de nombres ou `np.arange()`.

```python
# Votre code ici :
nombres = 
print(nombres)
```

### Test automatique

```python
def test_series_nombres():
    assert isinstance(nombres, pd.Series), "nombres doit être une Series Pandas"
    assert len(nombres) == 5, "La Series doit contenir 5 éléments"
    assert list(nombres.values) == [1, 2, 3, 4, 5], "La Series doit contenir les nombres de 1 à 5"
    print("Bravo ! Vous avez correctement créé la Series de nombres.")

test_series_nombres()
```

## Partie 2 : Création d'un DataFrame à partir d'un Dictionnaire

Un DataFrame est comme une feuille de calcul avec des lignes et des colonnes. C'est la structure de données principale de Pandas.

### Exemple et Explications

```python
# Création d'un DataFrame à partir d'un dictionnaire
data = {
    'Nom': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'Ville': ['Paris', 'Lyon', 'Marseille']
}
df = pd.DataFrame(data)
print(df)
```

Explication :
- Les clés du dictionnaire deviennent les noms des colonnes.
- Chaque valeur du dictionnaire devient une colonne du DataFrame.

### Exercice

Créez un DataFrame avec des informations sur des livres (titre, auteur, année de publication).

Indice : Structurez vos données sous forme de dictionnaire avec au moins 3 livres.

```python
# Votre code ici :
livres = 
print(livres)
```

### Test automatique

```python
def test_dataframe_livres():
    assert isinstance(livres, pd.DataFrame), "livres doit être un DataFrame Pandas"
    assert len(livres) >= 3, "Le DataFrame doit contenir au moins 3 livres"
    assert set(livres.columns) == {'titre', 'auteur', 'année'}, "Le DataFrame doit avoir les colonnes 'titre', 'auteur', et 'année'"
    print("Excellent ! Vous avez correctement créé le DataFrame des livres.")

test_dataframe_livres()
```

## Partie 3 : Accès aux Données d'un DataFrame

Pandas offre plusieurs méthodes pour sélectionner des données spécifiques dans un DataFrame.

### Exemples et Explications

```python
# Sélectionner une colonne
print(df['Nom'])

# Sélectionner plusieurs colonnes
print(df[['Nom', 'Age']])

# Sélectionner des lignes avec .loc[]
print(df.loc[0])  # Première ligne
```

Explication :
- `df['Nom']` retourne une Series avec la colonne 'Nom'.
- `df[['Nom', 'Age']]` retourne un nouveau DataFrame avec les colonnes sélectionnées.
- `df.loc[0]` sélectionne la première ligne du DataFrame.

### Exercice

À partir du DataFrame 'livres' que vous avez créé, sélectionnez :
1. La colonne des titres
2. Les colonnes des titres et des auteurs
3. La deuxième ligne du DataFrame

```python
# Votre code ici :
titres = 
titres_auteurs = 
deuxieme_livre = 
```

### Test automatique

```python
def test_selection_donnees():
    assert isinstance(titres, pd.Series), "titres doit être une Series Pandas"
    assert isinstance(titres_auteurs, pd.DataFrame), "titres_auteurs doit être un DataFrame Pandas"
    assert isinstance(deuxieme_livre, pd.Series), "deuxieme_livre doit être une Series Pandas"
    assert list(titres_auteurs.columns) == ['titre', 'auteur'], "titres_auteurs doit contenir les colonnes 'titre' et 'auteur'"
    print("Parfait ! Vous avez correctement sélectionné les données du DataFrame.")

test_selection_donnees()
```

## Partie 4 : Opérations de Base sur un DataFrame

Pandas permet d'effectuer facilement des calculs et d'appliquer des fonctions à vos données.

### Exemples et Explications

```python
# Ajouter une nouvelle colonne
df['Année de naissance'] = 2023 - df['Age']

# Appliquer une fonction à une colonne
df['Nom en majuscules'] = df['Nom'].apply(lambda x: x.upper())
```

Explication :
- On peut créer de nouvelles colonnes en effectuant des opérations sur les colonnes existantes.
- La méthode `apply()` permet d'appliquer une fonction à chaque élément d'une colonne.

### Exercice

Pour votre DataFrame 'livres' :
1. Ajoutez une colonne 'Âge du livre' qui calcule l'âge du livre en 2023
2. Créez une colonne 'Longueur du titre' qui contient le nombre de caractères de chaque titre

```python
# Votre code ici :
livres['Âge du livre'] = 
livres['Longueur du titre'] = 
print(livres)
```

### Test automatique

```python
def test_operations_dataframe():
    assert 'Âge du livre' in livres.columns, "La colonne 'Âge du livre' doit être ajoutée au DataFrame"
    assert 'Longueur du titre' in livres.columns, "La colonne 'Longueur du titre' doit être ajoutée au DataFrame"
    assert all(livres['Âge du livre'] == 2023 - livres['année']), "Le calcul de l'âge du livre n'est pas correct"
    assert all(livres['Longueur du titre'] == livres['titre'].str.len()), "Le calcul de la longueur du titre n'est pas correct"
    print("Bravo ! Vous avez correctement effectué les opérations sur le DataFrame.")

test_operations_dataframe()
```

## Conclusion

Félicitations ! Vous avez maintenant une compréhension de base des Series et des DataFrames de Pandas. Vous savez comment les créer, accéder à leurs données et effectuer des opérations simples. Ces compétences sont fondamentales pour l'analyse de données avec Python.

N'hésitez pas à expérimenter davantage avec ces concepts. La pratique est la clé pour maîtriser Pandas et devenir efficace dans l'analyse de données.