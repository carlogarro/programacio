---
marp: true
theme: gaia
_class: lead
paginate: true
title: Aleatorietat
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

# Aleatorietat (Randomness)

- Utilitzar funcions del mòdul random
- Generar nombres aleatoris
- Aplicar aleatorietat en programes

---

## El mòdul random

El mòdul **random** forma part de la Python Standard Library.

Serveix per generar números aleatoris, barrejar dades, seleccionar elements a l’atzar...

La funció `randint(a, b)` retorna un enter aleatori entre a i b (**inclosos** a diferència de range).

```python
from random import randint

print("Resultat del dau:", randint(1,6))
```

---

La funció `shuffle()` barreja una estructura de dades.

```python
from random import shuffle

words = ["atlas","banana","carrot"]
shuffle(words)
print(words) # resultat possible ['banana','atlas','carrot']
```

La funció `choice()` selecciona un element aleatori.

```python
from random import choice

words = ["atlas","banana","carrot"]
print(choice(words)) # resultat possible "carrot"
```

---

## Exemple: números de loteria

Suposem una loteria amb números del 1 al 40 on se’n trien 7

```python
from random import randint

for i in range(7):
    print(randint(1,40))
```

Quin problema tenim?

---

```python
from random import randint

weekly_draw = []

while len(weekly_draw) < 7:
    new_number = randint(1,40)
    if new_number not in weekly_draw:
        weekly_draw.append(new_number)

print(weekly_draw)
```

---

```python
from random import shuffle

number_pool = list(range(1,41))
shuffle(number_pool)
weekly_draw = number_pool[0:7]

print(weekly_draw)
```

La funció `sample()` selecciona elements únics.

```python
from random import sample

number_pool = list(range(1,41))
weekly_draw = sample(number_pool,7)

print(weekly_draw)
```

---

<div class="exercici">

Lottery numbers

</div>

---

## D'on venen aquests nombres aleatòris?

Els números aleatoris es generen a partir d’una _seed_ (llavor).

```python
from random import randint, seed

seed(1337)

print(randint(1,100))
```

Això generarà sempre el mateix resultat. Usar la funció seed() pot ser útil per fer proves als nostres programes, reproduir resultats, depurar errors...

---

Els números de random no són realment aleatoris, són **pseudorandom**. Els ordinadors funcionen de manera determinista. Per això utilitzen algoritmes matemàtics.
Quan es necessiten números realment aleatoris es poden utilitzar fonts externes com soroll electrònic, radiació de fons, sensors físics... A https://www.random.org/ podem trobar nombres aleatoris reals.

---

<div class="exercici">

Lottery numbers

Password generator, part 1

Password generator, part 2

Dice roller

Random words

</div>
