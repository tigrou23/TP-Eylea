# TP 2

## Instruction `input`

### Exercice 1
```python
chaine1 = str(input("Entrez le premier mot : "))
chaine2 = str(input("Entrez le deuxième mot : "))

print("Le premier mot est : " + chaine1 + ". Et il est composé de " + str(len(chaine1)) + " lettres.")
print("Le deuxième mot est : " + chaine2 + ". Et il est composé de " + str(len(chaine2)) + " lettres.")

print("Le deuxième mot apparaît " + str(chaine1.count(chaine2)) + " fois dans le premier mot.")
```

### Exercice 2
```python
longueur = int(input("Entrez la longueur du rectangle : "))
largeur = int(input("Entrez la largeur du rectangle : "))

print("L'air du rectangle est égale à " + str(longueur * largeur) + ".")
```

### Exercice 3
```python
sequence = str(input("Saisissez la séquence nucléotidique : "))

sequence = sequence.upper()

nb_A = sequence.count('A')
nb_T = sequence.count('T')
nb_G = sequence.count('G')
nb_C = sequence.count('C')
nb_erreur = len(sequence) - (nb_A + nb_T + nb_G + nb_C)

pourcentage_A = nb_A*100/len(sequence)
pourcentage_T = nb_T*100/len(sequence)
pourcentage_G = nb_G*100/len(sequence)
pourcentage_C = nb_C*100/len(sequence)
pourcentage_erreur = nb_erreur*100/len(sequence)

print("Le pourcentage en A est de " + str(pourcentage_A) + "%.")
print("Le pourcentage en T est de " + str(pourcentage_T) + "%.")
print("Le pourcentage en G est de " + str(pourcentage_G) + "%.")
print("Le pourcentage en C est de " + str(pourcentage_C) + "%.")
print("Le pourcentage de mauvais caractères est de " + str(pourcentage_erreur) + "%.")
```

## Instruction `if` et blocs d'instructions

### Exercice 4
```python
chaine1 = str(input("Entrez le premier mot : "))
chaine2 = str(input("Entrez le deuxième mot : "))

# V1
if(chaine1.count(chaine2) > 0):
    print("La seconde chaine est contenue dans la première.")

# V2
if(chaine2 in chaine1):
    print("La seconde chaine est contenue dans la première.")
```

### Exercice 5
```python
nombre = int(input("Entrez un nombre : "))

if(nombre % 2 == 0):
    print("Le nombre est pair.")
else : 
    print("Le nombre est impair.")
```

### Exercice 6
```python
nombre = int(input("Entrez un nombre : "))

if(nombre > 0):
    print("Le nombre est positif.")
elif(nombre < 0): 
    print("Le nombre est négatif.")
else:
    print("Le nombre est égal à 0.")
```

### Exercice 7
```python
choix = int(input("Entrez 1 si vous voulez les X premiers caractères du mot ou 2 si vous souhaitez les X derniers caractères du mot : "))
mot = str(input("Entrez un mot : "))
nombre = int(input("Entrez un nombre : "))

if(choix == 1):
    print("Les " + str(nombre) + " premiers caractères sont : '" + mot[0:nombre] + "'.")
elif(choix == 2):
    print("Les " + str(nombre) + " derniers caractères sont : '" + mot[(len(mot))-nombre:len(mot)] + "'.")
else:
    print("Vous n'avez ni choisi 1 ou 2.")
```
