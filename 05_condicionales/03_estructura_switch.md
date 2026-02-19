# Estructura `switch` en C#

La estructura `switch` nace para facilitar la lectura y organización del código cuando se deben evaluar múltiples condiciones en cadena.

Aunque puede resolverse con varios `if / else if`, `switch` hace el código más claro cuando todas las comparaciones dependen de una misma expresión.

---

## 📌 Sintaxis general

```csharp
switch (expresionControl)
{
    case constante1:
        // código a ejecutar
        break;

    case constante2:
        // código a ejecutar
        break;

    case constante3:
        // código a ejecutar
        break;

    default:
        // código si no coincide ningún case
        break;
}
```

📌 `expresionControl` se evalúa una sola vez.
📌 Se ejecuta el `case` que coincida con el valor.

---

# 🧠 ¿Por qué usar `switch` en vez de `if`?

Ejemplo con `if`:

```csharp
if (medioTransporte == "coche")
{
    ...
}
else if (medioTransporte == "tren")
{
    ...
}
else if (medioTransporte == "avion")
{
    ...
}
```

Con `switch` queda más limpio y organizado cuando todas las comparaciones son iguales contra una sola variable.

---

# ⚠ A tener en cuenta

✔ Cada expresión constante debe ser única.
✔ Los `case` solo pueden contener valores constantes.
✔ No se pueden repetir valores en distintos `case`.
✔ Cada `case` debe terminar con `break`, `return` o `throw`.
✔ `default` es opcional pero recomendable.

---

## 📌 Tipos que se pueden usar en `switch`

Tradicionalmente:

* `int`
* `char`
* `string`
* `enum`

❌ No se puede usar directamente:

* `double`
* `float`

⚠ Esto es porque las comparaciones con decimales pueden ser imprecisas.

---

# 🚀 Ejemplo práctico

```csharp
Console.WriteLine("Escoge medio de transporte (coche, tren, avion)");
string medioTransporte = Console.ReadLine();

switch (medioTransporte)
{
    case "coche":
        Console.WriteLine("Velocidad media: 100 km/h");
        break;

    case "tren":
        Console.WriteLine("Velocidad media: 250 km/h");
        break;

    case "avion":
        Console.WriteLine("Velocidad media: 800 km/h");
        break;

    default:
        Console.WriteLine("Transporte no contemplado");
        break;
}
```

---

# 🧠 Concepto clave

* `switch` evalúa una sola expresión.
* Es ideal cuando se comparan muchos valores posibles de la misma variable.
* Hace el código más legible que múltiples `else if`.

---

# 🎯 Resumen

Usa `switch` cuando:

* Evalúas una sola variable.
* Comparas contra valores constantes.
* Tienes muchos `else if`.

Usa `if` cuando:

* Las condiciones son complejas.
* Involucran rangos (`>`, `<`, `>=`, etc.).
* Hay múltiples variables en la condición.