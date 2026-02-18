# Formateo estándar y personalizado en C# (`N`, `F`, `C`, `P`)

## 📋 Descripción

En C#, los números pueden convertirse a texto con formatos específicos usando:

```csharp
numero.ToString("Formato");
```

Los formatos estándar permiten controlar:

* cantidad de decimales
* separadores de miles
* símbolo de moneda
* representación en porcentaje

Algunos de los más importantes son:

* `N` → Number
* `F` → Fixed-point
* `C` → Currency
* `P` → Percent

---

## 🎯 Problema que resuelve

Un número sin formato puede verse así:

```csharp
12345.6789
```

Pero en aplicaciones reales necesitamos mostrarlo como:

* 12,345.68
* $12,345.68
* 45.00%

El formateo permite presentar datos correctamente al usuario.

---

## 💡 Idea central

> `ToString()` puede recibir un código de formato que cambia la representación visual del número.

Esto no cambia el valor interno del número, solo su presentación como texto.

---

# 🔢 `N` — Number (Número con separadores)

Agrega separador de miles y permite controlar decimales.

```csharp
double numero = 12345.6789;
Console.WriteLine(numero.ToString("N2"));
```

Salida:

```
12,345.68
```

* `N2` → 2 decimales
* `N0` → sin decimales

✔️ Muy usado para reportes y tablas.

---

# 🔹 `F` — Fixed-point (Decimal fijo)

Muestra el número con cantidad fija de decimales, pero sin separador de miles.

```csharp
double numero = 12345.6789;
Console.WriteLine(numero.ToString("F2"));
```

Salida:

```
12345.68
```

✔️ Ideal cuando no quieres separadores.

---

# 💰 `C` — Currency (Moneda)

Muestra el símbolo de moneda según la configuración regional.

```csharp
decimal precio = 199.99m;
Console.WriteLine(precio.ToString("C"));
```

Salida (depende de la cultura del sistema):

```
$199.99
```

✔️ Muy usado en aplicaciones financieras.

---

# 📊 `P` — Percent (Porcentaje)

Multiplica el número por 100 y agrega símbolo `%`.

```csharp
double descuento = 0.15;
Console.WriteLine(descuento.ToString("P"));
```

Salida:

```
15.00 %
```

✔️ Útil para tasas, estadísticas y métricas.

---

# 🌎 Importante: Cultura (CultureInfo)

El resultado depende de la configuración regional.

Por ejemplo:

* En EE.UU. → `1,234.56`
* En muchos países de Latinoamérica → `1.234,56`

Se puede especificar cultura manualmente:

```csharp
using System.Globalization;

double numero = 12345.67;
Console.WriteLine(numero.ToString("N2", new CultureInfo("es-CO")));
```

Esto controla separadores y símbolos.

---

## 🧠 20% Pareto (lo imprescindible)

Si entiendes esto, entiendes el formateo:

* `"N"` → número con separador
* `"F"` → decimal fijo
* `"C"` → moneda
* `"P"` → porcentaje
* El número no cambia, solo su representación
* La cultura afecta el resultado

En aplicaciones reales usarás principalmente:

👉 `C` para dinero
👉 `N2` para reportes
👉 `P` para métricas

---

## 🤔 Reflexión (con respuestas)

**¿El formateo cambia el valor del número?**
No. Solo cambia cómo se muestra como texto.

**¿Por qué `0.15` con formato `P` muestra 15%?**
Porque el formato multiplica el valor por 100 automáticamente.

**¿Por qué cambia el separador decimal según el país?**
Porque depende de la cultura configurada.

**¿Qué formato usarías en una aplicación bancaria?**
`C` junto con una cultura específica.

---

## ✍️ Resumen

🎨 El formateo en C# permite presentar números de forma profesional y clara.

Los formatos estándar más importantes son:

* `N` → número con separador
* `F` → decimal fijo
* `C` → moneda
* `P` → porcentaje

Dominar esto es clave para aplicaciones reales, especialmente en:

* finanzas
* reportes
* estadísticas
* dashboards