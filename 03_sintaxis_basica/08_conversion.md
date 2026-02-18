# Declaraciones y conversiones en C#

## 📋 Descripción

En C# existen distintas formas de **declarar variables** y también distintas maneras de **convertir tipos de datos**.

Estos conceptos son fundamentales porque:

* determinan cómo se almacenan los datos
* afectan el comportamiento del programa
* influyen en la seguridad de tipos

En C# podemos encontrar:

* Declaraciones explícitas
* Declaraciones implícitas
* Conversiones implícitas
* Conversiones explícitas (casting)

---

## 🎯 Problema que resuelven

Los datos no siempre están en el tipo que necesitamos.

Por ejemplo:

* un número entero puede necesitar convertirse en decimal
* un decimal puede necesitar convertirse en entero
* puede que no sepamos el tipo exacto al declarar una variable

Las declaraciones y conversiones permiten:

* mayor flexibilidad
* reutilización de datos
* compatibilidad entre tipos

---

## 💡 Idea central

> C# es un lenguaje fuertemente tipado, pero permite inferencia de tipos y conversiones controladas.

El compilador siempre debe saber qué tipo tiene una variable, incluso cuando usamos `var`.

---

# 📝 Declaraciones en C#

---

## 🔹 Declaración explícita

Es cuando indicamos directamente el tipo de dato.

```csharp
int edad = 27;
double temperatura = 34.5;
```

Aquí el tipo es definido manualmente por el desarrollador.

---

## 🔹 Declaración implícita (uso de `var`)

Es cuando dejamos que el compilador infiera el tipo.

```csharp
var edadPersona4 = 27;
Console.WriteLine(edadPersona4);
```

Aunque usamos `var`, el tipo sigue siendo `int`.
El tipo se determina en tiempo de compilación y no puede cambiar después.

✔️ Hace el código más limpio
✔️ Útil cuando el tipo es evidente

---

## 🔹 Asignación múltiple

En C# se puede asignar el mismo valor a múltiples variables:

```csharp
int edadPersona1;
int edadPersona2;
int edadPersona3;
int edadPersona4;

edadPersona1 = edadPersona2 = edadPersona3 = edadPersona4 = 37;
```

También se puede declarar en una sola línea:

```csharp
int edadPersona1, edadPersona2, edadPersona3, edadPersona4 = 27;
Console.WriteLine(edadPersona4);
```

⚠️ En este caso **solo `edadPersona4` tiene valor asignado**, las demás variables quedan sin inicializar.

---

# 🔄 Conversiones en C#

---

## 🔹 Conversión implícita

Ocurre automáticamente cuando no hay riesgo de pérdida de información.

Ejemplo:

```csharp
int habitantesCiudad = 1000000;
long habitantesCiudad2018 = habitantesCiudad;
Console.WriteLine(habitantesCiudad2018);
```

Aquí no hay pérdida de datos porque `long` puede almacenar valores más grandes que `int`.

✔️ No requiere casting
✔️ Es segura

---

## 🔹 Conversión explícita (Casting)

Se usa cuando puede haber pérdida de información.

Ejemplo:

```csharp
double temperatura = 34.5;
int temperaturaColombia;
temperaturaColombia = (int) temperatura;
Console.WriteLine(temperaturaColombia);
```

Aquí se pierde la parte decimal (`.5`).

✔️ Se debe indicar manualmente
✔️ Puede provocar pérdida de precisión

---

## 🧠 20% Pareto (lo imprescindible)

Si entiendes esto, entiendes declaraciones y conversiones:

* `var` no significa tipo dinámico, solo inferido
* Las conversiones implícitas son seguras
* Las conversiones explícitas pueden perder información
* C# siempre mantiene control de tipos

---

## 🤔 Reflexión (con respuestas)

**¿`var` convierte a C# en un lenguaje dinámico?**
No. El tipo se determina en compilación y no puede cambiar.

**¿Cuándo ocurre una conversión implícita?**
Cuando no existe riesgo de pérdida de datos.

**¿Por qué el casting puede ser peligroso?**
Porque puede truncar o alterar el valor original.

**¿Qué pasa si intento convertir un tipo incompatible sin casting?**
El compilador generará un error.

---

## ✍️ Resumen

🧩 En C#, toda variable tiene un tipo definido, aunque usemos `var`.

Las conversiones permiten adaptar datos entre distintos tipos:

* Implícitas → seguras y automáticas
* Explícitas → requieren casting y pueden perder información

Comprender esto es clave para evitar errores silenciosos y comportamientos inesperados.