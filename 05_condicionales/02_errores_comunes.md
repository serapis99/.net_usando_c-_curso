# Errores Comunes al Usar Condiciones en C#

Las estructuras condicionales (`if`, `else`, `switch`) son fundamentales en C#, pero es muy común cometer errores que pueden generar comportamientos inesperados.

A continuación, los errores más frecuentes y cómo evitarlos.

---

# 1️⃣ Usar `=` en lugar de `==`

❌ Error común:

```csharp
int edad = 18;

if (edad = 18)  // ❌ Error
{
    Console.WriteLine("Tienes 18 años");
}
```

📌 `=` es operador de asignación.
📌 `==` es operador de comparación.

✔ Correcto:

```csharp
if (edad == 18)
{
    Console.WriteLine("Tienes 18 años");
}
```

---

# 2️⃣ No usar llaves `{ }`

Aunque C# permite omitir llaves cuando solo hay una línea, puede causar errores visuales.

❌ Peligroso:

```csharp
if (edad >= 18)
    Console.WriteLine("Mayor de edad");
    Console.WriteLine("Acceso permitido"); // ❌ Siempre se ejecuta
```

✔ Correcto:

```csharp
if (edad >= 18)
{
    Console.WriteLine("Mayor de edad");
    Console.WriteLine("Acceso permitido");
}
```

📌 Buena práctica: siempre usar llaves.

---

# 3️⃣ Condiciones mal ordenadas

❌ Ejemplo problemático:

```csharp
if (edad >= 18)
{
    Console.WriteLine("Mayor de edad");
}
else if (edad >= 60)
{
    Console.WriteLine("Adulto mayor");
}
```

📌 El segundo bloque nunca se ejecutará porque si alguien tiene 60, ya cumple `>= 18`.

✔ Correcto:

```csharp
if (edad >= 60)
{
    Console.WriteLine("Adulto mayor");
}
else if (edad >= 18)
{
    Console.WriteLine("Mayor de edad");
}
```

🧠 Regla: evalúa primero las condiciones más específicas.

---

# 4️⃣ Comparaciones redundantes

❌ Innecesario:

```csharp
if (esActivo == true)
{
    Console.WriteLine("Activo");
}
```

✔ Mejor:

```csharp
if (esActivo)
{
    Console.WriteLine("Activo");
}
```

Y para negar:

```csharp
if (!esActivo)
{
    Console.WriteLine("Inactivo");
}
```

---

# 5️⃣ Confundir `&&` con `||`

`&&` → AND → Ambas condiciones deben cumplirse
`||` → OR → Solo una debe cumplirse

❌ Error lógico:

```csharp
if (edad >= 18 || edad <= 60)
```

📌 Esta condición casi siempre será verdadera.

✔ Correcto:

```csharp
if (edad >= 18 && edad <= 60)
```

---

# 6️⃣ Comparar `double` directamente

Los números decimales pueden tener pequeñas imprecisiones.

❌ Problemático:

```csharp
double numero = 0.1 + 0.2;

if (numero == 0.3)  // Puede fallar
{
    Console.WriteLine("Es 0.3");
}
```

✔ Mejor usar tolerancia:

```csharp
if (Math.Abs(numero - 0.3) < 0.0001)
{
    Console.WriteLine("Es aproximadamente 0.3");
}
```

---

# 7️⃣ Condiciones demasiado complejas

❌ Difícil de leer:

```csharp
if ((edad > 18 && edad < 60 && activo == true) || admin == true && puntos > 100)
```

✔ Mejor dividir:

```csharp
bool esAdultoActivo = edad > 18 && edad < 60 && activo;
bool tienePermisoEspecial = admin && puntos > 100;

if (esAdultoActivo || tienePermisoEspecial)
{
    Console.WriteLine("Acceso permitido");
}
```

📌 Mejora la legibilidad y mantenimiento.

---

# 🎯 Resumen clave

Errores más comunes:

* Usar `=` en vez de `==`
* No usar llaves
* Ordenar mal condiciones
* Confundir `&&` con `||`
* Comparar `double` directamente
* Crear condiciones demasiado largas

---

# 🧠 Regla de oro

> Si una condición es difícil de leer, probablemente necesita simplificarse.