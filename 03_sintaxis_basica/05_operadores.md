# Operadores en C#

## 📋 Descripción

Los **operadores** son símbolos que permiten realizar operaciones sobre valores y variables.

En C#, los operadores permiten:

* realizar cálculos matemáticos
* comparar valores
* asignar resultados
* evaluar condiciones
* combinar expresiones lógicas

Son la base de casi toda expresión dentro del lenguaje.

---

## 🎯 Problema que resuelven

Sin operadores:

* no podríamos realizar cálculos
* no podríamos comparar datos
* no existirían decisiones (`if`, `while`, etc.)
* el código sería incapaz de procesar información

Los operadores permiten que el programa:

* transforme datos
* tome decisiones
* modifique estados

---

## 💡 Idea central

> Un operador define qué acción se ejecuta sobre uno o más operandos.

Dependiendo del tipo de operador, puede:

* devolver un número
* devolver un booleano
* modificar una variable
* evaluar una condición

---

# 🔢 Tipos de operadores

---

## ➕ Operadores aritméticos

Se usan para cálculos matemáticos.

* `+` → suma
* `-` → resta
* `*` → multiplicación
* `/` → división
* `%` → módulo (residuo)

Ejemplo:

```csharp
int resultado = 10 % 3; // 1
```

---

## 📝 Operadores de asignación

Asignan valores a variables.

* `=` → asignación simple
* `+=` → suma y asigna
* `-=` → resta y asigna
* `*=` → multiplica y asigna
* `/=` → divide y asigna
* `%=` → módulo y asigna

Ejemplo:

```csharp
x += 5; // equivalente a x = x + 5
```

---

## ⚖️ Operadores de comparación

Devuelven un valor booleano (`true` o `false`).

* `==` → igual
* `!=` → diferente
* `>` → mayor
* `<` → menor
* `>=` → mayor o igual
* `<=` → menor o igual

Son fundamentales para estructuras condicionales.

---

## 🧠 Operadores lógicos

Permiten combinar expresiones booleanas.

* `&&` → AND
* `||` → OR
* `!` → NOT

Ejemplo:

```csharp
if (edad >= 18 && tieneDocumento)
```

---

## 🔁 Operadores de incremento y decremento

* `++x` → incrementa antes de usar
* `x++` → incrementa después de usar
* `--x` → decrementa antes
* `x--` → decrementa después

La diferencia entre pre y post puede cambiar el resultado en expresiones complejas.

---

## 🧩 Operadores de tipo (identidad)

* `is` → verifica si un objeto es de cierto tipo
* `as` → conversión segura
* `typeof` → obtiene información del tipo

Se usan principalmente en programación orientada a objetos.

---

## ❓ Operador ternario

Permite escribir una condición en una sola línea.

```csharp
condicion ? valorSiTrue : valorSiFalse;
```

Ejemplo:

```csharp
string mensaje = edad >= 18 ? "Mayor" : "Menor";
```

Es útil cuando la condición es simple y clara.

---

## 🧠 20% Pareto (lo imprescindible)

Si entiendes esto, entiendes los operadores:

* Son la base de cualquier expresión en C#
* Los más usados en el día a día son:

  * `=`
  * `==`
  * `+`
  * `&&`
  * `? :`
* Permiten:

  * transformar datos
  * evaluar condiciones
  * modificar variables
* Sin operadores no existe lógica de programa

---

## 🤔 Reflexión (con respuestas)

**¿Por qué los operadores de comparación son tan importantes?**
Porque permiten que el programa tome decisiones.

**¿Qué diferencia hay entre `=` y `==`?**
`=` asigna un valor.
`==` compara dos valores.

**¿Por qué el operador ternario debe usarse con cuidado?**
Porque si la condición es compleja puede afectar la legibilidad.

**¿Cuándo puede ser peligroso usar `x++` en una expresión grande?**
Cuando el orden de evaluación altera el resultado esperado.

---

## ✍️ Resumen

⚙️ Los **operadores** son los mecanismos que permiten que un programa piense y actúe.
Sin ellos no hay cálculos, decisiones ni cambios de estado.

Dominar los operadores es dominar la base del lenguaje.
