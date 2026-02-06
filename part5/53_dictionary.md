---
marp: true
theme: gaia
_class: lead
paginate: true
title: Encara més sobre llistes
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

# Diccionaris

- Estructura de dades **diccionari**
- Utilitzar diccionaris amb diferents tipus de claus i valors
- Recórrer el contingut d’un diccionari
- Usos típics dels diccionaris

---

## Per què no només llistes?

Les llistes tenen una limitació important:

- Els elements s’accedeixen per **índex** (0, 1, 2…)
- Cal saber la posició o recórrer tota la llista

Per a moltes situacions, això no és pràctic.

---

# Què és un diccionari?

Un **diccionari** és una estructura de dades basada en:

- **claus (keys)**
- **valors (values)**

Cada clau apunta a un valor.

---

## Crear un diccionari

```python
my_dictionary = {}

my_dictionary["gos"] = "dog"
my_dictionary["gat"] = "cat"
my_dictionary["peix"] = "fish"
```

## Accedir a les dades

```python
print(len(my_dictionary)) # 3
print(my_dictionary) # {'gos': 'dog', 'gat...}
print(my_dictionary["gos"]) # dog
```

---

## Diccionaris i entrada d’usuari

```python
word = input("Introdueix una paraula: ")
if word in my_dictionary:
  print("Traducció:", my_dictionary[word])
else:
  print("Paraula no trobada")
```

L’operador `in` comprova si la clau existeix.

---

## Què es pot guardar en un diccionari?

Claus: normalment immutables (str, int, tuple)
Valors: qualsevol tipus

```python
results = {}
results["Mary"] = 4
results["Alice"] = 5
results["Larry"] = 2
```

```python
lists = {}
lists[5] = [1, 2, 3]
lists[42] = [5, 4, 5, 4, 5]
lists[100] = [5, 2, 3]
```

---

## Claus úniques

Cada clau només pot aparèixer una vegada.

```python
my_dictionary["salutacio"] = "hola"
my_dictionary["salutacio"] = "hey"

print(my_dictionary["salutacio"]) #hey
```

El valor anterior es reemplaça. **IMPORTANT**: Les claus no poden ser mutables.

**Si vols accedir a dades pel seu nom i no per posició, utilitza un diccionari**

---

<div class="exercici">
Times ten

Factorials

</div>

---

## Recórrer un diccionari

Un diccionari també es pot recórrer amb un bucle `for`. El diccionari ens dona una clau cada vegada, i el valor s’obté amb `my_dictionary[key]`.

```python
my_dictionary = {}

my_dictionary["gos"] = "dog"
my_dictionary["gat"] = "cat"
my_dictionary["peix"] = "fish"

for key in my_dictionary:
    print("clau:", key)
    print("valor:", my_dictionary[key])
```

---

A vegades podem necessitar accedir a clau i valors alhora. Podem usar el mètode `items()`.

```python
for key, value in my_dictionary.items():
    print("key:", key)
    print("value:", value)
```

<div class="exercici">
Histogram

Phone book, version 1

Phone book, version 2

</div>

---

## Eliminar claus i valors d'un diccionari
