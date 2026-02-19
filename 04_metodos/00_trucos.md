# Trucos y Buenas Prácticas en C#

## 🔹 1️⃣ División entre enteros

En C#, cuando se divide **dos enteros (`int`)**, el resultado también será un entero.

```csharp
int a = 5;
int b = 2;

Console.WriteLine(a / b); // Resultado: 2
```

📌 Aunque matemáticamente sería `2.5`, el resultado es `2` porque se descarta la parte decimal.

---

### ✅ ¿Cómo obtener decimales?

Al menos uno de los valores debe ser `double` (o convertirlo).

```csharp
int a = 5;
int b = 2;

Console.WriteLine((double)a / b); // Resultado: 2.5
```

O directamente:

```csharp
Console.WriteLine(5.0 / 2); // 2.5
```

🧠 Regla práctica:

> Si ambos operandos son enteros, el resultado será entero.

---

## 🔹 2️⃣ Métodos demasiado largos

Si un método ocupa más de una pantalla completa o realiza muchas tareas, es muy probable que necesite ser **modularizado**.

### 📌 Señales de alerta:

* Hace más de una responsabilidad.
* Tiene demasiadas variables locales.
* Es difícil de leer o entender.
* Tiene muchos `if` o `switch` anidados.

### ✔ Solución:

Dividirlo en métodos más pequeños y especializados.

Esto mejora:

* Legibilidad
* Reutilización
* Mantenimiento
* Testeo

🧠 Regla práctica:

> Un método debería hacer una sola cosa y hacerla bien.

---

## 🔹 3️⃣ Métodos compactos (Expression-bodied members)

Si un método solo tiene una línea de código o un `return` inmediato, puede escribirse de forma más compacta usando `=>`.

### 🔹 Forma tradicional

```csharp
static double DivideNumeros(double num1, int num2)
{
    return num1 / num2;
}
```

### 🔹 Forma compacta

```csharp
static double DivideNumeros(double num1, int num2) => num1 / num2;
```

✔ Más limpio
✔ Más corto
✔ Ideal para métodos simples

---

## 🎯 Resumen rápido

* La división de enteros devuelve entero.
* Convierte a `double` si necesitas decimales.
* Si un método es muy largo, probablemente necesita dividirse.
* Usa `=>` cuando el método tenga una sola expresión.