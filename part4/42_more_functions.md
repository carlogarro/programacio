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

# Més sobre funcions

- Més sobre arguments i paràmetres d'una funció
- Retornar valors de les funcions i com usar-los al teu codi
- Afegir indicacions del tipus dels paràmetres i dels valors de retorn

---

## Recordatori: què és una funció?

```python
def missatge():
    print("Aquest missatge l’ha mostrat una funció")
```

Crida:

```python
missatge()
```

---

## Paràmetres i arguments

Una funció pot tenir paràmetres:

```python
def saludar(nom):
    print("Hola,", nom)
```

```python
saludar("Emily")
```

- "Emily" → argument
- name → paràmetre

---

## Múltiples paràmetres

```python
def sum(a, b):
    print("La suma és", a + b)

sum(2, 3)
```

<div class="exercici">

Line ⭐

</div>

---

## Cridar una funció dins d'altres funcions

Pots cridar una funció des d'una altra funció.

```python
def saludar(nom):
    print("Hola,", nom)

def saludar_multiples_vegades(nom, vegades):
    while vegades > 0:
        saludar(nom)
        vegades -= 1

saludar_multiples_vegades("Emily", 3)
```

---

<div class="exercici">

A box of hashes ⭐
A square of hashes ⭐
A square ⭐
A triangle ⭐⭐
A shape ⭐⭐
A spruce ⭐⭐⭐

</div>

---

## La instrucció return

Les funcions que definim nosaltres poden **retornar valors** amb la instrucció `return`.

```python
def suma(a, b):
    return a + b
resultat = suma(2, 3)
print("Suma:", resultat)
```

```python
def pregunta_nom():
    nom = input("Com et dius? ")
    return nom
nom = pregunta_nom()
print("Hola,", nom)
```

---

## return finalitza la funció

```python
def mes_petit(a, b):
    if a < b:
        return a
    return b

print(mes_petit(3, 7))
print(mes_petit(5, 2))
```

---

## return sense valor també la finalitza

```python
def saludar(nom):
    if nom == "":
        print("???")
        return
    print("Hola,", nom)

saludar("Emily")
saludar("")
saludar("Mark")
```

---

## Ús de valors retornats

Els valors retornats es poden guardar en variables.

```python
def suma(a, b):
    return a + b

resultat = suma(4, 6)
print("La suma és", resultat)
```

Però no és sempre necessari. El podem usar directament.

```python
print("La suma és", suma(4, 6))
```

---

## Funcions dins funcions amb return

```python
def suma(a, b):
    return a+b

def resta(a, b):
    return a-b

resultat = resta(suma(5, 2), suma(2, 3))
print("El resultat és", resultat)
```

---

## Diferència entre return i print

```python
def max1(a, b):
    if a > b:
        return a
    else:
        return b

def max2(a, b):
    if a > b:
        print(a)
    else:
        print(b)

result = max1(3, 5)
print(result)

max2(7, 2)
```

---

`return`

- Finalitza l’execució de la funció i retorna un valor.
- El valor retornat es pot guardar en una variable, usar-lo en altres expressions o passar-lo com argument a una altra funció.

`print`

- Mostra informació a la pantalla immediatament.
- La funció no retorna cap valor; el que imprimeix no es pot reutilitzar en el programa.

---

<div class="exercici">

The greatest number ⭐

Same characters ⭐

First, second and last words ⭐⭐

</div>

---

## Tipus dels arguments

Quan cridem una funció, els arguments han de tenir el tipus correcte.

Tipus comuns en Python:

| Tipus             | Exemple        |
| ----------------- | -------------- |
| Enter (`int`)     | 23             |
| Decimal (`float`) | -0.45          |
| String (`str`)    | "Peter Python" |
| Booleà (`bool`)   | True           |

---

```python
def print_multiples_vegades(missatge, vegades):
    while vegades > 0:
        print(missatge)
        vegades -= 1

print_multiples_vegades("Hola!", 5)
print_multiples_vegades("Hola!", "Emily")
```

---

## Indicar tipus amb Type Hints

```python
def print_many_times(message: str, times: int):
    while times > 0:
        print(message)
        times -= 1
```

```python
def ask_for_name() -> str:
    name = input("Quin és el teu nom? ")
    return name
```

- Són suggeriments sobre el tipus dels arguments i del valor retornat
- No impedeixen errors si s’envien arguments del tipus incorrecte
- Milloren la llegibilitat i ajuden a entendre millor la funció
