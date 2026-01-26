---
marp: true
theme: gaia
_class: lead
paginate: true
title: Sentències condicionals en Python
author: Curs Python 2025
date: 2025-08-26
lang: ca
---

<style>
.exercici {
  position: relative;
  border-radius: 12px;
  background: #fff8e1;
  padding: 1.2em;
  margin: 1em 0;
  box-shadow: 0 4px 8px rgba(0,0,0,0.15);
  border-left: 6px solid #ff9800;
  font-size: 1.1em;
}

.exercici::before {
  content: "Exercici";
  position: absolute;
  top: -10px;
  right: -10px;
  background: #ff9800;   /* verd */
  color: white;
  padding: 0.2em 0.6em;
  border-radius: 12px;
  font-size: 0.85em;
  font-weight: bold;
}


section::after {
  content: attr(data-marpit-pagination) '/' attr(data-marpit-pagination-total);
}

</style>

# Més encara sobre llistes

- Crear llistes amb diferents tipus d'elements
- Utilitzar les llistes per organitzar dades
- Emmagatzemar una matriu com una llista bidimensional

---

## Llistes amb diferents tipus de dades

En Python, una llista pot contenir qualsevol tipus de valor, no només enters.

Llistes de strings

```python
names = ["Marlyn", "Ruth", "Paul"]
names.append("David")

print(len(names))
names.sort()

for name in names:
    print(name)
```

---

Llistes amb floats

```python
mesures = [-2.5, 1.1, 7.5, 14.6, 21.0, 19.2]

for mesura in mesures:
    print(mesura)

mitjana = sum(mesures) / len(mesures)
print("Mitjana:", mitjana)
```

---

## Recordatori: variables globals dins funcions

Una funció pot “veure” variables definides fora (globals), però usar-les és mala pràctica ja que pot causar errors difícils de detectar.

```python
def print_reversed(noms: list):
    i = len(llista_noms) - 1  # NO fa servir el paràmetre "names"
    while i >= 0:
        print(llista_noms[i])
        i -= 1

llista_noms = ["Steve", "Jean", "Katherine", "Paul"]
print_reversed(llista_noms)
print_reversed(["Huey", "Dewey", "Louie"])
```

---

## Warning: overwriting parameters

```python
def number_in_list(numbers: list, number: int):
    for number in numbers:
        if number == number:
            return True
        else:
            return False
```

---

```python
def number_in_list(numbers: list, searched_number: int):
    for number in numbers:
        if number == searched_number:
            return True
        else:
            return False
```

---

```python
def number_in_list(numbers: list, searched_number: int):
    for number in numbers:
        if number == searched_number:
            return True
    return False
```

<div class="exercici">

The longest string

</div>

---

## Llistes dins de llistes

Una llista pot contenir altres llistes com a elements:

```python
my_list = [[5, 2, 3], [4, 1], [2, 2, 5, 1]]
print(my_list)
print(my_list[1]) # [4, 1]
print(my_list[1][0]) # 4
```

**Per què és útil?**
Una llista pot representar un objecte o registre, per exemple, informació d’una persona:

["Anna", 12, 1.45]

---

Una base de dades seria una llista de llistes:

```python
persones = [["Betty", 10, 1.37],["Peter", 7, 1.25],["Alan", 39, 1.78]]

for person in persons:
    name = person[0]
    age = person[1]
    height = person[2]
    print(f"{name}: {age} anys, {height} metres d'alçada")
```

Per representar dades com aquestes, aviat coneixerem els **diccionaris**, que sovint són més clars.

---

## Matrius

Una matriu és una llista 2D: una llista de files, on cada fila és una llista.

<img src="https://programming-24.mooc.fi/static/57e8504bd70c2538405be5b5e1572347/8d139/5_1_1.webp" height="200">

Exemple:

```python
my_matrix = [[1, 2, 3],[3, 2, 1],[4, 5, 6]]
```

---

```python
my_matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

for row in my_matrix:
    print(row)
```

```python
for row in my_matrix:
    print("Una nova fila")
    for element in row:
        print(element)
```

[Visualization tool a python tutor](https://pythontutor.com/visualize.html#)

---

## Accedir a una fila

Seleccionar una fila és directe: només cal l’índex de la fila.

```python
def sum_of_row(my_matrix, row_no: int):
    row = my_matrix[row_no]     # agafem la fila
    row_sum = 0
    for item in row:
        row_sum += item
    return row_sum

m = [[4, 2, 3, 2], [9, 1, 12, 11], [7, 8, 9, 5], [2, 9, 15, 1]]

my_sum = sum_of_row(m, 1)
print(my_sum)   # 33 → 9 + 1 + 12 + 11
```

---

## Accedir a una columna

Com que la matriu està guardada per files, cal recorrer totes les files i agafar l’índex de la columna.

```python
def sum_of_column(my_matrix, column_no: int):
    column_sum = 0
    for row in my_matrix:
        column_sum += row[column_no]
    return column_sum

m = [[4, 2, 3, 2], [9, 1, 12, 11], [7, 8, 9, 5], [2, 9, 15, 1]]

my_sum = sum_of_column(m, 2)
print(my_sum)   # 39 → 3 + 12 + 9 + 15
```

---

<div class="exercici">

Number of matching elements

</div>

## Una matriu bidimensional per fer l'estructura d'un joc

Una matriu (o _array 2D_) és una estructura molt útil per representar taulers de joc.
Molts jocs funcionen sobre una quadrícula → és natural guardar l’estat del joc en files i columnes.

---

## Sudoku

Un sudoku es pot representar amb una matriu de 9×9:

![sudoku](https://programming-24.mooc.fi/static/5a4d938ae5202e8db72b179ff4d76293/0cb6c/5_1_3.webp)

---

```python
sudoku = [
[9, 0, 0, 0, 8, 0, 3, 0, 0],
[0, 0, 0, 2, 5, 0, 7, 0, 0],
[0, 2, 0, 3, 0, 0, 0, 0, 4],
[0, 9, 4, 0, 0, 0, 0, 0, 0],
[0, 0, 0, 7, 3, 0, 5, 6, 0],
[7, 0, 5, 0, 6, 0, 4, 0, 0],
[0, 0, 7, 8, 0, 3, 9, 0, 0],
[0, 0, 1, 0, 0, 0, 0, 0, 3],
[3, 0, 0, 0, 0, 0, 0, 0, 2]
]
```

---

Podem mostrar correctament amb la següent funció:

```python
def print_grid(sudoku):
    for row in sudoku:
        for square in row:
            if square > 0:
                print(f" {square}", end="")
            else:
                print(" _", end="")
        print()

print_grid(sudoku)
```

---

<div class="exercici">

Go

Sudoku: check row

Sudoku: check column

Sudoku: check block

Sudoku: check grid

</div>
