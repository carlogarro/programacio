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

# Llistes

- Què és una llista
- Accedir a un element d'una llista
- Afegir i eliminar elements d'una llista
- Aprendre _built-in functions_ de les llistes

---

## Definició de llista

Una llista és una **col·lecció de valors** guardada dins una sola variable.

- Els elements es posen entre **claudàtors** `[]`.
- Cada element s’anomena **ítem** o **element**.

```python
buida = []
numeros = [7, 2, 2, 5, 2]
```

---

## Accedir als diferents elements d'una llista

Igual que els strings, les llistes s’indexen des de 0.

- Últim índex: `llista[len(llista) - 1]` o `llista[-1]`

```python
nums = [7, 2, 2, 5, 2]

print(nums[0])  # 7
print(nums[1])  # 2
print(nums[3])  # 5
```

---

## Modificar elements d'una llista

A diferència dels strings (immutables) les llistes són mutables, és a dir, podem modificar els seus elements.

```python
nums = [7, 2, 2, 5, 2]
nums[1] = 3 # Ara nums és [7, 3, 2, 5, 2]
```

<div class="exercici">

Change the value of an item ⭐

</div>

---

## Afegir elements a una llista

En Python, podem afegir elements al final d’una llista amb el mètode `append()`.

```python
numbers = []
numbers.append(5)
numbers.append(10)
numbers.append(3)
print(numbers) # numbers serà [5, 10, 3]
```

<div class="exercici">

Add items to a list ⭐

</div>

---

## Afegir elements en una posició específica

Per afegir un element en una posició específica, fem servir el mètode `insert()`:

```python
numbers = [1, 2, 3, 4, 5, 6]
numbers.insert(0, 10) # [10, 1, 2, 3, 4, 5, 6]
numbers.insert(2, 20) # [10, 1, 20, 2, 3, 4, 5, 6]
```

Tots els elements a partir d’aquell índex es desplacen una posició a la dreta.

---

## Eliminar elements

Hi ha dues maneres principals:

1️⃣ Eliminar per índex → `.pop()`

Elimina l’element d’aquell índex.

2️⃣ Eliminar per valor → `.remove()`

Elimina la primera ocurrència del valor. Si hi ha més d’una, només treu la primera. Similar al mètode `.find()`.

---

```python
my_list = [4, 2, 7, 2, 5]
my_list.pop(2) # [4, 2, 2, 5]

```

```python
my_list = [1, 2, 3, 4, 5, 6]

my_list.remove(2) # [1, 3, 4, 5, 6]
my_list.remove(5) # [1, 3, 4, 6]
```

---

## L'operador in

Igual que amb els strings, podem usar l'operador `in` per comprovar la preséncia d'un element en una llista.

```python
my_list = [1, 3, 4]

if 1 in my_list:
    print("La llista conté l'element 1")

if 2 in my_list:
    print("La llista conté l'element 2")
```

---

<div class="exercici">

Addition and removal ⭐

Same word twice ⭐

</div>

---

## Ordenar llistes

1️⃣ Ordena la llista original, modificant-la _in place_ → Mètode `.sort()`

```python
my_list = [2, 5, 1, 2, 4]
my_list.sort()
print(my_list)
```

2️⃣ Crea una nova llista ordenada sense modificar l’original → Funció `sorted()`

```python
my_list = [2, 5, 1, 2, 4]
print(sorted(my_list))
```

---

<div class="exercici">

List twice ⭐

</div>

---

## Màxim, mínim i suma

Python té funcions molt útils per treballar amb llistes:

- `max(llista)` → retorna el valor més gran
- `min(llista)` → retorna el valor més petit
- `sum(llista)` → retorna la suma de tots els elements

---

```python
my_list = [5, 2, 3, 1, 4]

greatest = max(my_list)
smallest = min(my_list)
list_sum = sum(my_list)

print("Greatest:", greatest) # Greatest: 5
print("Smallest:", smallest) # Smallest: 1
print("Sum:", list_sum) # Sum: 15
```

---

## Mètodes vs Funcions

Hi ha dues maneres diferents de processar llistes en Python, cosa que pot resultar confús. En la majoria dels casos utilitzaràs mètodes de llista, com ara `append` i `sort`. S'utilitzen amb l'operador de punt (.) sobre la variable de la llista:

Algunes funcions accepten una llista com a argument. Més amunt hem vist que les funcions `max`, `min`, `len` i `sorted` fan justament això.

**Les funcions treballen amb dades externes, en canvi els mètodes treballen sobre l’objecte mateix.**

---

## Funcions pròpies on els arguments són llistes

```python
def mediana(numeros: list):
    numeros_ordenats = sorted(numeros)
    centre = len(numeros_ordenats) // 2
    return numeros_ordenats[centre]
```

```python
talla_sabata = [45, 44, 36, 39, 40]
print("La mediana és", mediana(talla_sabata))

edats = [1, 56, 34, 22, 5, 77, 5]
print("La mediana és", mediana(edats))
```

---

## Funcions pròpies que retornen llistes

```python
def introduir_numeros():
    numeros = []
    while True:
        entrada_usuari = input("Introdueix un enter (buit per acabar): ")
        if entrada_usuari == "":
            break
        numeros.append(int(entrada_usuari))
    return numeros
```

---

## Per què és millor usar funcions?

- El codi queda més clar
- És més fàcil de provar cada part
- Pots reutilitzar funcionalitats

```python
print("Talla de sabates:")
talla_sabates = introduir_numeros()

print("Pesos:")
pesos = introduir_numeros()

print("Alçades:")
alçades = introduir_numeros()
```

---

<div class="exercici">

The length of a list ⭐

Arithmetic mean ⭐

The range of a list ⭐⭐

</div>
