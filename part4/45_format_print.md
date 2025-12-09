Format del print

El print serveix per mostrar informació per pantalla

Podem donar format al text de diferents maneres

Això fa el codi més llegible i el resultat més clar

➕ Concatenació amb +
print("Hola " + nom + " tens " + str(edat) + " anys")

Uneix textos amb +

⚠️ Tot ha de ser string

Cal convertir números amb str()

🔹 Diversos arguments al print
print("Hola", nom, "tens", edat, "anys")

Cada part va separada per comes

print afegeix espais automàticament

Funciona amb tipus diferents

⚙️ Separador (sep)
print("Hola", nom, edat, sep=" - ")

sep indica què posa entre els elements

Pot ser qualsevol text ("", " - ", "\n", etc.)

↵ Final de línia (end)
print("Hola", end=" ")
print("què tal?")

Per defecte print acaba amb un salt de línia

end permet canviar aquest comportament

✨ f-strings (recomanat)
print(f"Hola {nom}, tens {edat} anys")

Forma moderna i clara

No cal convertir tipus

Molt llegible 👍

🔢 Formats amb f-strings
print(f"El resultat és {num:.2f}")

.2f → 2 decimals

Ideal per números decimals

📐 Alineació de text
print(f"{nom:15} | {nom:>15}")

Reserva espai per al text

: defineix el format

> alinea a la dreta

✅ Resum

- → simple però limitat

comes al print → flexible

f-strings → la millor opció 🚀

Permeten format, decimals i alineació
