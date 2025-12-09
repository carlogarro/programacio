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

# Format del print

- Utilitzar argument de la funció print per donar format.

- Utilitzar f-strings

---

## Us bàsic del print

### Concatenació amb +

```python
print("Hola " + nom + " tens " + str(edat) + " anys")
```

- Uneix textos amb +
- Tot ha de ser string
- Cal convertir números amb str()

---

### Múltiples arguments al print

```python
print("Hola", nom, "tens", edat, "anys")
```

Cada part va separada per comes

`print` afegeix espais automàticament

---

### Separador (sep)

```python
print("Hola", nom, edat, sep=" - ")
```

`sep` indica què posa entre els elements

Pot ser qualsevol text ("", " - ", "\n", etc.)

### Final de línia (end)

```python
print("Hola", end=" ")
print("què tal?")
```

Per defecte print acaba amb un salt de línia. end permet canviar aquest comportament

---

## f-strings (recomanat)

```python
print(f"Hola {nom}, tens {edat} anys")
```

Forma moderna i clara. No cal convertir tipus.Molt llegible.

**Formats amb f-strings**

```python
print(f"El resultat és {num:.2f}")
```

.2f → 2 decimals

---

**Alineació de text**

```python
print(f"{nom:15} | {nom:>15}")
```

Més info: https://www.w3schools.com/python/python_string_formatting.asp

`:` defineix el format `>` alinea a la dreta

<div class="exercici">

Integers to strings ⭐⭐

</div>
