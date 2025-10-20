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

# Treballant amb strings

- Utilitzar els operadors `+` i `*` amb strings (cadenes de text)
- Com esbrinar la longitud d’un string
- Indexar un string
- Buscar substrings dins d’un string

---

## Operacions amb cadenes

Els strings es poden combinar (o **concatenar**) amb l’operador `+`:

```python
inici = "ex"
final = "emple"
paraula = inici + final
print(paraula) # exemple
```

L’operador `*` també es pot utilitzar amb un string, quan l’altre operand és un enter. En aquest cas, l'string es repeteix tantes vegades com indiqui el número:

```python
paraula = "banana"
print(paraula * 3) # bananabananabanana
```

---

## Exemple: dibuixar una piràmide amb un bucle

Combinant operacions amb cadenes i bucles, podem escriure un programa que dibuixi una piràmide:

<div style="display: flex; gap: 2em;">
<div style="flex: 2;">

```python
n = 10  # nombre de nivells de la piràmide
fila = "*"
while n > 0:
    print(" " * n + fila)
    fila += "**"
    n -= 1
```

<div class="exercici-classe">
String multiplied

</div>

</div>
<div style="flex: 1;">

          *
         ***
        *****
       *******
      *********
     ***********
    *************

</div>
</div>

---

## La longitud d’un string

La funció `len`, _length_ (longitud abreviat), retorna el nombre de caràcters que i ha dins d’un string. El resultat sempre és un nombre enter.

```python
len("hey") # retorna 3, ja que l'string "hey" té tres caràcters.
```

El següent programa demana un string a l’usuari i després el mostra subratllat:

```python
input_string = input("Introdueix un string: ")
print(input_string)
print("-"*len(input_string))
```

---

<div class="exercici-classe">

The longer string

</div>

---

## Índexs i accés als caràcters d’un string

Com que els strings són essencialment seqüències de caràcters, és possible accedir a cadascun d’aquests caràcters individualment.

L’operador `[]` permet accedir a un caràcter concret mitjançant el seu índex (la seva posició dins la cadena). Comencen sempre en 0:

<div style="display: flex; gap: 2em;">
<div style="flex: 1;">

| Caràcter | 1r  | 2n  | 3r  |
| -------- | --- | --- | --- |
| Índex    | 0   | 1   | 2   |
| Gos      | G   | o   | s   |

</div>

<div style="flex: 2;">

```python
input_string = "Gos"
print(input_string[0]) # G
print(input_string[1]) # o
print(input_string[2]) # s
```

</div>
</div>

---

## Recorregut amb un bucle

Podem recórrer tots els caràcters amb un bucle while:

```python
input_string = input("Escriu un string: ")
index = 0

while index < len(input_string):
    print(input_string[index])
    index += 1
```

---

## Primer i últim caràcter

L’últim caràcter té sempre l’índex `len(string) - 1`. Observa l'exemple anterior del gos, per accedir a l'últim caràcter usem l'índex 2.

```python
input_string = input("Escriu un string: ")
print("Primer caràcter: " + input_string[0])
print("Últim caràcter: " + input_string[len(input_string) - 1])
```

---

## Caràcters negatius

També podem accedir als caràcters des del final de la cadena:

`-1` → últim caràcter

`-2` → penúltim caràcter, etc.

Així podem simplificar l’exemple anterior:

```python
input_string = input("Escriu un string: ")
print("Primer caràcter: " + input_string[0])
print("Últim caràcter: " + input_string[-1])
```

---

## Error IndexError: string index out of range

Si has provat els exemples anteriors, potser ja t’ha aparegut el missatge d’error: `IndexError: string index out of range
`

Aquest error apareix quan intentes accedir a una posició (índex) que no existeix dins de la cadena.

```python
input_string = "python"
print("El desè caràcter és: " + input_string[9])
```

---

De vegades cal comprovar si l'string no està buit abans d’accedir als seus caràcters:

```python
input_string = input("Escriu una string: ")

if len(input_string) > 0:
    print("Primer caràcter: " + input_string[0])
else:
    print("L'string està buit. No hi ha cap primer caràcter.")
```

<div class="exercici-classe">
End to beginning

Second and second to last characters

</div>

---

<div class="exercici-classe">
A line of hashes

A rectangle of hashes

Underlining

Right-aligned

A framed word

</div>

---

## Substrings

Una substring (subcadena) d’un string és una seqüència de caràcters que forma part d’aquest string. Per exemple, la cadena "exemple" conté els substrings "exem", "emp" i "ple", entre moltes altres.

**Com seleccionar una subcadena**: Si coneixes els índexs d’inici i final de la part que vols extreure, pots fer-ho amb la notació: `[a:b)`. És a dir, inclou el primer caràcter, però exclou l’últim. Com en els intervals de matemàtiques.

---

```python
input_string = "programacio"

print(input_string[0:3])  # pro
print(input_string[4:9])  # ramac
# Si s’ometeix l’índex inicial, comença a 0
print(input_string[:3])   # pro
# Si s’ometeix l’índex final, arriba fins al final de l’string
print(input_string[4:])   # ramacio

```

<div class="exercici-classe">
Substrings, part 1

Substrings, part 2

</div>

---

## Buscar substrings dins d’un string

L’operador `in` permet comprovar si un string conté un determinat substring. L’expressió booleana `a in b` retorna `True` si l’string `b` conté el substring `a`.

```python
input_string = "test"

print("t" in input_string)   # True
print("x" in input_string)   # False
print("es" in input_string)  # True
print("ets" in input_string) # False
```

---

El programa següent permet a l’usuari cercar substrings dins d’un string fixat al codi:

```python
input_string = "perpendicular"

while True:
    substring = input("Què vols buscar? ")
    if substring in input_string:
        print("Trobat!")
    else:
        print("No s’ha trobat.")
```

---

<div class="exercici-classe">

Does it contain vowels

</div>

---
