---
marp: true
theme: gaia
_class: lead
paginate: true
title: Events
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

# Events amb Pygame

- Entendre els events de pygame
- Detectar teclat
- Detectar ratolí
- Fer programes interactius

---

## Què és un event?

<div style="display: flex; gap: 30px;">

<div style="flex: 1;">

Un event és una acció de l’usuari:

- moure el ratolí
- fer clic
- prémer una tecla
- tancar la finestra

</div>

<div style="flex: 2;">

```python
import pygame

pygame.init()
window = pygame.display.set_mode((640, 480))

while True:
    for event in pygame.event.get():
        print(event)

        if event.type == pygame.QUIT:
            exit()
```

Mostra tots els events en pantalla.

</div>

</div>

---

## Exemples de tipis d’events

`QUIT` → tancar finestra
`KEYDOWN` → tecla premuda
`KEYUP` → tecla alliberada
`MOUSEBUTTONDOWN` → clic ratolí
`MOUSEMOTION` → moviment ratolí

```python
if event.type == pygame.KEYDOWN:
    if event.key == pygame.K_LEFT:
        print("left")
    if event.key == pygame.K_RIGHT:
        print("right")
```

---

Documentació d'events:
https://www.pygame.org/docs/ref/event.html

Documentació de tecles:
https://www.pygame.org/docs/ref/key.html#key-constants-label

---

## Exemple: moure un personatge

<div style="display: flex; gap: 30px;">

<div style="flex: 1;">

```python
if event.key == pygame.K_LEFT:
    x -= 10
if event.key == pygame.K_RIGHT:
    x += 10
```

Aquest moviment no és fluid, ens fa premer la tecla cada cop que volem fer un pas.

</div>

<div style="flex: 1;">

![alt text](https://programming-24.mooc.fi/aac8387e39d3bb4adbfc1c36cae57345/pygame_move_robot.gif)

</div>
</div>

---

## Exemple: moure un personatge

```python
to_right = False
to_left = False
if event.type == pygame.KEYDOWN:
    if event.key == pygame.K_RIGHT:
        to_right = True

if event.type == pygame.KEYUP:
    if event.key == pygame.K_RIGHT:
        to_right = False

if to_right:
    x += 2
if to_left:
    x -= 2
```

---

<div class="exercici">
Four directions

Four walls

Two players

</div>

---

## Events del ratolí

<div style="display: flex; gap: 30px;">
<div style="flex: 2;">

```python
import pygame

pygame.init()
window = pygame.display.set_mode((640, 480))

while True:
    for event in pygame.event.get():
        if event.type == pygame.MOUSEBUTTONDOWN:
            print(event.button, event.pos)

        if event.type == pygame.QUIT:
            exit()
```

</div>
<div style="flex: 1;">

1 (82, 135)

1 (369, 135)

1 (269, 297)

3 (515, 324)

</div>
</div>

---

## Exemple: Dibuixar on click

<div style="display: flex; gap: 30px;">
<div style="flex: 2;">

```python
if event.type == pygame.MOUSEBUTTONDOWN:
    x = event.pos[0]
    y = event.pos[1]

x = event.pos[0] - robot.get_width()/2
y = event.pos[1] - robot.get_height()/2
```

</div>
<div style="flex: 1;">

![alt text](https://programming-24.mooc.fi/a41511bd13655f68553cc7e34de61edf/pygame_cursor.gif)

</div>
</div>

---

## Exemple: Seguir el ratolí

<div style="display: flex; gap: 30px;">
<div style="flex: 2;">

```python
if robot_x < target_x:
    robot_x += 1
if robot_x > target_x:
    robot_x -= 1
if robot_y < target_y:
    robot_y += 1
if robot_y > target_y:
    robot_y -= 1
```

</div>
<div style="flex: 1;">

![alt text](https://programming-24.mooc.fi/cd4d53df2a1564c181f38b7a2d45e7c9/pygame_cursor2.gif)

</div>
</div>

---

<div class="exercici">
Robot and mouse

The location of the robot

</div>
