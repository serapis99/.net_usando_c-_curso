# Switch Moderno en C# (Switch Expression y Pattern Matching)

A partir de versiones modernas de C#, el `switch` evolucionó para ser más expresivo, compacto y poderoso.

Ya no solo compara valores constantes, ahora permite:

* Expresiones más limpias
* Pattern Matching (coincidencia de patrones)
* Comparaciones con rangos
* Evaluaciones más complejas

---

# 1️⃣ Switch Expression (forma compacta)

Es una versión más corta y funcional del `switch` tradicional.

## 📌 Sintaxis

```csharp
variable switch
{
    valor1 => resultado1,
    valor2 => resultado2,
    _ => resultadoPorDefecto
};
```

📌 `_` representa el caso por defecto (equivalente a `default`).

---

## 🔹 Ejemplo

```csharp
Console.WriteLine("Escoge medio de transporte (coche, tren, avion)");
string medioTransporte = Console.ReadLine();

string velocidad = medioTransporte switch
{
    "coche" => "Velocidad media: 100 km/h",
    "tren" => "Velocidad media: 250 km/h",
    "avion" => "Velocidad media: 800 km/h",
    _ => "Transporte no contemplado"
};

Console.WriteLine(velocidad);
```

✔ Más limpio
✔ Más compacto
✔ Más legible

---

# 2️⃣ Switch moderno con rangos (Pattern Matching)

Ahora podemos evaluar rangos directamente.

## 🔹 Ejemplo con edades

```csharp
int edad = 25;

string categoria = edad switch
{
    < 18 => "Menor de edad",
    >= 18 and < 60 => "Adulto",
    >= 60 => "Adulto mayor"
};

Console.WriteLine(categoria);
```

📌 Esto antes solo se podía hacer con `if`.

---

# 3️⃣ Switch con condiciones adicionales (`when`)

Permite agregar lógica extra.

```csharp
int numero = 10;

string resultado = numero switch
{
    int n when n % 2 == 0 => "Número par",
    int n when n % 2 != 0 => "Número impar"
};

Console.WriteLine(resultado);
```

---

# 4️⃣ Switch con tipos (Pattern Matching por tipo)

```csharp
object dato = 15;

string tipo = dato switch
{
    int => "Es un entero",
    string => "Es una cadena",
    double => "Es un decimal",
    _ => "Tipo desconocido"
};

Console.WriteLine(tipo);
```

📌 Esto es muy útil cuando trabajas con `object` o herencia.

---

# 🧠 Diferencias clave: Switch clásico vs moderno

| Switch clásico          | Switch moderno            |
| ----------------------- | ------------------------- |
| Usa `case`              | Usa `=>`                  |
| Requiere `break`        | No necesita `break`       |
| Solo valores constantes | Permite rangos y patrones |
| Más verboso             | Más compacto              |

---

# ⚠ Cuándo usar cada uno

Usa switch moderno cuando:

* Quieres asignar un valor directamente.
* Necesitas evaluar rangos.
* Quieres código más limpio.
* Estás trabajando con tipos o patrones.

Usa switch clásico cuando:

* Necesitas ejecutar múltiples líneas complejas.
* Estás modificando estado o realizando acciones extensas.

---

# 🎯 Resumen clave

El switch moderno:

* Es más expresivo.
* Permite pattern matching.
* Permite rangos.
* Reduce código repetitivo.
* Hace el código más declarativo.

---

# 🧠 Regla práctica

> Si tu switch devuelve un valor, usa Switch Expression.
> Si ejecuta muchas acciones complejas, usa switch clásico.