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

# Terminologia de programació

- Diferència entre una **sentència** i una **expressió**.
- Trobar el **tipus de dada** d’una expressió avaluada.
- Utilitzar mètodes de **depuració** per trobar errors al teu codi.

---

# Sentència (_Statement_)

- Una **sentència** executa alguna cosa en un programa.
- Exemples:

```python
print("Hola!")        # sentència de sortida
nombre = 2            # sentència d’assignació
```

Una sentència pot contenir-ne d’altres:

```python
if nom == "Anna":
    print("Hola!")
    nombre = 2
```

---

# Bloc

Un bloc equival a un grup de sentències consecutives amb la mateixa indentació.

```python
if edat > 17:
    print("Ets major d’edat!")
    edat = edat + 1
    print("Ara tens un any més...")
```

En Python els blocs s’expressen amb indentació.

El bloc principal ha de començar a l’extrem esquerre del fitxer.

---

# Expressió

Una expressió és un tros de codi que té un determinat tipus.

|  Expressió   |  Valor  |         Tipus         | Python data type |
| :----------: | :-----: | :-------------------: | :--------------: |
|  2 + 4 + 3   |    9    |        integer        |       int        |
| "abc" + "de" | "abcde" |        string         |       str        |
|    11 / 2    |   5.5   | floating point number |      float       |
|  2 \* 5 > 9  |  True   |     Boolean value     |       bool       |

Les expressions es poden assignar a variables.

---

# Funció

Una funció executa una funcionalitat.

Pot rebre **arguments** (o paràmetres).

```python
print("això és un argument")
```

Algunes funcions retornen un valor:

```python
nom = input("Escriu el teu nom: ")
```

---

# Tipus de dades

Cada valor té un tipus:

```python
nom = "Anna" # str
resultat = 100 # int
```

Es pot consultar amb la funció `type()`:

```python
print(type("Anna")) # <class 'str'>
print(type(100)) # <class 'int'>
```

---

# Sintaxi

Igual que als llenguatges naturals, la sintaxi d'un llenguatge determina com s’ha d’escriure el codi.

En Python, si no es compleixen les regles tindrem `SyntaxError`.

```python
if nom == "Anna"
    print("Hola!")
```

```text
Error:
SyntaxError: invalid syntax
```

---

# Debugar (_Debugging_)

Si la sintaxi és correcta però el programa no funciona bé, hi ha un <span style="color:red">_bug_</span>.
**És una habilitat clau per a qualsevol programador/a.**

Exemple:

```python
x = 10
y = 0
result = x / y

print(f"{x} divided by {y} is {result}")
```

```text
ZeroDivisionError: integer division or modulo by zero on line 3
```

---

**Mètodes útils**:

- Afegir print de depuració per veure valors intermedis.
- Provar el programa amb diferents _input_
- Localitzar la línia del problema al text de l'error.

<div class="exercici-casa">
Fix the syntax

Number of characters

Typecasting

</div>
