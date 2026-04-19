---
marp: true
theme: gaia
_class: lead
paginate: true
title: Animació
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

# Animació amb Pygame

- Crear animacions amb `pygame`
- Controlar la velocitat del programa
- Utilitzar un rellotge (`Clock`)
- Aplicar trigonometria bàsica

---

## Com funciona una animació?

<div style="display: flex; gap: 30px;">

<div style="flex: 2;">
Una animació consisteix en:

1. dibuixar una imatge
2. canviar-ne la posició
3. tornar-la a dibuixar
4. repetir moltes vegades

Això crea la il·lusió de moviment.

</div>

<div style="flex: 1;">

<img src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/5c1466fb-6ddb-4a16-8208-940a50c536b1/d88g9cf-48f164b9-dba6-450d-a44e-ef4cd63f3fe9.gif?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiIvZi81YzE0NjZmYi02ZGRiLTRhMTYtODIwOC05NDBhNTBjNTM2YjEvZDg4ZzljZi00OGYxNjRiOS1kYmE2LTQ1MGQtYTQ0ZS1lZjRjZDYzZjNmZTkuZ2lmIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.Ip1iAJFrxF3QYsqobJt8bwvfnmXd5c2jeTDksWTwK2w" alt="il·lusió de moviment" width="500"/>

</div>

</div>

---

```python
import pygame
pygame.init()
window = pygame.display.set_mode((640, 480))
robot = pygame.image.load("robot.png")
x = 0
y = 0
clock = pygame.time.Clock()
while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            exit()
    window.fill((0, 0, 0))
    window.blit(robot, (x, y))
    pygame.display.flip()
    x += 1
    clock.tick(60)
```

---

El mètode `tick` s'encarrega de la velocitat de l'animació. L'argument 60 dicta que el bucle s'ha d'executar 60 vegades per segon, cosa que significa que la imatge es mou 60 píxels cap a la dreta cada segon. Això coincideix aproximadament amb el valor de FPS o fotogrames per segon que s'utilitza amb els jocs.

En principi, el mètode `tick` assegura que l'animació s'executi a la mateixa velocitat a tots els ordinadors. Si no hi hagués aquest temps implicat, la velocitat de l'animació dependria de la velocitat de l'ordinador.

---

## Rebot a la paret

```python
velocity = 1
#...
x += velocity
if velocity > 0 and x+robot.get_width() >= 640:
    velocity = -velocity
if velocity < 0 and x <= 0:
    velocity = -velocity

clock.tick(60)
```

---

## Moviment circular

```python
x = 320+math.cos(angle)*100-robot.get_width()/2
y = 240+math.sin(angle)*100-robot.get_height()/2

window.fill((0, 0, 0))
window.blit(robot, (x, y))
pygame.display.flip()

angle += 0.01
```

---

El robot gira al voltant d'un cercle de radi 100 al voltant del centre de la finestra. La hipotenusa en aquest escenari és el radi del cercle. La funció cosinus dóna la longitud del costat adjacent d'un triangle rectangle en relació amb la hipotenusa, donant-nos la coordenada x de la ubicació. La funció sinus dóna la longitud del costat oposat, és a dir, la coordenada y. La ubicació s'ajusta a la mida de la imatge, de manera que el centre del cercle estigui al centre de la finestra.

Amb cada iteració, la mida de l'angle s'incrementa en 0,01. Com que utilitzem radians, un cercle complet és 2π, que equival a aprox 6,28. El robot necessita unes 628 iteracions per fer un cercle complet, i a 60 iteracions per segon això triga poc més de 10 segons.

---

<div class="exercici">
Vertical movement

Round the perimeter

Two robots

Robots in a circle

Bouncing ball

Robot invasion

</div>
