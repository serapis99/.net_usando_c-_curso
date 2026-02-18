# Parse en C# (`int.Parse`, `double.Parse`, etc.)

## 📋 Descripción

En C#, **Parse** es un método que permite convertir texto (`string`) en otros tipos de datos.

Se utiliza cuando:

* el usuario ingresa datos como texto
* se leen datos desde archivos
* se reciben datos desde APIs
* se necesita transformar texto en valores numéricos

Ejemplos comunes:

* `int.Parse()`
* `double.Parse()`
* `decimal.Parse()`
* `DateTime.Parse()`

---

## 🎯 Problema que resuelve

En C#, todo lo que entra desde:

* `Console.ReadLine()`
* archivos
* peticiones HTTP

llega como **string**.

Pero muchas veces necesitamos:

* números
* fechas
* valores booleanos

Parse permite convertir ese texto al tipo correcto.

---

## 💡 Idea central

> Parse transforma una cadena en un tipo específico.

⚠️ Si el texto no tiene el formato correcto, el método lanzará una excepción.

---

# 🔢 `int.Parse()`

Convierte un string en entero.

```csharp
string numeroTexto = "25";
int numero = int.Parse(numeroTexto);

Console.WriteLine(numero);
```

Si el texto no es numérico:

```csharp
int numero = int.Parse("hola"); // ERROR
```

Se lanzará una excepción `FormatException`.

---

# 🔢 `double.Parse()`

Convierte texto en número decimal.

```csharp
string temperaturaTexto = "34.5";
double temperatura = double.Parse(temperaturaTexto);
```

⚠️ Puede depender de la configuración regional (coma o punto decimal).

---

# 💰 `decimal.Parse()`

Recomendado para valores financieros.

```csharp
string precioTexto = "199.99";
decimal precio = decimal.Parse(precioTexto);
```

---

# 📅 `DateTime.Parse()`

Convierte texto en fecha.

```csharp
string fechaTexto = "2025-01-01";
DateTime fecha = DateTime.Parse(fechaTexto);
```

Debe estar en un formato válido.

---

# 🚨 Problema con Parse

Si el valor no es válido:

* lanza excepción
* puede romper el programa si no se maneja

Ejemplo problemático:

```csharp
int edad = int.Parse(Console.ReadLine());
```

Si el usuario escribe letras → el programa falla.

---

# ✅ Alternativa segura: `TryParse()`

Evita excepciones.

```csharp
string texto = "25";

if (int.TryParse(texto, out int numero))
{
    Console.WriteLine(numero);
}
else
{
    Console.WriteLine("Valor inválido");
}
```

Ventajas:

* no lanza excepción
* devuelve `true` o `false`
* más seguro para entradas del usuario

En aplicaciones reales, casi siempre se prefiere `TryParse`.

---

## 🧠 20% Pareto (lo imprescindible)

Si entiendes esto, entiendes Parse:

* Convierte `string` a otro tipo
* Lanza excepción si el formato es inválido
* `TryParse()` es más seguro
* Siempre valida entrada de usuario

Regla profesional:

👉 Entrada externa → usa `TryParse()`
👉 Datos controlados → puedes usar `Parse()`

---

## 🤔 Reflexión (con respuestas)

**¿Por qué todo llega como string desde Console.ReadLine()?**
Porque la entrada estándar siempre devuelve texto.

**¿Por qué Parse puede ser peligroso?**
Porque lanza excepción si el formato es incorrecto.

**¿Qué devuelve TryParse?**
Un booleano indicando si la conversión fue exitosa.

**¿Cuál es mejor en producción?**
TryParse, especialmente con datos del usuario.

---

## ✍️ Resumen

🔄 Parse permite convertir texto en datos útiles como enteros, decimales o fechas.

Pero:

* puede lanzar excepciones
* requiere validación

Para aplicaciones robustas, `TryParse()` es la opción recomendada.