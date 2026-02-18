# 🧭 Guía: ¿Qué es el código auto-documentado?

## 🎯 Objetivo

Comprender qué es el **código auto-documentado**, por qué es importante y cómo aplicarlo correctamente en proyectos desarrollados con **C#**.

---

## 🛠️ Requisitos o herramientas necesarias

* [ ] Conocimientos básicos de C#
* [ ] Entender qué son los comentarios en código
* [ ] Buenas prácticas básicas de programación

---

## 📋 ¿Qué es el código auto-documentado?

El **código auto-documentado** es aquel que se entiende por sí mismo, sin necesidad de comentarios adicionales.

Es decir:

> El código está escrito de forma tan clara que explica su intención a través de nombres bien elegidos y estructura limpia.

---

## ❌ Ejemplo de código poco claro

```csharp
int x = 5;
int y = 10;
int z = x * y;
```

Aquí no sabemos:

* Qué representa `x`
* Qué representa `y`
* Qué significa `z`

---

## ✅ Ejemplo de código auto-documentado

```csharp
int cantidadProductos = 5;
int precioUnitario = 10;
int totalCompra = cantidadProductos * precioUnitario;
```

Ahora es evidente:

* Qué representa cada variable
* Qué se está calculando
* Cuál es la intención del código

Sin necesidad de comentarios.

---

## 📌 Principios del código auto-documentado

### 🔹 Nombres descriptivos

```csharp
CalcularTotalFactura()
```

Es mejor que:

```csharp
Calcular()
```

---

### 🔹 Métodos pequeños y claros

Cada método debería hacer **una sola cosa**.

---

### 🔹 Evitar abreviaciones innecesarias

```csharp
numeroEstudiantes
```

En lugar de:

```csharp
numEst
```

---

### 🔹 Estructura clara

* Separar responsabilidades
* Usar espacios adecuados
* Mantener orden lógico

---

## 💡 Idea clave

Un buen código reduce la necesidad de comentarios.
Si necesitas explicar demasiado lo que hace, probablemente el código puede mejorarse.

---

## 🧠 Código auto-documentado vs comentarios

Los comentarios deben explicar:

* El **por qué**
* Decisiones complejas
* Casos especiales

El código debe explicar:

* El **qué**
* El **cómo**

---

## 🧠 Ventajas

* Mayor mantenibilidad
* Más fácil de leer en equipo
* Menos errores
* Más fácil de refactorizar

---

## ⚠️ Error común

Pensar que escribir muchos comentarios significa escribir mejor código.

No es así.

Código claro > Código comentado en exceso.

---

## 🤔 Reflexión

El código se lee muchas más veces de las que se escribe.
Escribirlo pensando en el "yo del futuro" es una inversión profesional.

---

## ✍️ Resumen

🔹 El código auto-documentado se entiende por sí mismo.
🔹 Usa nombres claros y estructura limpia.
🔹 Reduce la necesidad de comentarios innecesarios.
🔹 Mejora la calidad y mantenibilidad del software.