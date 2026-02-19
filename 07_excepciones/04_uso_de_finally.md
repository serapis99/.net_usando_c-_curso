# Bloque `finally` en C#

## 📋 Descripción

El bloque `finally` es una sección opcional que puede acompañar a `try` y `catch`.

Su característica principal es:

> El código dentro de `finally` se ejecuta siempre, ocurra o no una excepción.

Se utiliza principalmente para:

* Liberar recursos.
* Cerrar conexiones.
* Liberar archivos.
* Ejecutar limpieza obligatoria.
* Restaurar estados.

---

## 🎯 Problema que resuelve

Cuando trabajamos con recursos externos:

* Archivos
* Conexiones a base de datos
* Streams
* Sockets

Si ocurre una excepción antes de cerrar el recurso, este puede quedar:

* Abierto
* Bloqueado
* En estado inconsistente

El bloque `finally` garantiza que la limpieza ocurra sin importar el resultado.

---

## 💡 Idea central

> `finally` garantiza ejecución, incluso cuando el flujo se interrumpe por una excepción.

Es una herramienta de seguridad estructural del código.

---

## 🔎 Desarrollo

## 🔹 Estructura básica

```csharp
try
{
    // Código que puede fallar
}
catch (Exception ex)
{
    // Manejo del error
}
finally
{
    // Código que SIEMPRE se ejecuta
}
```

El flujo es:

1. Se ejecuta `try`.
2. Si ocurre excepción → se ejecuta `catch`.
3. Luego siempre se ejecuta `finally`.
4. Después continúa el flujo normal o se propaga la excepción.

---

## 🔹 Ejemplo práctico

```csharp
FileStream archivo = null;

try
{
    archivo = new FileStream("datos.txt", FileMode.Open);
    Console.WriteLine("Archivo abierto");
}
catch (Exception ex)
{
    Console.WriteLine("Ocurrió un error: " + ex.Message);
}
finally
{
    if (archivo != null)
    {
        archivo.Close();
        Console.WriteLine("Archivo cerrado");
    }
}
```

Aquí:

* Si el archivo se abre correctamente → se cerrará.
* Si ocurre excepción → igualmente se cerrará.
* Nunca queda abierto accidentalmente.

---

## 🔹 finally sin catch

También es válido usar `finally` sin `catch`:

```csharp
try
{
    Console.WriteLine("Ejecutando operación");
}
finally
{
    Console.WriteLine("Siempre se ejecuta");
}
```

Esto es útil cuando:

* No quieres manejar la excepción aquí.
* Solo quieres garantizar limpieza.

---

## 🔹 ¿Qué ocurre si hay `return`?

Incluso si hay `return` dentro del `try`:

```csharp
try
{
    return;
}
finally
{
    Console.WriteLine("Se ejecuta antes de salir");
}
```

El bloque `finally` se ejecuta antes de que el método termine.

---

## 🔹 Relación con `using`

En C#, lo más profesional hoy en día es usar `using` para liberar recursos automáticamente:

```csharp
using (var archivo = new FileStream("datos.txt", FileMode.Open))
{
    Console.WriteLine("Archivo abierto");
}
```

Internamente, `using` genera un `try/finally` donde se llama a `Dispose()`.

Es una forma más segura y limpia de manejar recursos.

---

## 🧠 Buenas prácticas

1. Usa `finally` para liberar recursos críticos.
2. No pongas lógica compleja dentro de `finally`.
3. No lances excepciones nuevas dentro de `finally` sin necesidad.
4. Prefiere `using` cuando trabajes con objetos que implementen `IDisposable`.
5. Mantén el bloque de limpieza simple y predecible.

---

## 🧠 20% Pareto (lo imprescindible)

Domina esto:

* `finally` se ejecuta siempre.
* Se usa para liberar recursos.
* Se ejecuta incluso si hay excepción o `return`.
* `using` es una forma moderna de aplicar el mismo principio.
* No debe contener lógica de negocio.

---

## 🤔 Reflexión (con respuestas)

**1. ¿Por qué no basta con cerrar recursos dentro del try?**
Porque si ocurre una excepción antes del cierre, el código no se ejecutará.

**2. ¿finally se ejecuta si no hay catch?**
Sí.

**3. ¿Qué ventaja tiene using sobre finally manual?**
Reduce errores humanos y mejora legibilidad.

**4. ¿Debe colocarse lógica de negocio en finally?**
No. Solo limpieza y liberación de recursos.

---

## ✍️ Resumen

El bloque `finally` garantiza ejecución independientemente del resultado del `try`.

Se utiliza principalmente para:

* Liberar recursos.
* Garantizar limpieza.
* Mantener consistencia del sistema.

En desarrollo profesional, el uso correcto de `finally` o `using` es clave para evitar fugas de memoria y recursos bloqueados.
