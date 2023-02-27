# TP 3

## Table de 5

```python
i = 0

while i <= 10:
    print(5 * i, end = " ")
    i += 1

    # Rq : à la sortie de la boucle, i = 11
```

## Exercice 1

### V1

```python
seq = input("Saisissez une séquence d'ADN : ")
seq = seq.upper()

i = 0

while i < len(seq):
    print(seq[i])
    i += 1
```

### V2

```python
seq = input("Entrez une séquence d'ADN : ")
seq = seq.upper()

i = 0

while i < len(seq):
    print(seq[i], end=" ")
    i += 1
```


## Exercice 2

```python
seq = input("Saisissez une séqence d'ADN : ")
seq = seq.upper()

i = 0

while i < len(seq) :
    print(seq[i], "est en position", i+1)
    i += 1
```

## Exercice 3
```python
seq_prot = input("Saisissez une séquence protéique : ")
seq_prot = seq_prot.upper()

nb_soufre = 0
i = 0

while i < len(seq_prot):
    if seq_prot[i] == "M" or seq_prot[i] == "C":
        nb_soufre += 1
    i += 1
    # ou alors if seq[i] in "MC"

print("La séquence protéique contient", nb_soufre, "aminé(s) soufré(s).")
```

## Exercice 4 et ajouter une vérification de la séquence

```python
seq = input("Saisissez une séquence d'ADN : ")
seq = seq.upper()

nb_a = 0
nb_t = 0
nb_c = 0
nb_g = 0

compteur_erreur = 0
j = 0

while j < len(seq):
    if seq[j] not in "ATCG":
        compteur_erreur += 1
    j += 1

if compteur_erreur > 0 :
    print("La séquence choisie n'est pas de l'ADN")
else :
    print("La séquence choisie est bien de l'ADN")


i = 0

while i < len(seq):
    if seq[i] == "A":
        nb_a += 1
    elif seq[i] == "T":
        nb_t += 1
    elif seq[i] == "C":
        nb_c += 1
    elif seq[i] == "G":
        nb_g += 1

    i += 1

# Ou alors if nb_autre == 0:
#               print("La séquence est bien de l'ADN") 

print("Le pourcentage en A est de", nb_a / len(seq) * 100, "%")
print("Le pourcentage en T est de", nb_t / len(seq) * 100, "%")
print("Le pourcentage en C est de", nb_c / len(seq) * 100, "%")
print("Le pourcentage en G est de", nb_g / len(seq) * 100, "%")
print("Le pourcentage en autres caractères est de", compteur_erreur / len(seq) * 100, "%")
```

## Exercice 5 : écrire ARN sous forme d'ADN dans bases de données (car même séquence)

**Attention** : la séquence transcrite est synthétisée sur l'autre brin, donc correspond à la même séquence avec les T remplacés par les U.

On peut utiliser sequence.replace("T", "U").

```python
seq = input("Saisissez une séquence d'ADN : ")
seq = seq.upper()

seq_transcrite = ""

i = 0

while i < len(seq):
    if seq[i] == "A":
        seq_transcrite += seq[i]
    elif seq[i] == "T":
        seq_transcrite += "U"
    elif seq[i] == "G":
        seq_transcrite += seq[i]
    else:
        seq_transcrite += seq[i]
    i += 1

print("Le transcrit de la séquence,  est :", seq_transcrite)
```

## Exercice 6

### V1 

On ne prend pas en compte les nucléotides qui ne sont pas dans un codon => ne les affiches pas => problème.

```python
seq = input("Saisissez une séquence d'ADN : ")
seq = seq.upper()

i = 2

while i < len(seq):

    print(seq[i-2:i+1], end = " ")
    i += 3
```

Et ajouter la fin de la séquence.

```python
seq = input("Saisissez une séquence d'ADN : ")
seq = seq.upper()
codons = ""

i = 0

while i < len(seq):
    codons += seq[i:i+3] + " "
    i = i + 3

print(codons)
```

### V2 

Version corrigée mais moins intuitive

```python
seq = input("Saisissez une séquence d'ADN : ")
seq = seq.upper()

i = 0

while i < len(seq):
    if i % 3 == 0 and i != 0:
        print(" "+seq[i], end = "")
    else:
        print(seq[i], end = "")
    i += 1
```