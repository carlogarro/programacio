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
.exercici-classe, .exercici-casa {
  position: relative;
  border-radius: 12px;
  background: #fff8e1;
  padding: 1.2em;
  margin: 1em 0;
  box-shadow: 0 4px 8px rgba(0,0,0,0.15);
  
  font-size: 1.1em;
}

.exercici-classe{
  border-left: 6px solid #ff9800;
}

.exercici-casa{
  border-left: 6px solid #d23d48;
}

/* Exercici a classe */
.exercici-classe::before {
  content: "Exercici a classe";
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

/* Exercici a casa */
.exercici-casa::before {
  content: "Exercici a casa";
  position: absolute;
  top: -10px;
  right: -10px;
  background: #d23d48;   /* blau */
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

# Combinació de condicions

- Operadors **and**, **or** i **not** en condicions
- _nested conditionals_

---

# Operadors lògics

- **and** → totes les condicions han de ser veritables
- **or** → almenys una condició ha de ser veritable
- **not** → nega una condició

Exemple amb `and`:

```python
number = int(input("Introdueix un número: "))
if number >= 5 and number <= 8:
    print("El número està entre 5 i 8")
```

---

Exemple amb or:

```python
number = int(input("Introdueix un número: "))
if number < 5 or number > 8:
print("El número NO està entre 5 i 8")
```

---

Taula de veritat
| a | b | a and b | a or b |
| ----- | ----- | ------- | ------ |
| False | False | False | False |
| True | False | False | True |
| False | True | False | True |
| True | True | True | True |

Not:
| a | not a |
| ----- | ----- |
| True | False |
| False | True |

---

```python
number = int(input("Introdueix un número: "))
if not (number >= 5 and number <= 8):
print("El número NO està entre 5 i 8")
```

Els operadors lògics també s’anomenen Boolean operators

Notació simplificada

Condició clàssica: x >= a and x <= b

Notació simplificada en Python: a <= x <= b

Funciona igual que la versió llarga

---

# Combinació de condicions

```python
n1 = int(input("Número 1: "))
n2 = int(input("Número 2: "))
n3 = int(input("Número 3: "))
n4 = int(input("Número 4: "))

if n1 > n2 and n1 > n3 and n1 > n4:
greatest = n1
elif n2 > n3 and n2 > n4:
greatest = n2
elif n3 > n4:
greatest = n3
else:
greatest = n4

print(f"{greatest} és el més gran dels números")
```

---

# Nested conditionals

Un `if` pot estar dins d’un altre `if`

```python
number = int(input("Introdueix un número: "))

if number > 0:
if number % 2 == 0:
print("El número és parell")
else:
print("El número és senar")
else:
print("El número és negatiu o zero")
```

Exemple amb sortides

Entrada: 3 → "El número és senar"

Entrada: 18 → "El número és parell"

Entrada: -4 → "El número és negatiu o zero"

Atenció a la indentació

La indentació defineix quines branques pertanyen a cada condició

Errors d’indentació poden canviar totalment el comportament del programa

---

# Alternativa sense nesting

```python
number = int(input("Introdueix un número: "))

if number > 0 and number % 2 == 0:
print("El número és parell")
elif number > 0 and number % 2 != 0:
print("El número és senar")
else:
print("El número és negatiu o zero")
```

Funciona igual que l’exemple amb nesting

Escollir una opció o l’altra depèn de la claredat i de la situació
