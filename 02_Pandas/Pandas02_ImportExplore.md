# Exercice : Importation et Exploration de Données avec Pandas

## Introduction

Pandas est une bibliothèque Python puissante pour l'analyse et la manipulation de données. Dans cet exercice, nous allons apprendre à importer des données à partir d'un fichier CSV, à explorer ces données avec différentes méthodes Pandas, et à créer un graphique simple pour visualiser une tendance.

Définitions :
- DataFrame : Structure de données 2D de Pandas, similaire à une feuille de calcul ou une table SQL.
- CSV : Format de fichier "Comma-Separated Values", couramment utilisé pour stocker des données tabulaires.
- Série temporelle : Séquence de points de données indexés par ordre chronologique.

Dans cet exercice, vous allez apprendre à :
1. Importer des données à partir d'un fichier CSV
2. Explorer les données avec les méthodes Pandas
3. Visualiser les données avec Matplotlib

## Exemple Guidé

Avant de commencer l'exercice, voici un exemple détaillé d'importation et d'exploration de données avec Pandas :

```python
import pandas as pd
import matplotlib.pyplot as plt

# Importation de données
df = pd.read_csv('exemple.csv')

# Affichage des premières lignes
print(df.head())

# Informations sur le DataFrame
print(df.info())

# Statistiques descriptives
print(df.describe())

# Création d'un graphique simple
df.plot(x='date', y='valeur')
plt.title('Évolution de la valeur dans le temps')
plt.xlabel('Date')
plt.ylabel('Valeur')
plt.show()
```

Cet exemple montre comment importer un fichier CSV, explorer ses données et créer un graphique simple.

## Exercice : Importation et Exploration de Données Météorologiques

### Énoncé

Dans cet exercice, vous allez travailler avec un fichier CSV contenant des données météorologiques. Vous importerez ces données, les explorerez et créerez un graphique pour visualiser la température au fil du temps.

### Indices et explications

- Utilisez `pd.read_csv()` pour importer le fichier CSV.
- Les méthodes `.info()` et `.describe()` sont utiles pour obtenir un aperçu rapide des données.
- La méthode `.plot()` de Pandas utilise Matplotlib en arrière-plan pour créer des graphiques.

### Code à compléter

```python
import pandas as pd
import matplotlib.pyplot as plt

print("Bibliothèques importées avec succès !")

# 1. Importation d'un fichier CSV
# Indice : Utilisez pd.read_csv() avec le nom du fichier 'weather_data.csv'
df = # Votre code ici

# Affichez les 5 premières lignes du DataFrame
print(df.head())

# 2. Exploration des données
# Affichez les informations sur le DataFrame
# Indice : Utilisez la méthode .info()
# Votre code ici

# Affichez les statistiques descriptives du DataFrame
# Indice : Utilisez la méthode .describe()
# Votre code ici

# 3. Visualisation de la forme du DataFrame et des noms de colonnes
# Affichez la forme du DataFrame
# Indice : Utilisez l'attribut .shape
# Votre code ici

# Affichez les noms des colonnes
# Indice : Utilisez l'attribut .columns
# Votre code ici

# 4. Création d'un graphique simple
# Convertissez la colonne 'date' en datetime si ce n'est pas déjà fait
df['date'] = pd.to_datetime(df['date'])

# Créez un graphique de l'évolution de la température
# Indice : Utilisez df.plot() avec les arguments x='date' et y='temperature'
# Votre code ici

# Ajoutez un titre et des labels aux axes
# Indice : Utilisez plt.title(), plt.xlabel() et plt.ylabel()
# Votre code ici

# Affichez le graphique
plt.show()
```

### Code de test

```python
# Tests automatiques

def test_import_csv():
    assert isinstance(df, pd.DataFrame), "df doit être un DataFrame pandas"
    assert len(df) > 0, "Le DataFrame ne doit pas être vide"
    assert set(df.columns) == {'date', 'temperature', 'humidity', 'pressure'}, "Les colonnes du DataFrame ne sont pas correctes"
    print("Parfait ! Vous avez correctement importé le fichier CSV.")

def test_exploration():
    assert df.shape[1] == 4, "Le DataFrame devrait avoir 4 colonnes"
    assert df.dtypes['date'] == 'object', "La colonne 'date' devrait être de type 'object'"
    assert df.dtypes['temperature'] == 'float64', "La colonne 'temperature' devrait être de type 'float64'"
    print("Bien joué ! Vous avez correctement exploré les données.")

def test_shape_and_columns():
    assert df.shape[0] > 20, "Le DataFrame devrait avoir plus de 20 lignes"
    assert list(df.columns) == ['date', 'temperature', 'humidity', 'pressure'], "Les noms des colonnes ne sont pas corrects"
    print("Excellent ! Vous avez correctement identifié la forme et les colonnes du DataFrame.")

def test_plot():
    fig = plt.gcf()
    assert len(fig.axes) > 0, "Aucun graphique n'a été créé"
    ax = fig.axes[0]
    assert ax.get_xlabel() != "", "L'axe x devrait avoir un label"
    assert ax.get_ylabel() != "", "L'axe y devrait avoir un label"
    assert ax.get_title() != "", "Le graphique devrait avoir un titre"
    print("Bravo ! Vous avez créé un graphique correct.")

# Exécution des tests
test_import_csv()
test_exploration()
test_shape_and_columns()
test_plot()
```

## Conclusion

Félicitations ! Vous avez terminé l'exercice sur l'importation et l'exploration de données avec Pandas. Vous avez appris à :
- Importer des données à partir d'un fichier CSV
- Explorer un DataFrame en utilisant diverses méthodes Pandas
- Visualiser des données temporelles avec un graphique simple

Ces compétences sont essentielles pour l'analyse de données avec Python et Pandas. Elles vous permettront de travailler efficacement avec des ensembles de données réels et de tirer des insights à partir de vos données.

N'hésitez pas à explorer davantage le DataFrame et à créer d'autres visualisations pour mieux comprendre les données. La pratique est la clé pour maîtriser ces concepts !