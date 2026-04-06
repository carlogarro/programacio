---
marp: true
theme: gaia
_class: lead
paginate: true
title: Mòduls
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

# Mòduls

- Saber què és un module de Python
- Com incloure un mòdul amb `import`
- Com buscar més informació del contingut d'un mòdul

---

## Utilitzar mòduls

Python ja inclou algunes funcions útils, com:

- `len()` → longitud d’una llista o text
- `sum()` → suma d’una col·lecció

Però això no és suficient per a tots els casos, per això existeix la **Python Standard Library**.

La standard library és una col·lecció de funcions, classes i altres eines útils. Aquestes eines estan organitzades en **mòduls**, on cada mòdul agrupa funcionalitats relacionades.

---

# Importar un mòdul

Per utilitzar un mòdul fem servir:

```python
import math

print(math.sqrt(5)) # square root, arrel quadrada
print(math.log(8, 2)) # logaritme en base dos
```

També podem importar només algunes funcions.

```python
from math import sqrt, log

print(sqrt(5))
print(log(5,2))
```

---

<div class="exercici">

Hypotenuse

</div>

---

## Documentació dels mòduls

Cada mòdul té documentació oficial. Per exemple, el mòdul math: https://docs.python.org/3/library/math.html

Podem veure què conté un mòdul amb:

```python
import math

print(dir(math))
# ['acos', 'asin', 'atan', 'ceil', 'cos', 'exp', 'factorial', 'floor', ...]
```

---

<div class="exercici">

Special characters

Fractions

</div>
