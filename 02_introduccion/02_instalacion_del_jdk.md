# 🧭 Guía: Instalar el SDK de .NET

## 🎯 Objetivo

Instalar correctamente el **SDK de .NET** para poder crear, compilar y ejecutar aplicaciones en **C#** desde la consola o un entorno como Visual Studio.

---

## 🛠️ Requisitos o herramientas necesarias

* [ ] Conexión a Internet
* [ ] Permisos de administrador
* [ ] Sistema operativo compatible (Windows, Linux o macOS)
* [ ] Espacio disponible en disco

---

## 📋 Pasos a seguir

### 1️⃣ Acceder al sitio oficial de descarga

Ingresa al sitio oficial de descargas de .NET:

🔗 [https://dotnet.microsoft.com/download](https://dotnet.microsoft.com/download)

Allí encontrarás siempre la versión más reciente y estable.

---

### 2️⃣ Elegir la versión adecuada

Selecciona la versión **LTS (Long Term Support)** si quieres estabilidad para proyectos profesionales.

Verás dos opciones principales:

* **SDK** ✅ (Necesario para desarrollar)
* **Runtime** ❌ (Solo para ejecutar aplicaciones)

👉 Debes descargar el **SDK**, ya que incluye:

* Compilador de C#
* CLI (`dotnet`)
* Runtime
* Plantillas de proyectos

---

### 3️⃣ Descargar según tu sistema operativo

Elige el instalador correspondiente a:

* Windows (.exe)
* Linux (paquete o comandos según distribución)
* macOS (.pkg)

Descarga el archivo y ejecútalo.

---

### 4️⃣ Ejecutar el instalador

Sigue el asistente de instalación aceptando las opciones por defecto.

En Windows:

* Se instalará automáticamente.
* Agregará el comando `dotnet` al PATH.

---

### 5️⃣ Verificar la instalación

Abre una terminal o consola y ejecuta:

```bash
dotnet --version
```

Si la instalación fue correcta, verás el número de versión instalado.

También puedes ejecutar:

```bash
dotnet --info
```

Para obtener información detallada del entorno.

---

## 💡 Idea clave

El **SDK de .NET** es la herramienta completa de desarrollo.
Sin el SDK no puedes crear ni compilar proyectos, solo ejecutarlos.

---

## 🧠 Tips y recomendaciones

* Usa siempre versiones **LTS** para proyectos reales.
* Puedes tener múltiples versiones instaladas al mismo tiempo.
* No confundas **Runtime** con **SDK**.
* Si `dotnet` no funciona, revisa la variable PATH.

---

## 🤔 Reflexión

Instalar el SDK es el primer paso real para convertir tu equipo en una máquina de desarrollo profesional con .NET.

---

## ✍️ Resumen

🚀 Descarga el SDK desde el sitio oficial, instálalo y verifica con `dotnet --version`.
Con esto ya puedes comenzar a desarrollar en C# dentro del ecosistema .NET.