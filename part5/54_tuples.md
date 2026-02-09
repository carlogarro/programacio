---
marp: true
theme: gaia
_class: lead
paginate: true
title: Tuples
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

# Tuples

- Coneixer el tipus de dades **tuple**
- Crear tuples amb diferents valors
- Entendre la diferència entre **tuple** i **llista**
- Coneixer usos típics dels tuples

---

## Què és un tuple?

Un **tuple** és una estructura de dades semblant a una llista, però amb dues diferències clau:

- Les tuples s’escriuen amb **parèntesis ()**
- Les tuples són **immutables** (no es poden modificar)

```python
point = (10, 20)
```

---

## Accedir als elements d’una tupla

Els elements s’accedeixen per índex, igual que en una llista:

```python
point = (10, 20)
print("x coordinate:", point[0])
print("y coordinate:", point[1])
```

Els valors d’una tupla no es poden canviar:

```python
point = (10, 20)
point[0] = 15 # Error
```

---

<div class="exercici">

Create a tuple

The oldest person

Older people

</div>

---

## Per a què serveixen les tuples?

- El conjunt de valors és fix
- Els valors estan relacionats

Exemple típic: coordenades d’un punt. Un punt en 2D sempre té dos elements; una `x` i una `y`.

El tamany d'una llista pot canviar (és mutable), així que no tindria sentit usar-la en casos com aquest.

---

## Tuples com a claus de diccionari

Com que les tuples són immutables, es poden usar com a claus d'un diccionari:

```python
points = {}
points[(3, 5)] = "dog"
points[(5, 0)] = "cat"
points[(1, 2)] = "fish"

print(points[(3, 5)])
```

---

## Tuples sense parèntesis

Els parèntesis no són obligatoris:

```python
numbers = (1, 2, 3)
numbers = 1, 2, 3
```

Ambdós creen exactament la mateixa tupla. Podem usar una tupla per retornar múltiples valors d'una funció.

```python
def minmax(my_list):
    return min(my_list), max(my_list)

my_list = [33, 5, 21, 7, 88, 312, 5]
min_value, max_value = minmax(my_list)
```

---

Si recordes el mètode items() dels diccionaris.

```python
for key, value in my_dictionary.items():
    print(key, value)
```

El mètode items() retorna tuples (key, value).

---

## Més utilitats

Intercanviar valors amb tuples

```python
number1, number2 = number2, number1
```

Equivalent a:

```python
helper = number1
number1 = number2
number2 = helper
```

Però molt més net

---

<div class="exercici">

Student database

A square of letters

</div>
