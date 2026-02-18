# Constantes en C#

## 📋 Descripción

Una **constante** es una variable cuyo valor **no puede cambiar** después de ser definido.

En C# se declaran usando la palabra clave:

```csharp
const
```

Ejemplo:

```csharp
const double PI = 3.1416;
```

Una vez asignado el valor, no puede modificarse.

---

## 🎯 Problema que resuelven

En muchos programas existen valores que:

* no deben cambiar
* representan reglas del negocio
* son configuraciones fijas
* son valores universales

Si esos valores se escriben “a mano” varias veces:

* es fácil cometer errores
* es difícil mantener el código
* un cambio obliga a buscar en todo el proyecto

Las constantes evitan este problema.

---

## 💡 Idea central

> Una constante protege un valor que no debe cambiar.

Además:

* mejora la claridad del código
* evita errores accidentales
* comunica intención

---

# 🔒 Declaración de constantes

```csharp
const int EDAD_MINIMA = 18;
```

Reglas importantes:

* Deben inicializarse al declararse.
* No pueden cambiar después.
* Solo pueden almacenar valores conocidos en tiempo de compilación.

---

# 📌 `const` vs `readonly`

En C# también existe `readonly`.

Ejemplo:

```csharp
readonly int edadMinima;
```

Diferencia clave:

| `const`                               | `readonly`                     |
| ------------------------------------- | ------------------------------ |
| Se fija en compilación                | Se fija en ejecución           |
| Es implícitamente estática            | Puede depender del constructor |
| Solo valores conocidos en compilación | Puede calcularse dinámicamente |

Ejemplo con `readonly`:

```csharp
class Persona
{
    readonly DateTime fechaCreacion = DateTime.Now;
}
```

Esto no sería posible con `const`.

---

# 🧠 Buenas prácticas con constantes

---

## 1️⃣ Usar constantes para valores que no cambian

✔️ Límites
✔️ Tasas fijas
✔️ Mensajes constantes
✔️ Configuraciones internas

Ejemplo:

```csharp
const int MAX_INTENTOS = 3;
```

---

## 2️⃣ Evitar “números mágicos”

❌ Malo:

```csharp
if (edad >= 18)
```

✔️ Mejor:

```csharp
const int EDAD_MINIMA = 18;

if (edad >= EDAD_MINIMA)
```

Esto mejora la legibilidad y mantenimiento.

---

## 3️⃣ Nombrarlas en MAYÚSCULAS

Convención común:

```csharp
const double IVA = 0.19;
```

Esto permite identificarlas rápidamente.

---

## 4️⃣ No abusar de `const`

No todo debe ser constante.

Si el valor puede cambiar en el futuro (por configuración o negocio), mejor:

* usar configuración externa
* usar `readonly`
* usar variables normales

---

## 5️⃣ Agrupar constantes relacionadas

Se pueden organizar dentro de clases estáticas:

```csharp
public static class Configuracion
{
    public const int MAX_USUARIOS = 100;
    public const int EDAD_MINIMA = 18;
}
```

Esto mejora la organización.

---

## 🧠 20% Pareto (lo imprescindible)

Si entiendes esto, entiendes constantes:

* `const` → valor fijo en compilación
* Evitan números mágicos
* Mejoran claridad
* No deben usarse para valores que pueden cambiar

En código profesional:

👉 Usa constantes para reglas inmutables
👉 Usa configuración para valores variables

---

## 🤔 Reflexión (con respuestas)

**¿Por qué evitar números mágicos?**
Porque reducen la claridad y dificultan mantenimiento.

**¿Cuándo usar readonly en lugar de const?**
Cuando el valor depende de ejecución o del constructor.

**¿Las constantes pueden cambiar?**
No. Nunca después de declararse.

**¿Qué comunica una constante en el diseño?**
Que ese valor es parte fija del sistema.

---

## ✍️ Resumen

🔒 Las **constantes** permiten proteger valores que no deben cambiar.

Son una herramienta clave para:

* claridad
* seguridad
* mantenimiento

Usarlas correctamente mejora la calidad del código y comunica intención de diseño.