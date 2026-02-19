# Condicional `if` en C#

La condición `if` permite decidir si una parte del código se ejecuta o no, dependiendo de si se cumple una condición.

La condición debe devolver un valor de tipo `bool` (`true` o `false`).

Se puede usar con:

* Operadores de comparación (`>`, `<`, `>=`, `<=`, `==`, `!=`)
* Operadores lógicos (`&&`, `||`, `!`)
* Cualquier expresión que retorne `bool`

---

# 1️⃣ Forma básica

```csharp
int edad = 15;

Console.WriteLine("Vamos a evaluar si eres mayor de edad");

if (edad >= 18)
{
    Console.WriteLine("Eres mayor de edad");
}
```

📌 Si la condición es verdadera, se ejecuta el bloque.
Si es falsa, no se ejecuta nada.

---

# 2️⃣ `if` con `else`

```csharp
int edad = 15;

Console.WriteLine("Vamos a evaluar si eres mayor de edad");

if (edad >= 18)
{
    Console.WriteLine("Eres mayor de edad");
}
else
{
    Console.WriteLine("Eres menor de edad");
}
```

📌 `else` se ejecuta cuando la condición del `if` es falsa.

---

# 3️⃣ `if` con múltiples condiciones (`else if`)

```csharp
int edad = 15;

Console.WriteLine("Vamos a evaluar tu rango de edad");

if (edad > 80)
{
    Console.WriteLine("Eres una persona de tercera edad");
}
else if (edad >= 18)
{
    Console.WriteLine("Eres mayor de edad");
}
else
{
    Console.WriteLine("Eres menor de edad");
}
```

📌 El flujo funciona así:

* Evalúa la primera condición.
* Si es verdadera, ejecuta ese bloque y termina.
* Si es falsa, pasa a la siguiente.
* Solo se ejecuta el primer bloque verdadero que encuentre.

---

# ⚡ Optimización del orden de condiciones

En aplicaciones grandes, el orden puede afectar ligeramente el rendimiento.

Si sabemos que:

* 80% de los usuarios tienen entre 18 y 60 años
* 10% son mayores de 60
* 10% son menores de 18

Conviene evaluar primero el caso más frecuente.

---

## 🔹 Código optimizado según el caso más común

```csharp
int edad = 15;

Console.WriteLine("Vamos a evaluar tu rango de edad");

if (edad >= 18 && edad <= 60)
{
    Console.WriteLine("Eres mayor de edad");
}
else if (edad > 60)
{
    Console.WriteLine("Eres una persona mayor");
}
else
{
    Console.WriteLine("Eres menor de edad");
}
```

📌 Ahora, en el 80% de los casos, solo se hace una evaluación principal.

---

# 🧠 Nota importante sobre rendimiento

En aplicaciones pequeñas, la diferencia es prácticamente imperceptible.

Pero en sistemas de alto tráfico o algoritmos críticos, ordenar condiciones por probabilidad puede ser una buena práctica.

---

# 🎯 Resumen clave

* `if` ejecuta código solo si la condición es verdadera.
* `else` cubre el caso contrario.
* `else if` permite múltiples escenarios.
* Solo se ejecuta el primer bloque verdadero.
* Ordenar condiciones por probabilidad puede mejorar rendimiento en sistemas grandes.