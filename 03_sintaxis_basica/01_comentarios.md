# 🧭 Guía: Comentarios en C#

## 🎯 Objetivo

Comprender qué son los **comentarios en C#**, para qué se utilizan y cómo aplicar convenciones estándar para mejorar la mantenibilidad del código.

---

## 🛠️ Requisitos o herramientas necesarias

* [ ] SDK de .NET instalado
* [ ] Conocimientos básicos de C#

---

## 📋 ¿Qué son los comentarios?

Los comentarios sirven para:

* Describir una parte del código
* Explicar decisiones técnicas
* Dejar recordatorios
* Advertir sobre comportamientos importantes

⚠️ El compilador ignora los comentarios.
No afectan la ejecución del programa.

---

## 📝 Tipos de comentarios en C#

### 🔹 Comentario de una sola línea

Se utiliza `//`

```csharp
// Comentario de una línea
```

Ideal para explicaciones cortas o anotaciones rápidas.

---

### 🔹 Comentario de varias líneas

Se utiliza `/* */`

```csharp
/*

****
Comentario de varias líneas
****
    
*/
```

Se usa cuando se necesita escribir una explicación más extensa.

---

## 📌 Convenciones importantes en comentarios

Existen palabras clave estándar que permiten identificar rápidamente tareas pendientes, errores o advertencias dentro del código.

Estas convenciones son reconocidas por muchos IDEs y herramientas.

---

### 🔹 `TODO`

Se usa cuando hay algo pendiente por implementar.

```csharp
// TODO: Añadir soporte para múltiples idiomas
```

---

### 🔹 `FIXME`

Se usa cuando hay algo que debe corregirse.

```csharp
// FIXME: Corregir cálculo de impuestos
```

---

### 🔹 `HACK`

Se usa cuando se implementa una solución temporal o poco elegante.

```csharp
// HACK: Solución temporal hasta migrar la base de datos
```

---

### 🔹 `BUG`

Se usa para señalar un error conocido.

```csharp
// BUG: Falla cuando el usuario no tiene permisos
```

---

### 🔹 `NOTE`

Se usa para dejar una aclaración importante.

```csharp
// NOTE: Este método se ejecuta antes de validar los datos
```

---

### 🔹 `OPTIMIZE`

Se usa cuando el código funciona, pero puede mejorarse en rendimiento.

```csharp
// OPTIMIZE: Reducir consultas innecesarias a la base de datos
```

---

### 🔹 `DEPRECATED`

Se usa para indicar que algo quedará obsoleto.

```csharp
// DEPRECATED: Esta función será eliminada en la próxima versión
```

---

### 🔹 `SECURITY`

Se usa cuando existe un punto crítico relacionado con seguridad.

```csharp
// SECURITY: Asegurar que las contraseñas se cifren antes de almacenarlas
```

---

## 💡 Idea clave

Los comentarios no son para explicar lo obvio, sino para explicar **el por qué**, no el qué.

---

## 🧠 Buenas prácticas

* No abuses de comentarios innecesarios.
* Mantén los comentarios actualizados.
* Prefiere código claro antes que comentarios extensos.
* Usa convenciones como `TODO` y `FIXME` para facilitar búsquedas.

---

## 🤔 Reflexión

Un buen comentario puede ahorrar horas de análisis en el futuro.
Un mal comentario puede generar más confusión que ayuda.

---

## ✍️ Resumen

🔹 Los comentarios documentan el código.
🔹 No afectan la ejecución.
🔹 Existen de una línea y múltiples líneas.
🔹 Las convenciones (`TODO`, `FIXME`, etc.) ayudan a mantener orden y calidad.


