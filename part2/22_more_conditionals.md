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

# Més sobre condicionals

- Crear múltiples branques dins d’instruccions condicionals
- Ús de **if**, **elif** i **else**
- Fer servir l’operador **mòdul (%)** en expressions booleanes

---

# Condicional bàsic

Exemple senzill:

```python
number = int(input("Introdueix un número: "))

if number < 0:
    print("El número és negatiu")

if number >= 0:
    print("El número és positiu o zero")
```

Aquí només hauria d’executar-se una de les opcions.

---

# if - else

Amb `else` simplifiquem:

```python
number = int(input("Introdueix un número: "))

if number < 0:
    print("El número és negatiu")
else:
    print("El número és positiu o zero")
```

➡️ Sempre s’executa únicament una branca.

---

# L'operador mòdul (%) i els nombres parells

L’operador `%` retorna el residu de la divisió. Ens serveix per comprovar si un número és parell:

```python
number = int(input("Introdueix un número: "))

if number % 2 == 0:
    print("El número és parell")
else:
    print("El número és senar")
```

---

# Comparació de cadenes

Recordeu per comparar strings, els hem de posar entre cometes, sinó el que indiquem és una variable.

```python
correcta = "gatet"
contrasenya = input("Escriu la contrasenya: ")

if contrasenya == correcta:
    print("Benvingut/da")
else:
    print("Accés denegat")
```

---

<div class="exercici-classe">
Age of maturity
</div>

---

# if - elif - else

Quan hi ha més de dues opcions:

```python
gols_casa = int(input("Gols de l’equip de casa: "))
gols_fora = int(input("Gols de l’equip de fora: "))

if gols_casa > gols_fora:
    print("Ha guanyat l’equip de casa!")
elif gols_fora > gols_casa:
    print("Ha guanyat l’equip de fora!")
else:
    print("Empat!")
```

---

# Diverses branques

Es poden posar tants `elif` com calgui:

```python
print("Calendari de festius")
data = input("Quina data és avui? ")

if data == "26 Des":
print("És Sant Esteve")
elif data == "31 Des":
print("És Cap d’Any (Hogmanay)")
elif data == "1 Gen":
print("És Any Nou")

print("Gràcies i adéu.")
```

---

# Observacions

No cal que hi hagi sempre un `else`

Si cap condició no es compleix → no s’executa cap branca

<div class="exercici-classe">
Greater than or equal to

The elder

Alphabetically last

</div>
```
