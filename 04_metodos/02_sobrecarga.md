# Ámbito o Alcance de Métodos y Variables en C#

## 📌 ¿Qué es el ámbito (scope)?

El **ámbito** o **alcance** determina desde qué parte del código una variable o método puede ser utilizado.

En C#, es fácil identificar el alcance gracias a las llaves `{ }`, ya que delimitan bloques de código.

---

## 🔹 1️⃣ Alcance local (variables dentro de un método)

Las variables declaradas dentro de un método solo existen dentro de ese método.

```csharp
class Program
{
    static void PrimerMetodo()
    {
        int numero1 = 5;
        int numero2 = 7;

        Console.WriteLine(numero1 + numero2);
    }

    static void SegundoMetodo()
    {
        // Console.WriteLine(numero1 + numero2); 
        // ❌ Error: no tiene acceso a las variables del PrimerMetodo
    }
}
```

📌 `numero1` y `numero2` tienen **alcance local**.
Solo pueden usarse dentro de `PrimerMetodo`.

---

## 🔹 2️⃣ Alcance de clase (variables globales dentro de la clase)

Si necesitamos que varios métodos accedan a las mismas variables, debemos declararlas a nivel de clase.

```csharp
class Program
{
    int numero1;
    int numero2;

    void PrimerMetodo()
    {
        numero1 = 5;
        numero2 = 7;

        Console.WriteLine(numero1 + numero2);
    }

    void SegundoMetodo()
    {
        Console.WriteLine(numero1 + numero2);
    }
}
```

📌 Ahora `numero1` y `numero2` tienen **alcance de clase**.
Todos los métodos de la misma clase pueden acceder a ellas.

---

## 🧠 Diferencia clave

| Tipo de variable | Dónde se declara                     | Quién puede usarla            |
| ---------------- | ------------------------------------ | ----------------------------- |
| Local            | Dentro de un método                  | Solo ese método               |
| De clase         | Dentro de la clase, fuera de métodos | Todos los métodos de la clase |

---

## ⚠ Buenas prácticas

* Usar variables locales siempre que sea posible.
* Evitar usar variables de clase si no es necesario.
* Mantener el menor alcance posible mejora el control y reduce errores.

---

# Sobrecarga de Métodos (Method Overloading)

## 📌 ¿Qué es?

La **sobrecarga de métodos** ocurre cuando usamos el mismo nombre de método varias veces dentro de la misma clase, pero con:

* Diferente número de parámetros
* Diferente tipo de parámetros

El compilador decide cuál método ejecutar según los argumentos enviados.

---

## 🔹 Ejemplo de sobrecarga

```csharp
class Program
{
    static int Suma(int num1, int num2) => num1 + num2;

    static double Suma(double num1, double num2) => num1 + num2;

    static int Suma(int num1, int num2, int num3) 
        => num1 + num2 + num3;

    static double Suma(double num1, double num2, double num3) 
        => num1 + num2 + num3;
}
```

✔ Mismo nombre: `Suma`
✔ Diferentes parámetros
✔ Misma intención (sumar)

---

## 🧠 ¿Qué NO es sobrecarga?

❌ Cambiar solo el tipo de retorno NO es sobrecarga válida.

Esto generaría error:

```csharp
int Suma(int a, int b) { ... }
double Suma(int a, int b) { ... } // ❌ Error
```

El compilador no distingue métodos por el tipo de retorno.

---

# 🎯 Conceptos clave

* El alcance determina dónde puede usarse una variable.
* Las variables locales viven solo dentro del método.
* Las variables de clase pueden usarse en todos los métodos.
* La sobrecarga permite reutilizar el mismo nombre para comportamientos similares.