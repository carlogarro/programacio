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

# Definint funcions

- Com escriure i cridar les teves pròpies funcions
- Arguments i paràmetres d’una funció
- Definir funcions amb paràmetres propis

---

## Què és una funció?

Ja hem fet servir funcions com `len`, `print` o `input`.
Aquestes són funcions incorporades (_built-in functions_) i sempre estan disponibles.
Però també podem definir les nostres pròpies funcions.

---

## Definir una funció

Abans de poder utilitzar una funció, primer l’hem de definir.
Qualsevol definició comença amb la paraula clau `def`.

Després hi posem el nom de la funció, parèntesis () i dos punts :
A continuació, hi va el cos de la funció, amb el codi indentat (com a if o while).

```python
def missatge():
    print("Aquesta és la meva pròpia funció!")
```

Si executes aquest programa... no passarà res!
El codi dins la funció només s’executa quan la cridem.

---

## Cridar una funció

Per executar una funció, simplement escrivim el seu nom seguit de ():

```python
def message():
    print("Aquesta és la meva pròpia funció!")

message()
```

---

## Cridar una funció diverses vegades

Un cop definida, pots cridar-la tantes vegades com vulguis:

```python
def message():
    print("Aquesta és la meva pròpia funció!")

message()
message()
message()
```

---

# Funcions amb arguments

Moltes funcions reben un o més arguments que afecten el que fan.
Per exemple, les funcions incorporades de Python print i input reben com a _argument_ el text que s’ha de mostrar:

```python
print("Hola!")                          # argument = el string "Hola!"
nom = input("Com et dius? ")            # argument = el text de la pregunta
print(nom)                              # argument = el valor de la variable nom
```

# Arguments vs Paràmetres

A Python (i en programació en general), fem una petita distinció:

Argument → és la dada que passem quan cridem la funció.
Paràmetre → és la variable dins la funció que rep aquest valor.

Tot i que sovint es fan servir com a sinònims, nosaltres intentarem mantenir la diferència clara.
Això t’ajudarà a entendre millor documentació i llibres tècnics més endavant.

---

# Definint una funció amb un paràmetre

Els paràmetres s’especifiquen dins els parèntesis () del nom de la funció.

```python
def saludar(persona):
    print("Hola", persona)

saludar("Emily")
saludar("Anna!")
```

L’argument "Emily" s’assigna al paràmetre persona.
A dins la funció, persona val "Emily" i el print mostra: Hola Emily

---

# Bones pràctiques per posar noms

Els noms de funcions i paràmetres segueixen les mateixes regles que les variables

Han de ser descriptius, escrits en minúscules i amb guions baixos (\_) si calen diverses paraules

<div class="exercici">

Seven Brothers ⭐

The first character ⭐

</div>

---

## Més exemples de funcions amb arguments

Exemple 1: funció amb un número com a paràmetre

```python
def al_quadrat(x):
    print(f"El quadrat del número {x} és {x * x}")

al_quadrat(2)
al_quadrat(5)
```

---

Exemple 2: funció amb una condició dins del cos

```python
def saludar(nom):
    if nom == "Emily":
        print("Hola", nom)
    else:
        print("Ei", nom)

saludar("Emily")
saludar("Mark")
```

---

Exemple 3: funció amb dos arguments

```python
def suma(x, y):
    resultat = x + y
    print(f"La suma dels arguments {x} i {y} és {resultat}")

suma(1, 2)
suma(5, 24)
```

---

## Nota important

Nota important

Els noms dels paràmetres dins la funció no tenen cap relació amb les variables de fora.
Per exemple:

```python
x = 100
y = 30
suma(1, 2) # La suma dels arguments 1 i 2 és 3
suma(x + y, 10) # La suma dels arguments 130 i 10 és 140

```

---

<div class="exercici">

Mean ⭐

Print many times ⭐

A square of hashes ⭐⭐

Chessboard ⭐⭐⭐

A word squared ⭐⭐⭐

</div>
