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

# Bucles amb condicions

- Com crear un bucle **while** amb una condició.
- Entendre el paper de la **inicialització**, la **condició** i l’**actualització** dins un bucle.

---

## Recordem...

A la secció anterior vam veure el bucle `while True`,  
on la condició és sempre **certa** i cal fer servir `break` per sortir-ne.

```python
a = 1
while True:
    print(a)
    a += 1
    if a == 5:
        break
```

---

# Condicions dins del while

La condició no ha de ser sempre `True`. Pot ser qualsevol expressió booleana:

```python
while <condició>:
    <bloc de codi>
```

El bucle s’executa mentre la condició sigui certa. Quan deixa de ser-ho, el programa continua després del bucle.

---

```python
num = int(input("Introdueix un número: "))

while num < 10:
  print(num)
  num += 1

print("Execució finalitzada.")
```

Si la condició és falsa des del principi, el bloc del bucle no s’executa mai:

---

# Els tres elements clau d’un bucle

Perquè un bucle funcioni correctament cal:

1️⃣ **Inicialització** – definir el valor inicial de la variable.
2️⃣ **Condició** – determina quan el bucle continuarà.
3️⃣ **Actualització** – modifica la variable perquè el bucle acabi.

```python
num = 1 # Inicialització

while number < 10: # Condició
  print(num)
  num += 1 # Actualització

print("Execució finalitzada.")
```

---

# Escriure condicions en bucles

Qualsevol **expressió booleana** (o combinació d’elles) és vàlida com a condició d’un bucle.

El següent programa imprimeix **cada tercer número**,  
sempre que sigui **menor que 100** i **no divisible per 5**.

```python
num = int(input("Introdueix un número: "))

while num < 100 and num % 5 != 0:
    print(num)
    num += 3
```

---

<div class="exercici-classe">
Print numbers

Fix the code: Countdown

Numbers

</div>

---

# Consells de debugging

Suposa que comences a escriure un programa més complex, com el del proper exercicis (potències de dos). Començaries així:

```python
limit = int(input("Límit superior: "))
num = 1
while num == limit:
    # més codi...
```

Quan programes, no sol funcionar bé al primer intent. Cal provar-lo, corregir-lo i tornar a provar — sovint **moltes** vegades.

---

Però si cada cop cal escriure l'`input` manualment, les proves es fan lentes i pesades.

<mark>**Truc**</mark>: Hard-code per provar

```python
# Durant les proves pots “fixar” el valor d’entrada en lloc de demanar-lo cada cop:
limit = 8 # int(input("Upper limit"))
num = 1
while num == limit:
  # més codi...
```

Així pots provar ràpidament amb diferents valors: 8, 42, 100...

Si el test diu que el teu codi falla amb l’entrada 42, prova amb aquest valor directament i observa què passa.

---

# Debugging amb print

Afegir instruccions `print()` dins del bucle et mostra què està passant en temps real:

Això t’ajuda a veure:

- Quins valors prenen les variables.
- Si la condició canvia com esperes.
- On el bucle pot quedar-se atrapat.

---

# Eina visual: Python Tutor

https://pythontutor.com

És una eina online que et permet:

- Executar el teu codi pas a pas.
- Veure el valor de cada variable a cada línia.
- Seguir el flux d’execució amb una fletxa vermella.

---

<div class="exercici-classe">
Powers of two

Powers of base n

The sum of consecutive numbers, version 1

</div>

---

# Construint strings

Ja des de la primera setmana vam veure que es poden unir textos:

```python
curs = "primer"
curs = curs + " de"
curs = curs + " batxillerat"
print(curs)
```

L’operador `+=` ens permet fer-ho d’una manera més compacta:

```python
curs = "primer"
curs += " de"
curs += " batxillerat"
print(curs)
```

---

# Combinar text i variables amb f-strings

Les _f-strings_ són molt útils quan volem incloure valors dins el text:

```python
curs = "Programació"
nota = 4

veredicte = "Has obtingut "
veredicte += f"la nota de {nota} "
veredicte += f"al curs de {curs}."

print(veredicte)
```

---

En l’exercici anterior vas calcular la suma de nombres consecutius afegint sempre un nou valor dins d’un bucle.
Exactament la mateixa idea s’aplica també a les cadenes de text: pots afegir noves parts a una cadena dins d’un bucle. Aquesta tècnica et serà útil en el proper exercici.

<div class="exercici-classe">
The sum of consecutive numbers, version 2
</div>
