# 🧭 Guía: Crear tu primer proyecto con dotnet new

## 🎯 Objetivo

Aprender a crear un proyecto desde cero utilizando la **CLI de .NET** con el comando `dotnet new`, entendiendo la estructura básica generada automáticamente.

---

## 🛠️ Requisitos o herramientas necesarias

* [ ] SDK de .NET instalado
* [ ] Terminal o consola (PowerShell, CMD, Bash, etc.)
* [ ] Conocimientos básicos de C#

---

## 📋 Pasos a seguir

### 1️⃣ Verificar que .NET esté instalado

En la terminal, ejecuta:

```bash
dotnet --version
```

Si aparece un número de versión, el SDK está correctamente instalado.

---

### 2️⃣ Crear una carpeta para el proyecto

Es recomendable organizar los proyectos en una carpeta dedicada:

```bash
mkdir MiPrimerProyecto
cd MiPrimerProyecto
```

---

### 3️⃣ Crear el proyecto con `dotnet new`

Para crear una aplicación de consola (la más básica), ejecuta:

```bash
dotnet new console
```

Este comando:

* Crea los archivos necesarios
* Genera un archivo `.csproj`
* Crea un archivo `Program.cs`
* Restaura automáticamente las dependencias

---

### 4️⃣ Ejecutar el proyecto

Una vez creado, ejecuta:

```bash
dotnet run
```

Deberías ver en pantalla:

```
Hello, World!
```

🎉 ¡Tu primer proyecto en .NET está funcionando!

---

### 5️⃣ Comprender la estructura generada

Archivos principales creados:

* **Program.cs** → Contiene el código principal.
* **MiPrimerProyecto.csproj** → Archivo de configuración del proyecto.
* **obj/** → Archivos temporales generados en compilación.

Ejemplo básico de `Program.cs`:

```csharp
Console.WriteLine("Hello, World!");
```

---

## 💡 Idea clave

El comando `dotnet new` genera automáticamente la estructura base de un proyecto según una **plantilla**.

---

## 🧠 Tips y recomendaciones

* Puedes ver todas las plantillas disponibles con:

```bash
dotnet new list
```

* Para crear otros tipos de proyectos:

```bash
dotnet new web
dotnet new mvc
dotnet new classlib
```

* Usa `dotnet build` si solo quieres compilar sin ejecutar.

---

## 🤔 Reflexión

Con `dotnet new`, el desarrollo en .NET comienza desde la consola.
No necesitas un IDE para empezar: el SDK ya incluye todo lo necesario.

---

## ✍️ Resumen

🚀 `dotnet new console` crea tu primer proyecto.
🚀 `dotnet run` lo ejecuta.
🚀 El SDK genera automáticamente la estructura básica del proyecto.
