# Entrada estándar, salida estándar y salida de error en C#

## 📋 Descripción

En C#, cuando trabajamos con aplicaciones de consola, existen tres flujos básicos de comunicación:

* **Entrada estándar (stdin)**
* **Salida estándar (stdout)**
* **Salida estándar de error (stderr)**

Estos flujos permiten que el programa:

* reciba datos
* muestre resultados
* reporte errores

Son conceptos fundamentales en programación de sistemas y ejecución en terminal.

---

## 🎯 Problema que resuelven

Un programa necesita comunicarse con el exterior.

Debe poder:

* recibir información del usuario
* mostrar resultados
* diferenciar mensajes normales de errores

Separar estos flujos permite:

* redireccionar información
* automatizar procesos
* registrar errores por separado

---

## 💡 Idea central

> Un programa de consola tiene tres canales de comunicación independientes.

Cada uno cumple un propósito distinto, aunque todos interactúan con la terminal.

---

# ⌨️ Entrada estándar (stdin)

Es el flujo por donde el programa **recibe datos**.

En C# se utiliza principalmente:

```csharp
Console.ReadLine();
```

Ejemplo:

```csharp
Console.Write("Ingresa tu nombre: ");
string nombre = Console.ReadLine();
Console.WriteLine($"Hola {nombre}");
```

Aquí el usuario escribe desde el teclado y el programa captura esa información.

---

# 🖥️ Salida estándar (stdout)

Es el flujo normal de salida del programa.

Se usa para mostrar información regular.

```csharp
Console.WriteLine("Mensaje informativo");
```

Todo lo que se imprime con:

* `Console.WriteLine()`
* `Console.Write()`

va a la salida estándar.

Es el canal usado para:

* resultados
* mensajes informativos
* datos procesados

---

# ⚠️ Salida estándar de error (stderr)

Es un flujo separado destinado exclusivamente a **errores**.

En C# se usa:

```csharp
Console.Error.WriteLine("Ocurrió un error");
```

Ejemplo:

```csharp
Console.Error.WriteLine("Error: archivo no encontrado");
```

Aunque visualmente aparece en la misma consola, internamente es un flujo diferente.

Esto permite:

* redireccionar errores a un archivo
* registrar fallos sin mezclar con resultados normales
* automatizar scripts más fácilmente

---

# 🔄 Redirección de flujos (concepto importante)

En la terminal se pueden redireccionar los flujos.

Ejemplo conceptual:

* `>` redirige salida estándar
* `2>` redirige errores

Esto es muy usado en:

* automatización
* DevOps
* ejecución de scripts
* integración continua

---

## 🧠 20% Pareto (lo imprescindible)

Si entiendes esto, entiendes los flujos estándar:

* `Console.ReadLine()` → entrada estándar
* `Console.WriteLine()` → salida estándar
* `Console.Error.WriteLine()` → salida de error
* stdout y stderr son flujos distintos
* Separar errores de resultados es buena práctica

---

## 🤔 Reflexión (con respuestas)

**¿Por qué existe un flujo separado para errores?**
Para poder manejarlos y redireccionarlos independientemente de la salida normal.

**¿Visualmente stdout y stderr se ven distintos?**
No necesariamente, pero internamente son diferentes.

**¿Por qué esto es importante en producción?**
Porque permite registrar errores sin mezclar con datos procesados.

**¿Una aplicación web usa estos conceptos?**
Sí, internamente el sistema operativo sigue usando estos flujos.

---

## ✍️ Resumen

🖥️ Todo programa de consola tiene tres canales de comunicación:

* Entrada estándar → recibe datos
* Salida estándar → muestra resultados
* Salida de error → reporta fallos

Comprender esta separación es clave para:

* crear aplicaciones robustas
* automatizar procesos
* manejar errores profesionalmente