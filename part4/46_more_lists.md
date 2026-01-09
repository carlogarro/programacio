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

# Més sobre llistes i strings

- Més mètodes per tallar llistes i strings
- Immutabilitat d'un string
- Mètodes `count` i `replace`

---

Podem agafar una part d’un string o d’una llista amb la sintaxi:

`text[inici:final]`

Exemple amb string:

```python
s = "exemple"
print(s[3:6]) # mpl
```

Exemple amb llista:

```python
nums = [3,4,2,4,6,1,2,4,2]
print(nums[3:7]) # [4,6,1,2]
```

---

## Més formes de tallar (fer un _slice_)

Igual que amb range, podem afegir un pas:

```python
print("exemple"[0:6:2]) # eep
print([1,2,3,4,5,6,7,8][6:2:-1]) # [7,6,5,4]
```

Si ometem inici o final, Python assumeix fins al principi o fins al final:

```python
text = "exemple"
print(text[:4]) # exem
print(text[4:]) # ple
```

---

Invertir un string (truc curt)

```python
text = "exemplary"
print(text[::-1]) # yralpmexe
```

Això usa `step = -1` → recorre la llista de darrere cap endavant.

<div class="exercici">

Everything reversed ⭐

</div>

---

## Immutabilitat dels strings

Tot i que els strings i les llistes semblen similars, hi ha una diferència important: Els strings no es poden modificar després de crear-se.

Exemple d’error:

```python
s = "exemple"
s[0] = "a" # `TypeError: 'str' object does not support item assignment`
```

```python
nums = [1,2,3]
nums[0] = 10 # nums → [10,2,3]
```

---

Però pots reassignar la variable a un string nou:

```python
s = "Hey"
s = s + "!" # s → "Hey!"
```

Aquí no hem canviat el string original: hem creat un de nou i la variable ara apunta al nou. L'string original es troba en algun lloc de la memòria "perdut", no hi ha referència cap a ell i no pot tornar a ser utilitzar en el programa.

---

## Més mètodes per llistes i strings

El mètode `count` compta quantes vegades apareix un element en una llista o un substring en un string:

```python
s = "Tres tristes tigres"
print(s.count("tr")) # → 2

nums = [1,2,3,1,4,5,1,6]
print(nums.count(1)) # → 3
```

Detall: no compta coincidències superposades
Ex: en "aaaa" → "aa" fa 2, no 3.

---

El mètode `replace` crea un nou string on substitueix **totes** les coincidències d’un substring:

```python
msg = "Hola com estàs?"
print(msg.replace("Hola", "Hey")) # → "Hey com estàs?"
```

Els strings són immutables, per tant replace no modifica l'original:

```python
text = "Python és divertit"
text.replace("Python", "Java")
print(text) # → "Python és divertit"
```

Cal guardar el resultat si el volem fer servir més endavant:

```python
text = text.replace("Python", "Java")
print(text) # → "Java és divertit
```

---

<div class="exercici">

Most common character

No vowels allowed

No shouting allowed

Neighbours in a list

</div>
