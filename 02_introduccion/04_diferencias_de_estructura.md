# 🧭 Guía: Diferencia entre versiones antiguas y modernas de C#

## 🎯 Objetivo

Comprender por qué en versiones modernas de **C#** ya no es necesario declarar explícitamente la clase `Program` ni el método `Main`, y cómo el compilador maneja este cambio.

---

## 🛠️ Requisitos o herramientas necesarias

* [ ] SDK de .NET instalado
* [ ] Conocimientos básicos de C#
* [ ] Proyecto de consola creado con `dotnet new console`

---

## 📋 Comparación entre versiones

### 🔹 Versión antigua (C# tradicional)

Antes (por ejemplo en .NET Framework o versiones anteriores de C#), era obligatorio definir explícitamente:

* Namespace
* Clase `Program`
* Método `Main`

```csharp
using System;

namespace PrimeraAplicacion
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Bienvenido a C#");
        }
    }
}
```

Aquí el punto de entrada del programa es:

```csharp
static void Main(string[] args)
```

El compilador sabe que debe comenzar la ejecución desde ese método.

---

### 🔹 Versión moderna (C# 9 en adelante)

En versiones modernas (desde .NET 6 en adelante por defecto), el código puede escribirse así:

```csharp
Console.WriteLine("Bienvenido a C#");
```

Mucho más simple 👌

---

## ❓ ¿Cómo sabe la nueva versión cuál es la clase `Main`?

La respuesta es: **Top-Level Statements**.

Desde **C# 9**, el compilador permite escribir código directamente en el archivo sin declarar explícitamente `Main`.

Internamente, el compilador transforma tu código en algo equivalente a esto:

```csharp
using System;

internal class Program
{
    private static void Main(string[] args)
    {
        Console.WriteLine("Bienvenido a C#");
    }
}
```

Es decir:

* El compilador **genera automáticamente la clase `Program`**
* Genera automáticamente el método `Main`
* Coloca tu código dentro de ese método

---

## 💡 Idea clave

En C# moderno, el punto de entrada sigue siendo `Main`, pero ahora el compilador lo genera automáticamente para simplificar el código.

---

## 🧠 ¿Por qué hicieron este cambio?

* Reducir código repetitivo
* Facilitar el aprendizaje
* Hacer más limpio el inicio de proyectos pequeños
* Modernizar la sintaxis

Esto hace que el primer programa sea más intuitivo para principiantes.

---

## 🧠 Tips y recomendaciones

* Puedes seguir usando la estructura tradicional si lo deseas.
* En proyectos grandes, entender cómo funciona `Main` sigue siendo importante.
* Este comportamiento aplica principalmente a proyectos creados con `dotnet new console` en versiones modernas.

---

## 🤔 Reflexión

El lenguaje no eliminó `Main`.
Simplemente lo ocultó para que el desarrollador se enfoque primero en la lógica y no en la estructura ceremonial.

---

## ✍️ Resumen

🔹 Antes: debías declarar `class Program` y `static void Main`.
🔹 Ahora: puedes escribir código directamente.
🔹 El compilador genera `Main` automáticamente usando *Top-Level Statements*.