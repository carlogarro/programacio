---
marp: true
theme: gaia
_class: lead
paginate: true
title: Tuples
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

# Llegir fitxers

- Saber llegir fitxers amb Python
- Entendre què és un **fitxer de text** i un **fitxer CSV**
- Poder processar dades d’un fitxer

---

## Treballar amb fitxers

Una tasca molt habitual en programació és:

- Llegir dades d’un fitxer
- Processar-les
- Escriure resultats en un altre fitxer

Això permet treballar amb **grans quantitats de dades automàticament**.

---

## Fitxers de text

- està format per **línies de text**
- es pot obrir amb editors com **VS Code**

Exemple de fitxer:

```
Hello there!
This example file contains three lines of text.
This is the last line.
```

---

## Obrir un fitxer

La forma recomanada és usar `with`.

```python
with open("example.txt") as new_file:
    contents = new_file.read()
    print(contents)
```

El fitxer s’obre al principi i es tanca automàticament al final. El mètode `read()` retorna un string amb tot el text del fitxer.

```
"Hello there!\nThis example file contains three lines of text.\nThis is the last line."
```

`\n` indica que hi ha un salt de línia "new line".

---

## Llegir el fitxer línia per línia

Moltes vegades és millor processar el fitxer línia per línia.

Un fitxer de text es pot veure com una llista de línies.

```python
with open("example.txt") as new_file:
    count = 0
    total_length = 0
    for line in new_file:
        line = line.replace("\n", "")
        count += 1
        print("Line", count, line)

        length = len(line)
        total_length += length
```

---

```
Line 1 Hello there!
Line 2 This example file contains three lines of text.
Line 3 This is the last line.
Total length of lines: 81
```

<div class="exercici">

Largest number

</div>

---

## Llegir fitxers CSV

CSV significa **Comma-Separated Values** (valors separats per una coma).

És un **fitxer de text** on les dades estan separades per un símbol.

Els més habituals són:

- `,` (coma)
- `;` (punt i coma)

---

## Per a què s’utilitzen els CSV?

Els CSV s’utilitzen molt per:

- guardar registres de dades
- intercanviar informació entre programes
- importar i exportar dades

Molts programes ho suporten, com per exemple **Microsoft Excel**.

---

## Separar les dades d’una línia

Per separar els camps d’una línia utilitzem el mètode `split()`. Aquest mètode divideix un text segons un separador.

```python
text = "monkey,banana,harpsichord"

words = text.split(",")

for word in words:
    print(word)
```

---

Suposem un fitxer `notes.csv`:

```
Paul;5;4;5;3;4;5;5;4;2;4
Beth;3;4;2;4;4;2;3;1;3;3
Ruth;4;5;5;4;5;5;4;5;4;4
```

```python
with open("grades.csv") as new_file:
    for line in new_file:
        line = line.replace("\n", "")
        parts = line.split(";")

        name = parts[0]
        grades = parts[1:]

        print("Name:", name)
        print("Grades:", grades)
```

---

<div class="exercici">

Fruit market

Matrix

</div>

---

## Llegir el mateix fitxer diverses vegades

De vegades un programa necessita **processar el mateix fitxer més d’una vegada**.

```python
with open("people.csv") as new_file:

    for line in new_file:
        parts = line.split(";")
        print("Name:", parts[0])
    age_of_oldest = -1
    for line in new_file:
        parts = line.split(";")
        age = int(parts[1])
```

---

El segon bucle no s’executa. Quan Python arriba al final del fitxer, el cursor queda al final, ja no hi ha més línies per llegir.

**Solució 1 (poc òptima):**

```python
with open("people.csv") as new_file:
    for line in new_file:
        print(line)

with open("people.csv") as new_file:
    for line in new_file:
        print(line)
```

---

**Solució 2:**

```python
people = []

with open("people.csv") as new_file:
    for line in new_file:
        parts = line.split(";")
        people.append((parts[0], int(parts[1]), parts[2]))
```

I després ja podem usar les dades guardades per fer la tasca que sigui necessària.

---

## Més formes de processar un csv

```python
grades = {}
with open("grades.csv") as new_file:
    for line in new_file:
        line = line.replace("\n", "")
        parts = line.split(";")
        name = parts[0]
        grades[name] = []
        for grade in parts[1:]:
            grades[name].append(int(grade))

print(grades)
```

---

## Eliminar elements innecessaris

El mètode `.strip()` elimina els espais en blanc, salts de línia, etc que hi ha al principi o final d'un string. Podem usar els mètodes `.lstrip()` o `.rstrip()` per eliminar els caràcters de l'esquerra (l de _left_) o de la dreta (r de _right_)

---

## Combinar dades de diversos fitxers

Molts programes treballen amb diversos fitxers alhora. Per exemple el fitxer `employees.csv` i el fitxer `salaries.csv`. Ambdós contenen un identificador comú: PIC (_personal identity code_).

---

```python
names = {}
with open("employees.csv") as new_file:
    for line in new_file:
        parts = line.split(';')
        if parts[0] == "pic":
            continue
        names[parts[0]] = parts[1]

salaries = {}
with open("salaries.csv") as new_file:
    for line in new_file:
        parts = line.split(';')
        if parts[0] == "pic":
            continue
        salaries[parts[0]] = int(parts[1]) +int(parts[2])

print("incomes:")
```

---

```python
for pic, name in names.items():
    if pic in salaries:
        salary = salaries[pic]
        print(f"{name:16} {salary} euros")
    else:
        print(f"{name:16} 0 euros")
```

---

<div class="exercici">

Course grading

Spell checker

Recipe search

City bikes

</div>
