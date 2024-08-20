# Exercice : Manipulation de Fichiers en Python

## Introduction

La manipulation de fichiers est une compétence essentielle en programmation Python. Elle permet de lire des données à partir de fichiers, d'écrire des résultats dans des fichiers et de modifier le contenu des fichiers existants.

Définitions :
- Fichier : Un ensemble de données stockées sur un support de stockage.
- Mode d'ouverture : Spécifie comment le fichier doit être ouvert (lecture, écriture, ajout).
- Flux (stream) : Un canal de communication pour les opérations d'entrée/sortie sur les fichiers.

Dans cet exercice, vous allez apprendre à :
1. Lire le contenu de fichiers de différentes manières
2. Écrire et ajouter du contenu dans des fichiers
3. Modifier le contenu des fichiers existants

## Exemple Guidé

Avant de commencer l'exercice, voici un exemple détaillé de manipulation de fichiers :

```python
# Écriture dans un fichier
with open("exemple.txt", "w") as fichier:
    fichier.write("Bonjour, monde!\n")
    fichier.write("Ceci est un exemple de manipulation de fichiers en Python.\n")

# Lecture du fichier entier
with open("exemple.txt", "r") as fichier:
    contenu = fichier.read()
    print("Contenu du fichier:")
    print(contenu)

# Lecture ligne par ligne
with open("exemple.txt", "r") as fichier:
    print("Lecture ligne par ligne:")
    for ligne in fichier:
        print(ligne.strip())  # strip() enlève les espaces et sauts de ligne en début/fin

# Ajout de contenu à la fin du fichier
with open("exemple.txt", "a") as fichier:
    fichier.write("Cette ligne a été ajoutée à la fin.\n")

# Vérification du contenu mis à jour
with open("exemple.txt", "r") as fichier:
    print("Contenu mis à jour:")
    print(fichier.read())
```

Cet exemple montre comment écrire dans un fichier, le lire de différentes manières et ajouter du contenu à la fin.

## Exercice : Opérations sur les Fichiers

### Énoncé

Dans cet exercice, vous allez créer plusieurs fonctions pour manipuler des fichiers de différentes manières.

### Indices et explications

- Utilisez le mot-clé `with` pour ouvrir des fichiers, il gère automatiquement la fermeture du fichier.
- Les modes d'ouverture courants sont "r" (lecture), "w" (écriture, écrase le contenu existant), et "a" (ajout à la fin).
- La méthode `read()` lit tout le contenu du fichier, tandis que `readlines()` retourne une liste de lignes.
- Pour remplacer du texte, vous pouvez utiliser la méthode `replace()` des chaînes de caractères.

### Code à compléter

```python
import os

# Fonction pour créer un fichier de test
def creer_fichier_test(nom_fichier, contenu):
    with open(nom_fichier, "w") as f:
        f.write(contenu)

# Créons un fichier de test
creer_fichier_test("test.txt", "Ligne 1\nLigne 2\nLigne 3\n")

# 1. Écrivez une fonction qui lit le contenu d'un fichier et le retourne sous forme de chaîne
def lire_fichier(nom_fichier):
    # Indice : Utilisez open() avec le mode "r" et la méthode read()
    # Votre code ici
    pass

# 2. Écrivez une fonction qui lit le contenu d'un fichier ligne par ligne et retourne une liste de lignes
def lire_lignes(nom_fichier):
    # Indice : Utilisez open() avec le mode "r" et la méthode readlines()
    # Votre code ici
    pass

# 3. Écrivez une fonction qui écrit une chaîne dans un fichier (en écrasant le contenu existant)
def ecrire_fichier(nom_fichier, contenu):
    # Indice : Utilisez open() avec le mode "w" et la méthode write()
    # Votre code ici
    pass

# 4. Écrivez une fonction qui ajoute une ligne à la fin d'un fichier existant
def ajouter_ligne(nom_fichier, nouvelle_ligne):
    # Indice : Utilisez open() avec le mode "a" et la méthode write()
    # Votre code ici
    pass

# 5. Écrivez une fonction qui lit un fichier, remplace toutes les occurrences d'un mot par un autre, et écrit le résultat dans un nouveau fichier
def remplacer_mot(nom_fichier_entree, nom_fichier_sortie, ancien_mot, nouveau_mot):
    # Indice : Lisez le contenu, utilisez la méthode replace(), puis écrivez dans un nouveau fichier
    # Votre code ici
    pass

# Ne modifiez pas le code ci-dessous
resultats = {
    "contenu_initial": lire_fichier("test.txt"),
    "lignes_initiales": lire_lignes("test.txt")
}

ecrire_fichier("nouveau.txt", "Nouveau contenu\n")
resultats["nouveau_contenu"] = lire_fichier("nouveau.txt")

ajouter_ligne("test.txt", "Ligne 4\n")
resultats["contenu_apres_ajout"] = lire_fichier("test.txt")

remplacer_mot("test.txt", "remplace.txt", "Ligne", "Rangée")
resultats["contenu_remplace"] = lire_fichier("remplace.txt")

# Nettoyage des fichiers créés
for fichier in ["test.txt", "nouveau.txt", "remplace.txt"]:
    if os.path.exists(fichier):
        os.remove(fichier)
```

### Code de test

```python
def test_exercice_fichiers(resultats):
    assert resultats["contenu_initial"] == "Ligne 1\nLigne 2\nLigne 3\n", "La lecture du fichier initial n'est pas correcte"
    assert resultats["lignes_initiales"] == ["Ligne 1\n", "Ligne 2\n", "Ligne 3\n"], "La lecture ligne par ligne n'est pas correcte"
    assert resultats["nouveau_contenu"] == "Nouveau contenu\n", "L'écriture dans un nouveau fichier n'est pas correcte"
    assert resultats["contenu_apres_ajout"] == "Ligne 1\nLigne 2\nLigne 3\nLigne 4\n", "L'ajout d'une ligne n'est pas correct"
    assert resultats["contenu_remplace"] == "Rangée 1\nRangée 2\nRangée 3\nRangée 4\n", "Le remplacement de mot n'est pas correct"
    print("Félicitations ! Vous avez réussi l'exercice sur la manipulation de fichiers.")

test_exercice_fichiers(resultats)
```

## Conclusion

Félicitations ! Vous avez terminé l'exercice sur la manipulation de fichiers en Python. Vous avez appris à :
- Lire le contenu complet d'un fichier
- Lire un fichier ligne par ligne
- Écrire du contenu dans un nouveau fichier
- Ajouter du contenu à la fin d'un fichier existant
- Modifier le contenu d'un fichier en remplaçant des mots

Ces compétences sont essentielles pour travailler avec des données stockées dans des fichiers, que ce soit pour l'analyse de données, la gestion de configurations, ou la création de rapports. La manipulation de fichiers est une opération courante dans de nombreux domaines de la programmation Python, de la science des données à l'automatisation de tâches.

N'oubliez pas de toujours fermer vos fichiers après les avoir utilisés (ou utilisez le mot-clé `with` qui le fait automatiquement) pour éviter les fuites de ressources. Continuez à pratiquer ces opérations dans vos propres projets pour devenir plus à l'aise avec la manipulation de fichiers en Python !