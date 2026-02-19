# Bucles en C#

## 📋 Descripción

Los **bucles** (loops) son estructuras de control que permiten **repetir la ejecución de un bloque de código** mientras se cumpla una determinada condición.

Son fundamentales en programación porque permiten:

* Procesar colecciones de datos.
* Ejecutar tareas repetitivas.
* Controlar flujos dinámicos.
* Automatizar operaciones.

En C#, los bucles se dividen conceptualmente en:

* **Determinados**
* **Indeterminados**

Esta clasificación depende de si conocemos o no la cantidad de iteraciones antes de ejecutar el ciclo.

---

## 🎯 Problema que resuelve

Sin bucles:

* Tendríamos que repetir manualmente el mismo código.
* El software sería rígido y poco escalable.
* No podríamos procesar listas, arreglos o flujos dinámicos de datos.

Los bucles permiten que el código sea:

* Flexible
* Dinámico
* Escalable

---

## 💡 Idea central

> Un bucle es una estructura que ejecuta código repetidamente hasta que se cumple una condición de salida.

El control de esa condición define el tipo de bucle.

---

## 🔎 Desarrollo

## 🔹 Bucles determinados

Son aquellos donde **conocemos o podemos calcular previamente la cantidad de iteraciones**.

Normalmente dependen de:

* Un contador
* El tamaño de una colección
* Un rango numérico

### ✔ `for`

Se utiliza cuando sabemos exactamente cuántas veces debe ejecutarse el bloque.

```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine("Iteración: " + i);
}
```

Estructura:

```csharp
for (inicialización; condición; incremento)
```

Flujo:

1. Se ejecuta la inicialización.
2. Se evalúa la condición.
3. Si es verdadera, se ejecuta el bloque.
4. Se ejecuta el incremento.
5. Se repite el proceso.

Es ideal cuando trabajamos con índices.

---

### ✔ `foreach`

Se usa para recorrer colecciones sin manejar manualmente un índice.

```csharp
int[] numeros = { 1, 2, 3, 4 };

foreach (int numero in numeros)
{
    Console.WriteLine(numero);
}
```

Características:

* Más legible.
* No requiere control manual del contador.
* No permite modificar fácilmente la colección durante la iteración.

Es preferible cuando solo necesitas recorrer datos.

---

## 🔹 Bucles indeterminados

Son aquellos donde **no sabemos cuántas veces se repetirá el código** antes de iniciar la ejecución.

Generalmente dependen de:

* Entrada del usuario
* Eventos
* Condiciones dinámicas

---

### ✔ `while`

Se ejecuta **mientras la condición sea verdadera**.

```csharp
bool condicion = true;

while (condicion)
{
    Console.WriteLine("Se ingresó en el bucle");
    condicion = false;
}
```

Flujo:

1. Se evalúa la condición.
2. Si es verdadera, se ejecuta el bloque.
3. Se vuelve a evaluar.
4. Termina cuando la condición es falsa.

Si la condición nunca cambia, se genera un **bucle infinito**.

---

### ✔ `do while`

La diferencia clave es que **siempre se ejecuta al menos una vez**, porque la condición se evalúa al final.

```csharp
bool condicion = true;

do
{
    Console.WriteLine("Se ingresó en el bucle");
    condicion = false;
}
while (condicion);
```

Uso típico:

* Menús interactivos.
* Validaciones donde el código debe ejecutarse al menos una vez.

---

## 🔹 Diferencia conceptual importante

| Tipo     | ¿Cuándo se evalúa la condición? | ¿Puede no ejecutarse nunca? |
| -------- | ------------------------------- | --------------------------- |
| while    | Antes del bloque                | Sí                          |
| do while | Después del bloque              | No                          |

---

## 🧠 Buenas prácticas

1. Asegúrate de que la condición de salida cambie.
2. Evita bucles infinitos no intencionales.
3. Usa `foreach` cuando solo necesites recorrer una colección.
4. Usa `for` cuando necesites controlar el índice.
5. Mantén el bloque del bucle lo más simple posible.
6. Evita lógica compleja que dificulte entender la condición.

---

## 🧠 20% Pareto (lo imprescindible)

Domina esto:

* `for` → cuando conoces el número de iteraciones.
* `foreach` → cuando recorres colecciones.
* `while` → cuando depende de una condición dinámica.
* `do while` → cuando debe ejecutarse al menos una vez.
* Siempre debe existir una condición clara de salida.

---

## 🤔 Reflexión (con respuestas)

**1. ¿Cuándo es mejor usar foreach en lugar de for?**
Cuando solo necesitas recorrer elementos sin usar el índice.

**2. ¿Qué error causa más problemas en bucles?**
No actualizar la condición de salida, generando bucles infinitos.

**3. ¿Por qué do while garantiza al menos una ejecución?**
Porque evalúa la condición al final.

**4. ¿Un bucle determinado siempre tiene número fijo?**
No necesariamente fijo, pero sí calculable antes de ejecutarse.

---

## ✍️ Resumen

Los bucles permiten repetir código de forma controlada.

* Usa `for` cuando controles iteraciones.
* Usa `foreach` para recorrer colecciones.
* Usa `while` cuando dependa de condiciones dinámicas.
* Usa `do while` cuando necesites al menos una ejecución.

El dominio de los bucles es clave para escribir código dinámico, eficiente y estructurado.
