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

# Bucles (Loops)

- Sabràs què és un **bucle (loop)** en programació
- Podràs fer servir un **bucle `while True`** als teus programes
- Entendràs com utilitzar la instrucció **`break`** per sortir d’un bucle

---

# Què és un bucle?

- Un **bucle** permet repetir una secció de codi diverses vegades.
- Cada repetició s’anomena una **iteració**.
- A diferència dels condicionals, que escullen quina branca executar, els bucles **repeteixen** instruccions.

---

## Exemple bàsic

```python
while True:
    number = int(input("Introdueix un número, -1 per sortir: "))

    if number == -1:
        break

    print(number ** 2)

print("Gràcies i adéu!")
```

🌀 El bucle es repeteix fins que l’usuari introdueix $-1$. Quan això passa, el programa surt del bucle amb `break`.

---

## Bucle infinit ⚠️

Si oblidem actualitzar o comprovar la condició correctament, el bucle pot no acabar mai.

```python
number = int(input("Introdueix un número, -1 per sortir: "))

while True:
    if number == -1:
        break
    print(number ** 2)
```

🧨 Aquest codi repeteix el mateix valor infinitament, ja que number no es demana de nou dins del bucle.

---

# Exemple: comprovació de PIN

```python
while True:
    codi = input("Introdueix el teu PIN: ")
    if codi == "1234":
        break
    print("Incorrecte... torna-ho a provar")

print("PIN correcte!")
```

🧩 El bucle continua fins que s’introdueix el PIN correcte.

---

<div class="exercici-classe">
Shall we continue?

Input validation

Fix the code: Countdown

Repeat password

</div>

---

# Variables auxiliars en bucles

Podem afegir variables que ajudin a controlar o registrar el comportament del bucle.

Anem a fer més realista el codi de la contrassenya.

---

```python
intents = 0
while True:
codi = input("Introdueix el teu PIN: ")
intents += 1
    if codi == "1234":
        correcte = True
        break
    if attempts == 3:
        correcte = False
        break
    print("Incorrecte... torna-ho a provar")
if correcte:
    print("PIN correcte!")
else:
    print("Massa intents...")
```

---

# Debugging en bucles

Els bucles poden causar errors difícils de detectar. És molt útil afegir `print` per veure què passa dins del bucle.

```python
while True:
    print("Inici del bucle")
    codi = input("PIN: ")
    intents += 1
    print("Intents:", intents)
```

Això t’ajuda a entendre en quin punt s’està executant el codi i quines condicions es compleixen.

---

<div class="exercici-classe">
PIN and number of attempts

The next leap year

</div>

---

# Concatenar strings amb l'operador `+`

També pots fer servir variables per guardar informació dins el bucle.

```python
codis = ""
intents = 0

while True:
codi = input("Introdueix el teu PIN: ")
intents += 1
codis += code + ", "
```

Aquí `codis` va acumulant tots els PINs escrits, separats per comes.

Això també és útil per guardar l’historial de dades dins d’un bucle.

---

<div class="exercici-classe">
Story

Working with numbers

</div>
