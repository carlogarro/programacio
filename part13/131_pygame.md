---
marp: true
theme: gaia
_class: lead
paginate: true
title: PyGame
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

# Pygame

- Instal·lar la llibreria `pygame`
- Crear una finestra gràfica
- Tancar correctament el programa
- Mostrar imatges dins la finestra

---

## Què és Pygame?

Pygame és una llibreria de Python per crear videojocs. Permet:

- dibuixar elements gràfics
- detectar teclat i ratolí
- reproduir sons
- controlar animacions

---

Per instal·lar-ho, a la terminal:

```bash
pip3 install pygame
```

Després comprova:

```python
import pygame
print("Pygame instal·lat")
```

---

```python
import pygame

pygame.init()

window = pygame.display.set_mode((640, 480)) #finestra xy dimensions

window.fill((0,0,0)) #pantalla negra rgb
pygame.display.flip() #actualitza la pantalla

while True:
    for event in pygame.event.get(): #tots els events observats
        if event.type == pygame.QUIT:
            exit()
```

Més sobre colors a [https://htmlcolorcodes.com/](https://htmlcolorcodes.com/)

---

```python
import pygame

pygame.init()
window = pygame.display.set_mode((640, 480))

robot = pygame.image.load("robot.png")

window.fill((0, 0, 0))
window.blit(robot, (100, 50))
pygame.display.flip()

while True:
for event in pygame.event.get():
if event.type == pygame.QUIT:
exit()
```

---

## Sistema de coordenades

(0,0) és la cantonada superior esquerra.
X creix cap a la dreta. Y creix cap avall

```python
window.blit(robot, (0, 0))
window.blit(robot, (300, 0))
window.blit(robot, (100, 200))
```

La mateixa imatge es pot reutilitzar moltes vegades.

---

## Centrar una imatge

```python
width = robot.get_width()
height = robot.get_height()
window.blit(robot, (320-width/2, 240-height/2))
```

---

<div class="exercici">

Four robots

Robots in a row

A hundred robots

Random robots

</div>
