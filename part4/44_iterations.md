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
  display: inline-block;
  max-width: 80%;
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
  content: "Exercicis";
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

# Iteracions definides amb bucle for

- Diferències entre iteracions definides i indefinides

- Utilitzar el bucle for en python

- Utilitzar el bucle for per iterar llistes i strings

---

## Iteració indefinida (while)

No sabem quantes vegades s’executarà. Para quan la condició deixa de complir-se.

```python
my_list = [3, 2, 4, 5, 2]
index = 0
while index < len(my_list):
    print(my_list[index])
    index += 1
```

---

## Iteració definida: El bucle for

Python ofereix una manera més clara i neta. No cal preocupar-se dels índexs.

Estructura:

```python
for variable in col·lecció:
    codi
```

---

### Recorre una llista amb el bucle for:

```python
my_list = [3, 2, 4, 5, 2]
for item in my_list:
    print(item)
```

Python agafa cada element automàticament. El codi és més llegible i segur.

### Recorre un string amb el bucle for

```python
paraula = "hola"
for lletra in paraula:
    print(character)
```

---

**Usa bucle for quan:**

- Ja tens una col·lecció (llista, string, etc.)

- Vols codi més clar i curt

**Usa bucle while quan:**

- No saps quantes iteracions caldran

<div class="exercici">

Star-studded ⭐

</div>

---

## La funció range

`range(final)` -> Rep un sol argument: Crea una "llista" de 0 fins a final-1. El valor final no s’inclou.

```python
for i in range(5):
    print(i)
```

`range(inici, final)` -> Amb dos arguments: Comença a inici i acaba a final - 1

```python
for i in range(3, 7):
    print(i)
```

---

`range(inici, final, pas)` -> Amb tres arguments: El tercer indica de quant en quant

```python
for i in range(1, 9, 2):
    print(i)
```

El pas pot ser negatiu: Serveix per comptar enrere

```python
for i in range(6, 2, -1):
    print(i)
```

---

## Resum ràpid

`range(b)` → de 0 fins b-1

`range(a, b)` → de a fins b-1

`range(a, b, c)` → de a fins b-1 amb pas de c

El final mai s’inclou

<div class="exercici">

From negative to positive ⭐

</div>

---

## De range a list

La funció range no retorna una llista. Retorna un objecte de tipus range. Aquest objecte es pot recórrer amb for, però no es mostra com una llista quan l'imprimeixes.

Si imprimeixes directament un range, veuràs això:

```python
numbers = range(2, 7)
print(numbers)
```

Resultat:
range(2, 7)

---

Python només mostra una descripció, no els valors. Per obtenir tots els valors, fem servir la funció list. Aquesta funció transforma el range en una llista real.

```python
numbers = list(range(2, 7))
    print(numbers)
```

Resultat:
[2, 3, 4, 5, 6]

---

<div class="exercici">

List of stars ⭐
Anagrams ⭐⭐
Palindromes ⭐⭐
The sum of positive numbers ⭐
Even numbers ⭐
The sum of lists ⭐⭐
Distinct numbers ⭐⭐⭐

</div>

---

## Trobar el millor o el pitjor element d’una llista

És una tasca molt habitual en programació. Consisteix a recórrer una llista i quedar-se amb l’element més adequat.

El criteri pot ser:

- el més gran
- el més petit
- el millor segons alguna condició

---

Fem servir una variable auxiliar.

Aquesta variable _recorda_ el millor element trobat fins ara.

Cada nou element es compara amb el millor actual.

**Estructura general**

```python
best = valor_inicial
for item in my_list:
    if item és millor que best:
best = item
```

`best` comença amb un valor inicial. El `for loop` recorre tota la llista. Si trobem un element millor, l’actualitzem.

---

<div class="exercici">

The length of the longest in the list ⭐⭐
The shortest in the list ⭐⭐
All the longest in the list ⭐⭐⭐

</div>
