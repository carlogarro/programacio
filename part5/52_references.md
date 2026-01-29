---
marp: true
theme: gaia
_class: lead
paginate: true
title: Encara més sobre llistes
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

# Referències en Python

- Referència a una variable
- Diverses variables poden referenciar el mateix objecte
- Utilitzar llistes com a paràmetres de funcions
- Efecte secundari en una funció

---

## Les variables són referències

En Python, les variables **no emmagatzemen directament el valor**.

Emmagatzemen una **referència** a un objecte en memòria. Tot són objectes. Pots veure on apunta una variable amb la funció `id()`.

```python
a = [1, 2, 3]
print(id(a))

b = "Això també és una referència"
print(id(b))
```

El nombre representa una adreça de memòria.

---

## Tipus immutables i mutables

int, float, bool, str. No es poden modificar, només substituir.

```python
x = 1
print(id(x))
x += 1
print(id(x)) # nou objecte
```

Les llistes són mutables, és a dir, el mateix objecte es modifica.

```python
numbers = [1, 2, 3]
numbers[0] = 10
```

---

## Múltiples referències a la mateixa llista

Assignar una llista no la copia:

```python
a = [1, 2, 3]
b = a

b[0] = 10
print(a)
```

`a` i `b` apunten a la mateixa llista.

---

## Copiar una llista

Còpia manual:

```python
original = [1, 2, 3]
copia = []

for item in original:
    copia.append(item)
```

Còpia amb _slicing_ (recomanat):

```python
original = [1, 2, 3]
copia = original[:]
```

---

## Llistes com a paràmetres de funcions

Quan passes una llista a una funció, passes una referència. La llista original queda modificada.

```python
def afegir_item(la_llista):
    la_llista.append(10)

numbers = [1, 2, 3]
afegir_item(numbers)
```

Una funció té **efectes secundaris** si modifica dades externes.

Per exemple: Modificar una llista passada com a paràmetre o canviar variables globals. Normalment, cal **evitar-los**.

---

<div class="exercici">
Items multiplied by two

Remove the smallest

Sudoku: print out the grid and add a number (llegir _hint_)

Sudoku: add number to a copy of the grid

Tic-Tac-Toe

Transpose a matrix

</div>
