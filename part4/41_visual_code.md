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

# L’editor Visual Studio Code, l’intèrpret de Python i l’eina de debugging integrada

- Utilitzar l’editor Visual Studio Code per completar els exercicis del curs.
- Coneixer l’intèrpret interactiu de Python i utilitzar-lo per executar codi línia a línia.

---

## Instal·lació de l’entorn per programar

Fins ara, totes les activitats del curs les has fet directament al navegador amb l’editor incrustat. Això està molt bé per als primers passos, però ara és moment de passar a un editor real de programació.

Hi ha molts editors possibles, però en aquest curs farem servir Visual Studio Code (VS Code), que s’ha convertit en un dels més populars els darrers anys.

Tutorial complet: https://www.mooc.fi/en/installation/vscode/

---

## Hauràs d’instal·lar

- Visual Studio Code: https://code.visualstudio.com/download
- Python 3: https://www.python.org/downloads/
- L’extensió de Python per a VS Code: https://marketplace.visualstudio.com/items?itemName=ms-python.python
- El plugin TMC, que executarà els tests dels exercicis: https://marketplace.visualstudio.com/items?itemName=moocfi.test-my-code Fes _log-in_ amb el teu usuari, busca INS Vila de Gràcia a Organizations i entra a Python Programming 2024.

---

## Comprovem que funciona tot correctament

<div class="exercici">

Hello Visual Studio Code ⭐

</div>

---

## Executar codi amb Visual Studio Code

El mètode més senzill és clicar la icona ▶️ a la cantonada superior dreta.

De vegades passa que un programa queda executant-se en segon pla (esperant un input, o bloquejat en un bucle infinit) sense que te n’adonis.
Quan intentes executar-ne un altre, simplement no funciona perquè l’anterior encara està ocupant recursos.

Solució ràpida:
Prem `Control + C` al terminal per aturar l’execució actual.

---

## L’intèrpret interactiu de Python

L’intèrpret és una de les eines més útils per a qualsevol programador/a de Python.
Permet executar codi línia a línia, immediatament.

Linux / macOS: Anar al Terminal y escriure `python3`
Windows: Inicio - Python 3.XX

A Visual Studio Code, quan executis un programa, s’obrirà el terminal. Allà també hi pots escriure `python3`.

També hi ha opcions web, com: https://www.python.org/shell/

---

## Tancar l’intèrpret

És important sobretot a VS Code: si l’intèrpret queda obert, intentar executar un programa donarà un error força críptic. Per tancar:

- `quit()`
- `exit()`
- `Control+D` (Linux / MacOS)
- `Control+Z` (Windows)

---

## El _debugger_ integrat de Visual Studio Code

Fins ara hem fet _debugging_ bàsic amb `print()`.
Ara veurem una eina molt potent: el _debugger_ visual de VS Code.

**Com s’utilitza?**

1. Marca un punt d’interrupció vermell (_breakpoint_) clicant a l’esquerra d’una línia.
2. Ves al menú Run (o ejecutar) → Start debugging (o iniciar depuración).
3. Selecciona Python File.
4. El programa s’executarà fins arribar al breakpoint i quedarà aturat.

---

**Què pots fer mentre està aturat?**

- A l’esquerra tens la vista Variables, amb totes les variables i els seus valors.
- Pots avançar línia a línia amb Step into.
- Al panell Debug Console, pots provar expressions amb les variables actuals

---

Cada programador té les seves preferències:

- hi ha qui prefereix molts `print()`,
- hi ha qui fa servir sempre el depurador visual,
- i molts combinen ambdós mètodes.

Val la pena provar les eines i decidir què t’és més còmode.
