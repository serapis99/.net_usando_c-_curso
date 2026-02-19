# Manejo de Excepciones en C#

## 📋 Descripción

Las **excepciones** en C# son mecanismos del runtime que representan errores que ocurren durante la ejecución del programa.

Una excepción no es simplemente un error lógico: es un **objeto que el runtime crea cuando detecta una situación anormal** que impide continuar la ejecución normal.

Ejemplos comunes:

* Entrada de datos inválida
* Acceso a archivos inexistentes
* Conexiones a bases de datos interrumpidas
* Errores de red
* Conversión de tipos inválida
* Desbordamiento numérico

En C#, el manejo se realiza con:

* `try` → bloque que contiene código que puede fallar
* `catch` → bloque que captura y maneja la excepción
* `finally` → bloque opcional que siempre se ejecuta

---

## 🎯 Problema que resuelve

Las excepciones permiten:

* Evitar que la aplicación termine abruptamente.
* Separar el flujo normal del flujo de error.
* Capturar información detallada del problema.
* Mantener estabilidad del sistema.

Sin manejo de excepciones:

* El programa se detiene.
* Se pierde información de diagnóstico.
* La experiencia del usuario se degrada.

---

## 💡 Idea central

> Una excepción es el mecanismo que usa el runtime para interrumpir el flujo cuando ocurre una condición inesperada.

El desarrollador decide si:

* La captura y maneja.
* La transforma.
* La propaga hacia capas superiores.

---

## 🔎 Desarrollo

### 🔹 Estructura básica

```csharp
try
{
    // Código que puede lanzar una excepción
}
catch (TipoDeExcepcion ex)
{
    // Manejo del error
}
```

El flujo funciona así:

1. El código dentro de `try` se ejecuta normalmente.
2. Si ocurre un error, el runtime crea un objeto excepción.
3. Se interrumpe el flujo.
4. Se transfiere el control al `catch` compatible más cercano.

---

### 🔹 Ejemplo simple

```csharp
int numero;
Console.WriteLine("Escribe un número");

try
{
    numero = int.Parse(Console.ReadLine());
}
catch (FormatException)
{
    numero = 0;
    Console.WriteLine("No has ingresado un número válido");
}
```

Aquí:

* `int.Parse()` puede lanzar una `FormatException`.
* Si ocurre, el programa no se detiene.
* Se asigna un valor seguro y continúa la ejecución.

---

### 🔹 Múltiples catch

```csharp
try
{
    numero = int.Parse(Console.ReadLine());
}
catch (FormatException)
{
    numero = 0;
    Console.WriteLine("Formato inválido");
}
catch (OverflowException)
{
    numero = 0;
    Console.WriteLine("Número demasiado grande o pequeño");
}
```

Regla importante:

* Las excepciones más específicas deben ir primero.
* La excepción base (`Exception`) debe ir al final.

---

### 🔹 Capturar la excepción base

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

`Exception` es la clase base de todas las excepciones en .NET.

Propiedades importantes:

* `Message` → descripción del error
* `StackTrace` → dónde ocurrió
* `InnerException` → error interno que originó el actual
* `Source` → origen del error

---

### 🔹 Catch sin especificar tipo

```csharp
catch
{
    Console.WriteLine("Ocurrió un error");
}
```

Esto captura cualquier excepción, pero no permite acceder a la información del error.
En sistemas profesionales se recomienda capturar tipos específicos.

---

### 🔹 Evitar excepciones innecesarias

Cuando el error es esperable (por ejemplo, validar entrada del usuario), es mejor usar métodos como:

```csharp
if (int.TryParse(Console.ReadLine(), out int numero))
{
    Console.WriteLine("Número válido");
}
else
{
    Console.WriteLine("Entrada inválida");
}
```

Esto evita el costo de lanzar excepciones innecesariamente.

---

### 🔹 Qué ocurre internamente

Cuando se lanza una excepción:

1. Se crea un objeto derivado de `Exception`.
2. Se captura el estado de la pila (stack trace).
3. El runtime busca un `catch` compatible.
4. Se realiza un proceso llamado *stack unwinding*.
5. El flujo se transfiere al bloque de manejo.

Este proceso tiene costo de rendimiento.

Por eso:

> Las excepciones no deben usarse como mecanismo normal de control de flujo.

---

## 🧠 Buenas prácticas

1. Captura la excepción más específica posible.
2. No uses `catch` vacío.
3. No ocultes errores sin registrarlos.
4. No uses excepciones para validaciones frecuentes.
5. Utiliza `TryParse` cuando el fallo sea esperable.
6. Permite que excepciones críticas se propaguen cuando corresponda.

---

## 🧠 20% Pareto (lo imprescindible)

Domina esto:

* `try` contiene código riesgoso.
* `catch` captura errores específicos.
* `Exception` es la clase base.
* Las excepciones interrumpen el flujo normal.
* No deben usarse como control habitual del programa.
* `TryParse` es preferible cuando el error es esperado.

---

## 🤔 Reflexión (con respuestas)

**1. ¿Toda excepción indica un bug?**
No necesariamente. Puede ser una condición externa inesperada.

**2. ¿Por qué no debo usar excepciones como validación común?**
Porque lanzar excepciones es costoso y rompe el flujo normal.

**3. ¿Qué ocurre si capturo primero `Exception` y luego una específica?**
La específica nunca se ejecutará.

**4. ¿Qué ventaja tiene capturar excepciones específicas?**
Permite manejar cada error según su naturaleza.

---

## ✍️ Resumen

Las excepciones en C# son el mecanismo estándar para manejar errores en tiempo de ejecución.

Úsalas cuando:

* Ocurre algo inesperado.
* Fallan recursos externos.
* Se requiere propagar un error crítico.

Evítalas cuando:

* El error es predecible y validable.
* Forman parte del flujo normal.

Un buen manejo de excepciones refleja diseño robusto, claridad arquitectónica y pensamiento profesional.
