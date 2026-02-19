# Filtrado de Excepciones y Control de Desbordamiento en C#

## 📋 Descripción

En C#, es posible **filtrar excepciones** utilizando la cláusula `when` dentro de un bloque `catch`.

Esto permite agregar una **condición adicional** para decidir si una excepción debe capturarse o no.

Además, C# permite controlar el comportamiento frente a **desbordamientos aritméticos (overflow)** mediante la palabra clave `checked`.

Ambos conceptos están relacionados con el manejo fino de errores y el control explícito del comportamiento del runtime.

---

## 🎯 Problema que resuelve

1. El filtrado con `when` permite:

   * Manejar excepciones de forma más precisa.
   * Evitar múltiples bloques `catch` complejos.
   * Separar errores por criterios específicos.

2. `checked` permite:

   * Detectar errores de desbordamiento numérico.
   * Evitar resultados incorrectos silenciosos.
   * Aumentar la seguridad en operaciones aritméticas críticas.

---

## 💡 Idea central

> No solo puedes capturar excepciones por tipo, también puedes decidir dinámicamente si deseas manejarlas.

Y en operaciones numéricas:

> C# prioriza rendimiento por defecto; `checked` prioriza seguridad.

---

## 🔎 Desarrollo

## 🔹 Filtrar excepciones con `when`

Sintaxis general:

```csharp
catch (TipoExcepcion ex) when (condicion)
{
    // Manejo del error
}
```

La condición del `when` se evalúa **antes de que el bloque catch capture definitivamente la excepción**.

Si la condición es `false`, el runtime continúa buscando otro `catch` compatible.

---

### ✔ Ejemplo de filtrado

```csharp
try
{
    int numero = int.Parse("texto");
}
catch (Exception e) when (e.GetType() != typeof(FormatException))
{
    Console.WriteLine("Excepción genérica");
}
catch (FormatException)
{
    Console.WriteLine("Excepción específica de formato");
}
```

Aquí ocurre lo siguiente:

1. Se lanza una `FormatException`.
2. El primer `catch` la recibe como `Exception`.
3. Se evalúa el `when`.
4. Como la condición es falsa (sí es `FormatException`), no entra.
5. El runtime continúa buscando y ejecuta el `catch` específico.

Esto permite invertir el orden tradicional de captura sin romper la lógica.

---

### 🔹 ¿Cuándo usar `when`?

* Cuando necesitas lógica condicional adicional.
* Cuando el tipo no es suficiente para diferenciar el error.
* Cuando deseas filtrar por propiedades del objeto excepción.

Ejemplo más profesional:

```csharp
catch (SqlException ex) when (ex.Number == 547)
{
    Console.WriteLine("Violación de clave foránea");
}
```

Aquí no solo importa el tipo, sino el código específico del error.

---

## 🔹 Desbordamiento aritmético en C#

Por defecto, en contexto no verificado, C# **no lanza excepción por overflow en enteros**.

Ejemplo:

```csharp
int numero = int.MaxValue;
int resultado = numero + 20;

Console.WriteLine(resultado);
```

Esto produce un valor incorrecto debido a overflow (wrap-around).

El runtime asume comportamiento de bajo nivel por rendimiento.

---

## 🔹 Uso de `checked`

Para forzar la validación de desbordamiento:

```csharp
checked
{
    int numero = int.MaxValue;
    int resultado = numero + 20;
    Console.WriteLine(resultado);
}
```

En este caso:

* Se lanza una `OverflowException`.
* El error ya no pasa silenciosamente.

También puede usarse en una sola expresión:

```csharp
int resultado = checked(numero + 20);
```

---

## 🔹 Contextos importantes

* `checked` → lanza excepción si hay overflow.
* `unchecked` → ignora el overflow (comportamiento por defecto).

El compilador también puede configurarse para usar `checked` por defecto.

---

## 🧠 Buenas prácticas

1. Usa `when` cuando el tipo de excepción no sea suficiente.
2. No abuses de filtros complejos que dificulten lectura.
3. En cálculos financieros o críticos, usa `checked`.
4. No asumas que overflow lanzará excepción automáticamente.
5. Sé explícito cuando la seguridad sea más importante que el rendimiento.

---

## 🧠 20% Pareto (lo imprescindible)

Domina esto:

* `when` permite filtrar excepciones dinámicamente.
* Si la condición del `when` es falsa, el catch no se ejecuta.
* C# no lanza overflow por defecto en enteros.
* `checked` fuerza la validación y lanza `OverflowException`.
* Seguridad numérica debe ser explícita.

---

## 🤔 Reflexión (con respuestas)

**1. ¿Por qué el runtime no valida overflow por defecto?**
Por rendimiento y compatibilidad con comportamiento de bajo nivel.

**2. ¿Qué ventaja tiene usar `when` en lugar de múltiples catch complejos?**
Permite un filtrado más preciso sin duplicar bloques.

**3. ¿Qué ocurre si el `when` devuelve false?**
El runtime continúa buscando otro `catch`.

**4. ¿En qué escenarios es obligatorio usar `checked`?**
En cálculos financieros, científicos o donde la precisión sea crítica.

---

## ✍️ Resumen

El filtrado con `when` permite un manejo avanzado y flexible de excepciones.

El uso de `checked` permite detectar errores de desbordamiento que, por defecto, C# ignora por rendimiento.

Ambos mecanismos reflejan un principio clave:

El desarrollador decide entre rendimiento implícito o seguridad explícita.
