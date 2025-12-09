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
