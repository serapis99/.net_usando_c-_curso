# Lanzamiento y Relanzamiento de Excepciones en C#

## 📋 Descripción

En C#, no solo podemos capturar excepciones, también podemos **lanzarlas explícitamente** usando la palabra clave `throw`.

Lanzar una excepción significa indicar de forma intencional que:

* Se ha producido una condición inválida.
* El estado del sistema no es correcto.
* El método no puede continuar su ejecución normalmente.

Esto es fundamental en el diseño de APIs y clases robustas.

---

## 🎯 Problema que resuelve

Permite:

* Validar argumentos de entrada.
* Proteger invariantes de una clase.
* Comunicar errores de forma clara.
* Evitar estados inconsistentes.

Sin lanzar excepciones:

* Los métodos pueden devolver resultados incorrectos.
* Los errores pueden pasar silenciosamente.
* El diseño pierde robustez.

---

## 💡 Idea central

> Lanzar una excepción es una forma explícita de declarar que el contrato del método fue violado.

Un método bien diseñado valida sus parámetros y falla de manera clara cuando algo no es correcto.

---

## 🔎 Desarrollo

## 🔹 Lanzar una excepción con `throw`

Sintaxis básica:

```csharp
throw new TipoDeExcepcion();
```

Ejemplo:

```csharp
public static string NombreDelMes(int mes)
{
    switch (mes)
    {
        case 12:
            return "Diciembre";

        default:
            throw new ArgumentOutOfRangeException(nameof(mes), 
                "El mes debe estar entre 1 y 12.");
    }
}
```

Aquí:

* Si el valor no es válido, el método no intenta continuar.
* Se lanza una excepción clara.
* Se informa qué parámetro es incorrecto.

`ArgumentOutOfRangeException` es apropiada cuando un valor está fuera del rango esperado.

---

## 🔹 Validación temprana (Guard Clauses)

Es más profesional validar antes de ejecutar lógica compleja:

```csharp
public static string NombreDelMes(int mes)
{
    if (mes < 1 || mes > 12)
        throw new ArgumentOutOfRangeException(nameof(mes));

    // lógica
}
```

Esto mejora:

* Claridad
* Legibilidad
* Mantenibilidad

---

## 🔹 Relanzar una excepción (Rethrow)

A veces necesitamos:

1. Capturar una excepción.
2. Ejecutar lógica adicional (log, limpieza, auditoría).
3. Volver a lanzarla.

Para esto usamos:

```csharp
throw;
```

Ejemplo:

```csharp
try
{
    ProcesarDatos();
}
catch (Exception ex)
{
    Console.WriteLine("Ocurrió un error. Registrando información...");
    Console.WriteLine(ex.Message);

    throw;
}
```

Clave importante:

* `throw;` preserva el stack trace original.
* `throw ex;` reinicia el stack trace (mala práctica).

---

## 🔹 Diferencia crítica

Correcto:

```csharp
throw;
```

Incorrecto:

```csharp
throw ex;
```

La segunda forma destruye el stack trace original, dificultando el diagnóstico.

---

## 🔹 Cuándo lanzar excepciones

Se deben lanzar cuando:

* Un argumento es inválido.
* El estado interno es inconsistente.
* Una operación no puede completarse.
* Se rompe el contrato del método.

No se deben lanzar cuando:

* El error es parte del flujo normal.
* Se puede validar previamente sin excepción.

---

## 🧠 Buenas prácticas

1. Usa excepciones específicas (`ArgumentNullException`, `InvalidOperationException`, etc.).
2. Incluye mensajes claros y descriptivos.
3. Usa `nameof(parametro)` en validaciones.
4. No uses excepciones para control de flujo normal.
5. Usa `throw;` para relanzar, no `throw ex;`.

---

## 🧠 20% Pareto (lo imprescindible)

Domina esto:

* `throw` lanza una excepción explícitamente.
* Se usa para validar contratos.
* `throw;` preserva el stack trace.
* `throw ex;` destruye el stack trace.
* Las excepciones deben comunicar fallos reales, no flujo normal.

---

## 🤔 Reflexión (con respuestas)

**1. ¿Por qué es importante lanzar excepción cuando un parámetro es inválido?**
Porque protege el contrato del método y evita estados incorrectos.

**2. ¿Qué problema causa usar `throw ex;`?**
Se pierde el stack trace original.

**3. ¿Una excepción siempre debe manejarse en el mismo método?**
No. Puede propagarse hasta una capa superior que tenga contexto suficiente para manejarla.

**4. ¿Qué comunica un método que lanza excepción ante entrada inválida?**
Que el método tiene reglas claras y no acepta estados incorrectos.

---

## ✍️ Resumen

Lanzar excepciones es una herramienta de diseño, no solo de error.

Permite:

* Defender contratos.
* Comunicar fallos correctamente.
* Mantener coherencia en el sistema.

El relanzamiento (`throw;`) permite agregar lógica intermedia sin perder información de diagnóstico.

Un diseño profesional usa excepciones para proteger la integridad del sistema, no como sustituto de validaciones básicas.
