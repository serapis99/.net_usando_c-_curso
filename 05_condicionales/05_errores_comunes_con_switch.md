# Errores comunes con switch clásico en C#

---

## 📋 Descripción

El `switch` clásico es una estructura de control que permite evaluar múltiples casos basados en una misma expresión.

Su sintaxis básica es:

```csharp
switch (expresion)
{
    case valorConstante:
        // código
        break;

    default:
        // código
        break;
}
```

Aunque es sencilla, es común cometer errores que generan fallos de compilación o comportamientos inesperados.

---

## 🎯 Problema que suele aparecer

Cuando se usa `switch` sin entender bien sus reglas:

* aparecen errores de compilación
* se ejecuta lógica no deseada
* se olvidan casos importantes
* el código se vuelve difícil de mantener

Conocer los errores comunes evita estos problemas.

---

## 💡 Idea central

> El `switch` clásico es estricto: requiere valores constantes, casos únicos y control explícito del flujo.

La mayoría de errores ocurren por no respetar estas reglas.

---

# ⚠️ Errores más comunes

---

## 1️⃣ Olvidar el `break`

Cada `case` debe terminar con:

```csharp
break;
```

❌ Incorrecto:

```csharp
switch (numero)
{
    case 1:
        Console.WriteLine("Uno");
    case 2:
        Console.WriteLine("Dos");
        break;
}
```

Esto genera error en C#, porque no permite continuar al siguiente `case` sin control de flujo.

✔️ Correcto:

```csharp
case 1:
    Console.WriteLine("Uno");
    break;
```

---

## 2️⃣ Usar valores no constantes en `case`

Los `case` solo aceptan valores conocidos en tiempo de compilación.

❌ Incorrecto:

```csharp
int x = 5;

switch (numero)
{
    case x: // error
        break;
}
```

✔️ Correcto:

```csharp
const int x = 5;
```

---

## 3️⃣ Repetir valores en distintos `case`

❌ Incorrecto:

```csharp
case 1:
    break;
case 1:
    break;
```

Cada expresión debe ser única.

---

## 4️⃣ Usar tipos no soportados

El `switch` clásico solo permite:

* `int`
* `char`
* `string`
* `enum`

❌ No permite:

* `double`
* `float`
* `decimal`

Ejemplo incorrecto:

```csharp
double numero = 2.5;

switch (numero) // error
{
}
```

---

## 5️⃣ No usar `default`

Aunque no es obligatorio, es una mala práctica omitirlo.

Si ningún `case` coincide, el programa simplemente continúa sin hacer nada.

✔️ Buena práctica:

```csharp
default:
    Console.WriteLine("Valor no reconocido");
    break;
```

---

## 6️⃣ Problemas con mayúsculas y minúsculas

Cuando se usa `string`, la comparación distingue entre mayúsculas y minúsculas.

```csharp
case "Coche"
```

No es lo mismo que:

```csharp
"coche"
```

✔️ Buena práctica:

```csharp
switch (medioTransporte.ToLower())
```

---

# 🧠 Buenas prácticas al usar switch clásico

---

## 1️⃣ Siempre cerrar cada case con break

Evita errores de flujo inesperados.

---

## 2️⃣ Usar default como red de seguridad

Protege contra valores no contemplados.

---

## 3️⃣ No usar switch cuando hay condiciones complejas

Si necesitas:

* rangos
* múltiples condiciones
* comparaciones lógicas

Es mejor usar `if`.

---

## 4️⃣ Mantenerlo simple

El `switch` clásico funciona mejor cuando:

* se comparan valores directos
* la lógica es clara
* cada caso es independiente

---

## 🧠 20% Pareto (lo imprescindible)

Si entiendes esto, evitas el 90% de errores:

* Cada `case` necesita `break`
* Los valores deben ser constantes
* No puede haber duplicados
* Solo admite ciertos tipos
* Siempre es recomendable usar `default`

---

## 🤔 Reflexión (con respuestas)

**¿Por qué C# obliga a usar break?**
Para evitar ejecución accidental de múltiples casos.

**¿Por qué los case deben ser constantes?**
Porque el switch se resuelve en tiempo de compilación.

**¿Cuándo no conviene usar switch clásico?**
Cuando necesitas evaluar rangos o condiciones complejas.

**¿Qué pasa si ningún case coincide y no hay default?**
No ocurre nada y el programa continúa.

---

## ✍️ Resumen

⚠️ El `switch` clásico es una herramienta clara y segura, pero estricta.

Para usarlo correctamente debes:

* respetar sus reglas
* controlar el flujo con `break`
* manejar el `default`
* evitar tipos no soportados

Dominar estos detalles mejora la calidad y seguridad del código.
