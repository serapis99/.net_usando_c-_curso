# Métodos en C#

## 📌 ¿Qué son?

Un **método** es un grupo de sentencias (instrucciones) al que se le asigna un nombre identificativo y que realiza una tarea específica.

Es una unidad de comportamiento dentro de una clase.

---

## 🎯 ¿Para qué sirven?

* Permiten ejecutar una tarea concreta cuando se necesite.
* Evitan repetir código.
* Mejoran la organización del programa.
* Hacen el código más reutilizable y mantenible.

📌 Un método **no ejecuta su tarea hasta que es llamado**.

---

## 🧩 Sintaxis básica

```csharp
tipoDeRetorno NombreMetodo(parametrosOpcionales)
{
    // cuerpo del método
}
```

### 🔎 Partes de la sintaxis

* `tipoDeRetorno` → Tipo de dato que devuelve (int, string, double, void, etc.)
* `NombreMetodo` → Identificador del método
* `parametros` → Datos que recibe (opcionales)
* `return` → Devuelve el resultado (si no es `void`)

---

# 🧮 Ejemplo 1: Método sin parámetros

```csharp
class Program
{
    static void Main()
    {
        Console.WriteLine(SumaNumero());
    }

    static int SumaNumero()
    {
        int num1 = 7;
        int num2 = 9;
        int resultado = num1 + num2;
        return resultado;
    }
}
```

✔ No recibe parámetros
✔ Devuelve un `int`

---

# 🧮 Ejemplo 2: Método con parámetros

```csharp
class Program
{
    static void Main()
    {
        Console.WriteLine(SumaNumero(7, 9));
    }

    static int SumaNumero(int num1, int num2)
    {
        int resultado = num1 + num2;
        return resultado;
    }
}
```

✔ Recibe dos parámetros
✔ Devuelve un `int`
✔ Es más reutilizable

---

# 🔄 Método que no devuelve valor (`void`)

Si un método no devuelve nada, se usa `void`:

```csharp
static void Saludar(string nombre)
{
    Console.WriteLine("Hola " + nombre);
}
```

---

# 🧠 Buenas prácticas al nombrar métodos

* Usar **PascalCase**
* El nombre debe expresar una acción (verbo)
* Debe ser claro y descriptivo

✔ Correcto:

* `CalcularTotal()`
* `ObtenerEdad()`
* `ImprimirFactura()`

❌ Incorrecto:

* `Metodo1()`
* `Prueba()`
* `X()`

📌 Un buen nombre evita comentarios innecesarios.

---

# ⚠ Advertencias importantes

* Todos los métodos deben estar dentro de una clase.
* En C# no existen funciones libres como en otros lenguajes; todo pertenece a una clase.
* Se debe especificar siempre el tipo de retorno.
* Si el método no devuelve nada, debe declararse como `void`.
* Si el método devuelve un valor, debe usar `return`.

---

# 🧠 Concepto clave

Un método es:

> Una acción reutilizable que vive dentro de una clase y se ejecuta solo cuando es llamada.