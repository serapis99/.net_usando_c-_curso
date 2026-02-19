# Parámetros Opcionales en C#

## 📌 ¿Qué son?

Los **parámetros opcionales** son aquellos que no es obligatorio enviar al llamar un método, porque ya tienen un valor asignado por defecto.

Permiten mayor flexibilidad al invocar el método.

---

## ✅ Reglas importantes

1. Los parámetros opcionales **deben ir al final** de la lista de parámetros.
2. Deben tener un **valor por defecto asignado** en la declaración del método.
3. El valor por defecto debe ser una **constante en tiempo de compilación**.

---

## 🧩 Sintaxis

```csharp
tipoRetorno NombreMetodo(tipo1 param1, tipo2 param2, tipo3 param3 = valorDefecto)
{
    // código
}
```

---

## 🔹 Ejemplo básico

```csharp
static double Suma(double num1, double num2, double num3 = 0)
{
    return num1 + num2 + num3;
}
```

### Llamadas válidas:

```csharp
Suma(8.2, 8.9, 9);   // Usa los 3 parámetros
Suma(8.2, 8.9);      // Usa el valor por defecto (num3 = 0)
```

📌 Si no se envía `num3`, automáticamente toma el valor `0`.

---

# ⚠ Ambigüedad con sobrecarga y parámetros opcionales

Una situación que puede generar confusión es cuando combinamos:

* Sobrecarga de métodos
* Parámetros opcionales

Ejemplo:

```csharp
static double Suma(double num1, double num2, double num3 = 0)
{
    return num1 + num2 + num3;
}

static double Suma(double num1, double num2)
{
    return num1 + num2;
}
```

### Llamadas:

```csharp
Suma(8.2, 8.9, 9);   // Se ejecuta el método de 3 parámetros
Suma(8.2, 8.9);      // Se ejecuta el método de 2 parámetros
```

---

## 🧠 ¿Por qué ocurre esto?

El compilador elige el método que **mejor se ajusta exactamente** a la llamada.

Cuando llamamos:

```csharp
Suma(8.2, 8.9);
```

Hay dos opciones posibles:

1. Método de 2 parámetros ✅ (coincidencia exacta)
2. Método de 3 parámetros (usando valor por defecto)

El compilador prioriza la coincidencia exacta.

---

## ❌ Buenas prácticas (para evitar problemas)

No es recomendable mezclar:

* Sobrecarga
* Parámetros opcionales

cuando generan ambigüedad innecesaria.

✔ Mejor opción:

Usar solo el método con parámetro opcional:

```csharp
static double Suma(double num1, double num2, double num3 = 0)
{
    return num1 + num2 + num3;
}
```

Esto evita confusión y mantiene el código más limpio.

---

# 🎯 Resumen clave

* Los parámetros opcionales deben ir al final.
* Deben tener un valor por defecto.
* El compilador elige el método que mejor coincida.
* Evita combinar sobrecarga y parámetros opcionales si no es necesario.