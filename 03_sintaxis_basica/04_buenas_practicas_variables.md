# 🧭 Guía: Buenas prácticas para nombrar variables en C#

## 🎯 Objetivo

Aprender a nombrar variables correctamente en **C#** para mejorar la legibilidad, mantenibilidad y calidad del código.

---

## 🛠️ Requisitos o herramientas necesarias

* [ ] Conocimientos básicos de C#
* [ ] Entender qué es una variable

---

## 📋 Reglas y buenas prácticas

### 🔹 1️⃣ No comenzar con guion bajo `_`

En C#, el guion bajo suele reservarse para **campos privados** dentro de una clase.

❌ Incorrecto:

```csharp
int _edad = 25;
```

✅ Correcto:

```csharp
int edad = 25;
```

---

### 🔹 2️⃣ No crear variables que solo se diferencien por una letra

Esto genera confusión y errores difíciles de detectar.

❌ Incorrecto:

```csharp
int total;
int total2;
int totall;
```

✅ Correcto:

```csharp
int totalVentas;
int totalImpuestos;
```

---

### 🔹 3️⃣ Comenzar con letra minúscula

Las variables locales deben comenzar con minúscula.

❌ Incorrecto:

```csharp
int Edad = 25;
```

✅ Correcto:

```csharp
int edad = 25;
```

---

### 🔹 4️⃣ Usar CamelCase para múltiples palabras

Si el nombre tiene más de una palabra, la segunda comienza con mayúscula.

❌ Incorrecto:

```csharp
int total_ventas;
int totalventas;
```

✅ Correcto (CamelCase):

```csharp
int totalVentas;
```

---

### 🔹 5️⃣ No usar notación húngara

La notación húngara antepone el tipo al nombre.

❌ Incorrecto:

```csharp
int iEdad;
string strNombre;
bool bActivo;
```

En C#, el tipo ya está declarado antes.

✅ Correcto:

```csharp
int edad;
string nombre;
bool activo;
```

---

### 🔹 6️⃣ Usar nombres descriptivos

Evita nombres genéricos como:

❌ Incorrecto:

```csharp
int x;
int dato;
```

✅ Correcto:

```csharp
int cantidadProductos;
int edadUsuario;
```

---

### 🔹 7️⃣ Evitar abreviaciones innecesarias

❌ Incorrecto:

```csharp
int numEst;
```

✅ Correcto:

```csharp
int numeroEstudiantes;
```

Solo usa abreviaciones si son universalmente conocidas (ej. `id`, `url`).

---

### 🔹 8️⃣ No usar palabras reservadas

C# no permite usar palabras clave como nombres de variables.

❌ Incorrecto:

```csharp
int class = 5;
```

---

### 🔹 9️⃣ Que el nombre refleje intención

El nombre debe indicar claramente el propósito.

❌ Poco claro:

```csharp
bool flag;
```

✅ Mejor:

```csharp
bool usuarioAutenticado;
```

---

## 💡 Idea clave

Una variable bien nombrada reduce la necesidad de comentarios y mejora la comprensión inmediata del código.

---

## 🧠 Convención general en C#

* Variables → `camelCase`
* Propiedades → `PascalCase`
* Clases → `PascalCase`
* Campos privados → `_camelCase`

---

## 🤔 Reflexión

El código se lee más de lo que se escribe.
Un mal nombre puede generar más errores que una mala lógica.

---

## ✍️ Resumen

🔹 Usa nombres descriptivos.
🔹 Aplica camelCase en variables.
🔹 No uses notación húngara.
🔹 Evita abreviaciones confusas.
🔹 Nombra según intención, no según tipo.