# Exercice : Analyse Avancée de Données avec Pandas

## Introduction

L'analyse avancée de données avec Pandas implique l'utilisation de techniques plus sophistiquées pour extraire des insights significatifs à partir de grands ensembles de données. Cela inclut le filtrage complexe, le tri, le groupement, et la création de tables pivots.

Définitions :
- Filtrage : Sélection d'un sous-ensemble de données basé sur des conditions spécifiques.
- Groupement : Regroupement de données basé sur une ou plusieurs colonnes pour effectuer des calculs agrégés.
- Table pivot : Tableau récapitulatif qui réorganise et résume les données selon différentes dimensions.

Dans cet exercice, vous allez apprendre à :
1. Charger et explorer un dataset de ventes
2. Filtrer les données selon des critères spécifiques
3. Trier les données pour identifier les meilleures ventes
4. Grouper les données et calculer des statistiques
5. Créer et visualiser une table pivot

## Exemple Guidé

Avant de commencer l'exercice, voici un exemple simple d'analyse avec Pandas :

```python
import pandas as pd
import matplotlib.pyplot as plt

# Créer un DataFrame d'exemple
data = {
    'Produit': ['A', 'B', 'A', 'C', 'B', 'C'],
    'Ventes': [100, 200, 150, 300, 250, 350],
    'Region': ['Nord', 'Sud', 'Nord', 'Sud', 'Nord', 'Sud']
}
df = pd.DataFrame(data)

# Filtrage
df_filtered = df[df['Ventes'] > 200]

# Tri
df_sorted = df.sort_values('Ventes', ascending=False)

# Groupement
df_grouped = df.groupby('Produit')['Ventes'].sum().sort_values(ascending=False)

# Table pivot
pivot = pd.pivot_table(df, values='Ventes', index='Produit', columns='Region', aggfunc='sum')

# Visualisation
pivot.plot(kind='bar', stacked=True)
plt.title('Ventes par Produit et Région')
plt.show()
```

Cet exemple montre comment effectuer des opérations de base d'analyse sur un DataFrame Pandas.

## Exercice

### Préparation

Commencez par importer les bibliothèques nécessaires et charger le dataset :

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Chargement du dataset
url = "https://raw.githubusercontent.com/datasciencedojo/datasets/master/supermarket_sales.csv"
df = pd.read_csv(url)

print(df.head())
print("\nInformations sur le DataFrame :")
df.info()
```

### Tâches

1. Filtrage des données

Filtrez le DataFrame pour ne garder que les ventes de la catégorie 'Fashion accessories' avec un montant total supérieur à 50.

Indice : Utilisez les opérateurs de comparaison et la méthode `loc[]` ou une condition booléenne.

```python
# Votre code ici
df_filtered = 

print("Données filtrées :")
print(df_filtered.head())
print(f"Nombre de lignes après filtrage : {len(df_filtered)}")
```

2. Tri des données

Triez le DataFrame par montant total de vente (colonne 'Total') en ordre décroissant et affichez les 10 meilleures ventes.

Indice : Utilisez la méthode `sort_values()` avec l'argument `ascending=False`.

```python
# Votre code ici
top_sales = 

print("Top 10 des ventes :")
print(top_sales)
```

3. Groupement et calcul de statistiques

Groupez les données par 'Product line', calculez la moyenne du 'Total' et la somme de la 'Quantity', puis triez les résultats par moyenne de 'Total' décroissante.

Indice : Utilisez `groupby()` suivi de `agg()` avec un dictionnaire pour spécifier différentes opérations par colonne.

```python
# Votre code ici
grouped_stats = 

print("Statistiques par catégorie de produits :")
print(grouped_stats)
```

4. Création d'une table pivot

Créez une table pivot avec 'Product line' en index, 'Gender' en colonnes, et la moyenne de 'Total' comme valeurs.

Indice : Utilisez `pivot_table()` avec les arguments appropriés.

```python
# Votre code ici
pivot_table = 

print("Table pivot des ventes moyennes par catégorie et genre :")
print(pivot_table)

# Visualisation de la table pivot
pivot_table.plot(kind='bar', stacked=True, figsize=(12, 6))
plt.title('Ventes moyennes par catégorie de produits et genre')
plt.xlabel('Catégorie de produits')
plt.ylabel('Vente moyenne')
plt.legend(title='Genre')
plt.tight_layout()
plt.show()
```

### Tests

Utilisez le code suivant pour tester vos fonctions :

```python
def test_dataset_loading():
    assert isinstance(df, pd.DataFrame), "df devrait être un DataFrame pandas"
    assert df.shape[0] > 100, "Le dataset devrait avoir plus de 100 lignes"
    assert 'Product line' in df.columns, "Le DataFrame devrait avoir une colonne 'Product line'"
    assert 'Total' in df.columns, "Le DataFrame devrait avoir une colonne 'Total'"
    print("Parfait ! Le dataset a été correctement chargé.")

def test_data_filtering():
    assert len(df_filtered) < len(df), "Le filtrage devrait réduire le nombre de lignes"
    assert df_filtered['Product line'].unique() == ['Fashion accessories'], "Le DataFrame filtré ne devrait contenir que 'Fashion accessories'"
    assert df_filtered['Total'].min() > 50, "Toutes les ventes devraient avoir un montant supérieur à 50"
    print("Excellent ! Vous avez correctement filtré les données.")

def test_data_sorting():
    assert len(top_sales) == 10, "Vous devriez afficher les 10 meilleures ventes"
    assert top_sales['Total'].is_monotonic_decreasing, "Les ventes devraient être triées par ordre décroissant"
    print("Bravo ! Vous avez correctement trié les données.")

def test_grouping_and_stats():
    assert isinstance(grouped_stats, pd.DataFrame), "Le résultat devrait être un DataFrame"
    assert set(grouped_stats.columns) == {'Total', 'Quantity'}, "Les colonnes devraient être 'Total' et 'Quantity'"
    assert grouped_stats.index.name == 'Product line', "L'index devrait être 'Product line'"
    assert grouped_stats['Total'].is_monotonic_decreasing, "Les résultats devraient être triés par 'Total' décroissant"
    print("Parfait ! Vous avez correctement groupé les données et calculé les statistiques.")

def test_pivot_table():
    assert isinstance(pivot_table, pd.DataFrame), "Le résultat devrait être un DataFrame"
    assert pivot_table.index.name == 'Product line', "L'index devrait être 'Product line'"
    assert set(pivot_table.columns) == {'Female', 'Male'}, "Les colonnes devraient être 'Female' et 'Male'"
    print("Excellent ! Vous avez correctement créé la table pivot.")

# Exécution des tests
test_dataset_loading()
test_data_filtering()
test_data_sorting()
test_grouping_and_stats()
test_pivot_table()
```

## Conclusion

Félicitations ! Vous avez maintenant appliqué des techniques avancées d'analyse de données avec Pandas, notamment :
- Le filtrage de données selon des conditions spécifiques
- Le tri des données pour identifier les meilleures ventes
- Le groupement de données et le calcul de statistiques par groupe
- La création et la visualisation d'une table pivot

Ces compétences sont essentielles pour extraire des insights significatifs de vos données et prendre des décisions basées sur les données. Continuez à pratiquer ces techniques sur différents ensembles de données pour améliorer votre maîtrise de l'analyse de données avec Pandas !