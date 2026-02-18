# Conversión de número a texto en C#

## 📋 Descripción

En C#, para convertir un **número a texto (string)** no se utiliza `Parse()`.
`Parse()` se usa para convertir **texto a número**, no al revés.

Para convertir un número a string se utilizan otros métodos como:

* `ToString()`
* interpolación de cadenas
* `Convert.ToString()`

---

## 🎯 Problema que resuelve

Muchas veces necesitamos:

* mostrar números en pantalla
* concatenarlos en mensajes
* guardarlos en archivos
* enviarlos como texto en una API

Pero los números (`int`, `double`, `decimal`, etc.) no son texto.

Necesitamos convertirlos.

---

## 💡 Idea central

> Para convertir un número a texto se usa `ToString()`.

No existe algo como `int.Parse()` al revés.

El flujo correcto es:

* Texto → Número → `Parse()`
* Número → Texto → `ToString()`

---

# 🔹 Método `ToString()`

Es el método más común.

```csharp
int edad = 25;
string edadTexto = edad.ToString();

Console.WriteLine(edadTexto);
```

Funciona con cualquier tipo numérico:

* `int`
* `double`
* `decimal`
* `long`

---

# 🔹 Interpolación de cadenas

En realidad, cuando usas interpolación, C# internamente llama a `ToString()`.

```csharp
int edad = 25;
string mensaje = $"Tienes {edad} años";
```

Aquí no necesitas convertir manualmente.

Es la forma más limpia en la mayoría de casos.

---

# 🔹 Convert.ToString()

Otra opción es usar la clase `Convert`.

```csharp
int numero = 100;
string texto = Convert.ToString(numero);
```

Se usa menos que `ToString()`, pero es válida.

---

# 🎨 Formateo con `ToString()`

`ToString()` permite formatear números.

Ejemplo con decimales:

```csharp
double precio = 19.5;
string precioTexto = precio.ToString("F2"); // 19.50
```

Ejemplo con moneda:

```csharp
decimal total = 199.99m;
string totalTexto = total.ToString("C");
```

Esto es muy útil en aplicaciones reales.

---

## 🧠 20% Pareto (lo imprescindible)

Si entiendes esto, entiendes la conversión número → texto:

* No se usa `Parse()`
* Se usa `ToString()`
* La interpolación lo hace automáticamente
* Se puede aplicar formato

En la práctica profesional usarás:

👉 Interpolación
👉 `ToString()` con formato

---

## 🤔 Reflexión (con respuestas)

**¿Por qué no existe algo como `string.Parse(int)`?**
Porque `Parse()` convierte desde string hacia otro tipo.

**¿Qué método se usa normalmente para convertir número a texto?**
`ToString()`.

**¿La interpolación convierte automáticamente?**
Sí, internamente usa `ToString()`.

**¿Cuándo usar formato en ToString()?**
Cuando necesitas controlar decimales, moneda, porcentaje, etc.

---

## ✍️ Resumen

🔁 Para convertir números a texto en C#:

* Usa `ToString()`
* Usa interpolación si estás construyendo mensajes
* Usa formato cuando necesites presentación específica

Recuerda:

👉 `Parse()` convierte texto a número
👉 `ToString()` convierte número a texto

Son operaciones inversas.
