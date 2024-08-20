# Projet Compact : Analyse d'un Dataset de Films avec Pandas

## Introduction

Ce projet vous guidera à travers l'analyse d'un dataset de films en utilisant Pandas. Vous allez importer, nettoyer, explorer et visualiser les données.

## Préparation

Importez les bibliothèques nécessaires :

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px
import plotly.graph_objects as go
from plotly.subplots import make_subplots

print("Bibliothèques importées avec succès !")
```

## 1. Import et Nettoyage des Données

Importez le dataset et nettoyez-le :

```python
# Importer le dataset
url = "https://raw.githubusercontent.com/danielgrijalva/movie-stats/master/movies.csv"
df = pd.read_csv(url)

# Nettoyer les données
df_clean = df.dropna()
df_clean['year'] = df_clean['year'].astype(int)
df_clean['rating'] = df_clean['rating'].astype(float)

# Test du nettoyage
assert df_clean.isnull().sum().sum() == 0, "Il reste des valeurs manquantes"
assert df_clean['year'].dtype == 'int64', "La colonne 'year' n'est pas de type int"
assert df_clean['rating'].dtype == 'float64', "La colonne 'rating' n'est pas de type float"
print("Données nettoyées avec succès !")

print(df_clean.head())
print(df_clean.info())
```

## 2. Exploration et Visualisation

Créez des visualisations pour explorer les données :

```python
# Distribution des notes
plt.figure(figsize=(10, 6))
plt.hist(df_clean['rating'], bins=20, edgecolor='black')
plt.title('Distribution des Notes de Films')
plt.xlabel('Note')
plt.ylabel('Nombre de Films')
plt.show()

# Relation année vs note
plt.figure(figsize=(12, 6))
plt.scatter(df_clean['year'], df_clean['rating'], alpha=0.5)
plt.title('Relation entre l\'Année de Sortie et la Note du Film')
plt.xlabel('Année')
plt.ylabel('Note')
plt.show()

correlation = df_clean['year'].corr(df_clean['rating'])
print(f"Corrélation entre l'année et la note : {correlation:.2f}")

# Défi : Créez un boxplot pour comparer les notes des films par genre
# Indice : Vous devrez peut-être traiter la colonne 'genre' si elle contient plusieurs genres par film
# Votre code ici :
```

## 3. Analyse des Genres par Décennie

Analysez l'évolution des genres au fil du temps :

```python
# Fonction pour attribuer une décennie
def get_decade(year):
    return (year // 10) * 10

df_clean['decade'] = df_clean['year'].apply(get_decade)

# Comptez le nombre de films par genre et par décennie
# Votre code ici :
genre_by_decade = 

# Affichez les 5 genres les plus populaires pour chaque décennie
for decade in sorted(genre_by_decade.index.unique()):
    print(f"\nTop 5 des genres pour la décennie {decade} :")
    print(genre_by_decade.loc[decade].nlargest(5))

# Défi : Créez un graphique à barres empilées montrant l'évolution des genres
# Votre code ici :
```

## 4. Dashboard avec Plotly

Créez un dashboard simple pour visualiser vos résultats :

```python
fig = make_subplots(rows=2, cols=2, subplot_titles=('Distribution des Notes', 'Notes vs Année', 'Top 5 Genres', 'Évolution des Genres par Décennie'))

# Distribution des notes
fig.add_trace(go.Histogram(x=df_clean['rating'], nbinsx=20, name='Notes'), row=1, col=1)

# Notes vs Année
fig.add_trace(go.Scatter(x=df_clean['year'], y=df_clean['rating'], mode='markers', name='Films'), row=1, col=2)

# Top 5 Genres
top_genres = df_clean['genre'].value_counts().nlargest(5)
fig.add_trace(go.Bar(x=top_genres.index, y=top_genres.values, name='Genres'), row=2, col=1)

# Évolution des genres par décennie
top_5_genres = df_clean['genre'].value_counts().nlargest(5).index
genre_evolution = df_clean[df_clean['genre'].isin(top_5_genres)].groupby(['decade', 'genre']).size().unstack()
for genre in top_5_genres:
    fig.add_trace(go.Scatter(x=genre_evolution.index, y=genre_evolution[genre], name=genre, mode='lines+markers'), row=2, col=2)

fig.update_layout(height=800, width=1200, title_text="Dashboard d'Analyse des Films")
fig.show()
```

## Conclusion et Défis Supplémentaires

Vous avez réalisé une analyse complète du dataset de films. Pour aller plus loin, essayez ces défis :

1. Analysez la relation entre la durée du film et sa note.
2. Identifiez les réalisateurs les plus prolifiques et leurs notes moyennes.
3. Créez une fonction pour recommander des films basés sur les préférences de l'utilisateur.