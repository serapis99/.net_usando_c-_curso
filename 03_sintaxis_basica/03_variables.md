# 🧭 Guía: Variables y tipos de datos en C#

## 🎯 Objetivo

Comprender qué es una **variable**, qué tipos de datos existen en C# y cuál es la diferencia entre **tipos por valor** y **tipos por referencia**.

---

## 🛠️ Requisitos o herramientas necesarias

* [ ] SDK de .NET instalado
* [ ] Conocimientos básicos de C#

---

## 📋 ¿Qué es una variable?

Una variable es un **espacio de memoria reservado** que nos permite almacenar información para usarla posteriormente en el programa.

Ejemplo:

```csharp
int edad = 25;
```

Aquí:

* `int` → tipo de dato
* `edad` → nombre de la variable
* `25` → valor almacenado

---

# 📦 Tipos de datos en C#

En C# existen dos grandes categorías:

1. **Tipos por valor**
2. **Tipos por referencia**

---

# 🔹 1️⃣ Tipos por valor

Son variables que almacenan **directamente su valor en memoria**.

Cuando se copian, se copia el valor completo.

---

## 🧮 Tipos primitivos (numéricos)

### 🔸 Enteros con signo

| Tipo    | Rango                                                  | Tamaño  |
| ------- | ------------------------------------------------------ | ------- |
| `sbyte` | -128 a 127                                             | 1 byte  |
| `short` | -32,768 a 32,767                                       | 2 bytes |
| `int`   | -2,147,483,648 a 2,147,483,647                         | 4 bytes |
| `long`  | -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807 | 8 bytes |

---

### 🔸 Enteros sin signo

| Tipo     | Rango                          | Tamaño  |
| -------- | ------------------------------ | ------- |
| `byte`   | 0 a 255                        | 1 byte  |
| `ushort` | 0 a 65,535                     | 2 bytes |
| `uint`   | 0 a 4,294,967,295              | 4 bytes |
| `ulong`  | 0 a 18,446,744,073,709,551,615 | 8 bytes |

---

### 🔸 Números reales

| Tipo      | Precisión                                 | Tamaño   |
| --------- | ----------------------------------------- | -------- |
| `float`   | ~7 dígitos                                | 4 bytes  |
| `double`  | ~15-16 dígitos                            | 8 bytes  |
| `decimal` | 28-29 dígitos (alta precisión financiera) | 16 bytes |

---

### 🔸 Booleanos

| Tipo   | Valores          | Tamaño |
| ------ | ---------------- | ------ |
| `bool` | `true` / `false` | 1 byte |

---

## ❓ ¿Qué es `Int32` y `Int64`?

Son los nombres estructurales dentro del namespace `System`.

Equivalencias:

```csharp
int      == System.Int32
long     == System.Int64
short    == System.Int16
byte     == System.Byte
```

Es decir:

* `int` es simplemente un alias de `System.Int32`
* `long` es alias de `System.Int64`

---

## 🏗️ Otros tipos por valor

### 🔹 Estructuras (`struct`)

Son tipos definidos por el usuario que también se almacenan por valor.

Ejemplo:

```csharp
struct Punto
{
    public int X;
    public int Y;
}
```

---

### 🔹 Enumerados (`enum`)

Permiten definir un conjunto fijo de constantes.

```csharp
enum DiaSemana
{
    Lunes,
    Martes,
    Miercoles
}
```

Internamente almacenan valores enteros.

---

# 🔹 2️⃣ Tipos por referencia

Son variables que **no almacenan el valor directamente**, sino una referencia (dirección de memoria) hacia donde está el objeto real.

Cuando se copian, se copia la referencia, no el objeto.

Ejemplo:

```csharp
class Persona
{
    public string Nombre;
}
```

```csharp
Persona p1 = new Persona();
Persona p2 = p1;
```

Aquí:

* `p1` y `p2` apuntan al mismo objeto en memoria.
* Si modificas uno, el otro también cambia.

---

## 📌 Ejemplos de tipos por referencia

* `class`
* `string`
* `array`
* `object`
* `interface`
* `delegate`
* `char`

---

## 💡 Idea clave

Tipos por valor → Copian el valor.
Tipos por referencia → Copian la dirección de memoria.

---

## 🧠 Diferencia visual simplificada

### Por valor

```
A = 5
B = A
```

B tiene su propia copia → No se afectan entre sí.

---

### Por referencia

```
A → [Objeto]
B → [Objeto]
```

Ambos apuntan al mismo objeto → Se afectan entre sí.

---

## 🤔 Reflexión

Entender la diferencia entre valor y referencia es fundamental para evitar errores de lógica, especialmente en aplicaciones grandes.

---

## ✍️ Resumen

🔹 Una variable es un espacio en memoria para guardar datos.
🔹 Existen tipos por valor y por referencia.
🔹 `int` es alias de `System.Int32`.
🔹 Las clases son por referencia, las estructuras son por valor.