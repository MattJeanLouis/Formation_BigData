# Exercice : Nettoyage de Données avec Pandas

## Introduction

Le nettoyage de données est une étape cruciale dans tout projet d'analyse de données. Il consiste à traiter les données brutes pour les rendre utilisables pour l'analyse. Pandas offre de nombreux outils puissants pour effectuer ces tâches de nettoyage efficacement.

Définitions :
- Valeurs manquantes : Données absentes ou non renseignées dans un dataset.
- Doublons : Lignes ou entrées identiques répétées dans un dataset.
- DataFrame : Structure de données 2D de Pandas, similaire à une feuille de calcul ou une table SQL.

Dans cet exercice, vous allez apprendre à :
1. Identifier et traiter les valeurs manquantes
2. Supprimer les doublons
3. Renommer les colonnes pour plus de clarté

## Exemple Guidé

Avant de commencer l'exercice, voici un exemple simple de nettoyage de données avec Pandas :

```python
import pandas as pd
import numpy as np

# Créer un DataFrame avec des données "sales"
df = pd.DataFrame({
    'A': [1, 2, np.nan, 4],
    'B': [5, 5, 7, np.nan],
    'C': ['x', 'y', 'z', 'x']
})

print("DataFrame original :")
print(df)

# Supprimer les lignes avec des valeurs manquantes
df_clean = df.dropna()

print("\nAprès suppression des valeurs manquantes :")
print(df_clean)

# Supprimer les doublons
df_unique = df.drop_duplicates()

print("\nAprès suppression des doublons :")
print(df_unique)

# Renommer les colonnes
df_renamed = df.rename(columns={'A': 'Valeur', 'B': 'Quantité', 'C': 'Catégorie'})

print("\nAprès renommage des colonnes :")
print(df_renamed)
```

Cet exemple montre comment effectuer des opérations de base de nettoyage sur un DataFrame Pandas.

## Exercice

### Préparation

Commencez par importer les bibliothèques nécessaires et créer un DataFrame "sale" :

```python
import pandas as pd
import numpy as np

# Créons un DataFrame "sale" pour l'exemple
data = {
    'A': [1, 2, np.nan, 4, 5, 5, np.nan],
    'B': [5, 6, 7, 8, np.nan, 9, 9],
    'C': ['a', 'b', 'c', 'd', 'e', 'e', 'g']
}
df = pd.DataFrame(data)

print("DataFrame original :")
print(df)

# Affichez les informations sur le DataFrame
print(df.info())
```

### Tâches

1. Suppression des lignes avec des valeurs manquantes

Utilisez la méthode appropriée pour supprimer les lignes contenant des valeurs manquantes.

Indice : La méthode `dropna()` peut être utilisée pour cette tâche.

```python
# Votre code ici
df_clean = 

print("DataFrame après suppression des valeurs manquantes :")
print(df_clean)
```

2. Remplacement des valeurs manquantes

Remplacez les valeurs manquantes de la colonne 'A' par la moyenne de cette colonne, et celles de la colonne 'B' par 0.

Indice : Utilisez la méthode `fillna()` avec différentes stratégies pour chaque colonne.

```python
df_filled = df.copy()
# Votre code ici
df_filled['A'] = 
df_filled['B'] = 

print("DataFrame après remplacement des valeurs manquantes :")
print(df_filled)
```

3. Suppression des doublons

Supprimez les lignes dupliquées du DataFrame.

Indice : La méthode `drop_duplicates()` est utile pour cette tâche.

```python
# Votre code ici
df_unique = 

print("DataFrame après suppression des doublons :")
print(df_unique)
```

4. Renommage des colonnes

Renommez les colonnes 'A', 'B', et 'C' en 'Valeur', 'Quantité', et 'Catégorie' respectivement.

Indice : Utilisez la méthode `rename()` avec un dictionnaire pour mapper les anciens noms aux nouveaux.

```python
# Votre code ici
df_renamed = 

print("DataFrame avec les colonnes renommées :")
print(df_renamed)
```

### Tests

Utilisez le code suivant pour tester vos fonctions :

```python
def test_dataframe_original():
    assert df.shape == (7, 3), "Le DataFrame original devrait avoir 7 lignes et 3 colonnes"
    assert df.isna().sum().sum() == 3, "Le DataFrame original devrait avoir 3 valeurs manquantes au total"
    assert df.duplicated().sum() == 1, "Le DataFrame original devrait avoir 1 ligne dupliquée"
    print("Parfait ! Le DataFrame 'sale' a été correctement créé.")

def test_dropna():
    assert df_clean.shape[0] < df.shape[0], "Des lignes auraient dû être supprimées"
    assert df_clean.isna().sum().sum() == 0, "Il ne devrait plus y avoir de valeurs manquantes"
    print("Excellent ! Vous avez correctement supprimé les lignes avec des valeurs manquantes.")

def test_fillna():
    assert df_filled.isna().sum().sum() == 0, "Il ne devrait plus y avoir de valeurs manquantes"
    assert df_filled['A'].iloc[2] == df['A'].mean(), "Les valeurs manquantes de la colonne A devraient être remplacées par la moyenne"
    assert df_filled['B'].iloc[4] == 0, "Les valeurs manquantes de la colonne B devraient être remplacées par 0"
    print("Bravo ! Vous avez correctement remplacé les valeurs manquantes.")

def test_drop_duplicates():
    assert df_unique.shape[0] < df.shape[0], "Des lignes auraient dû être supprimées"
    assert df_unique.duplicated().sum() == 0, "Il ne devrait plus y avoir de doublons"
    print("Parfait ! Vous avez correctement supprimé les doublons.")

def test_rename_columns():
    assert set(df_renamed.columns) == {'Valeur', 'Quantité', 'Catégorie'}, "Les colonnes n'ont pas été correctement renommées"
    print("Excellent ! Vous avez correctement renommé les colonnes.")

# Exécution des tests
test_dataframe_original()
test_dropna()
test_fillna()
test_drop_duplicates()
test_rename_columns()
```

## Conclusion

Félicitations ! Vous avez maintenant appris à effectuer des opérations de base de nettoyage de données avec Pandas, notamment :
- Supprimer ou remplacer les valeurs manquantes
- Éliminer les doublons
- Renommer les colonnes pour plus de clarté

Ces compétences sont essentielles pour préparer vos données avant toute analyse approfondie. N'hésitez pas à explorer davantage les fonctionnalités de Pandas pour le nettoyage et la transformation de données !