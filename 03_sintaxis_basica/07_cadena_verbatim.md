# Cadenas verbatim en C# (`@""`)

## 📋 Descripción

Las **cadenas verbatim** en C# son una forma especial de escribir strings usando el prefijo `@`.

Permiten:

* escribir rutas de archivos sin escapar barras invertidas
* escribir texto en múltiples líneas
* evitar el uso constante del carácter de escape `\`

Se escriben así:

```csharp
@"Texto aquí"
```

---

## 🎯 Problema que resuelven

En C#, el carácter `\` se usa como **carácter de escape**.

Por ejemplo:

```csharp
"C:\\Users\\Juan\\Documentos"
```

Esto puede volverse:

* difícil de leer
* propenso a errores
* visualmente confuso

Las cadenas verbatim eliminan esa necesidad.

---

## 💡 Idea central

> Una cadena verbatim interpreta el texto literalmente.

Eso significa que:

* no procesa secuencias de escape
* respeta saltos de línea
* mantiene el formato tal como se escribe

---

# 📂 Ejemplo con rutas de archivos

### ❌ Sin verbatim

```csharp
string ruta = "C:\\Users\\Juan\\Documentos\\archivo.txt";
```

### ✔️ Con verbatim

```csharp
string ruta = @"C:\Users\Juan\Documentos\archivo.txt";
```

Mucho más limpio y legible.

---

# 📄 Ejemplo con múltiples líneas

```csharp
string mensaje = @"Hola,
Bienvenido al sistema.
Este texto mantiene los saltos de línea.";
```

El texto conserva exactamente el formato escrito.

---

# 🔐 ¿Cómo incluir comillas dentro de una cadena verbatim?

En lugar de usar `\"`, se duplican las comillas:

```csharp
string frase = @"Ella dijo: ""Hola mundo""";
```

---

# 🧠 Combinación con interpolación

También se puede combinar con interpolación usando `$@` o `@$`.

```csharp
string nombre = "Carlos";

string mensaje = $@"Hola {nombre},
Bienvenido al sistema.";
```

Esto permite:

* interpolación
* múltiples líneas
* texto literal

Todo al mismo tiempo.

---

## 🧠 20% Pareto (lo imprescindible)

Si entiendes esto, entiendes las cadenas verbatim:

* Se usan con `@""`
* No requieren escapar `\`
* Permiten múltiples líneas
* Para comillas dobles se usan `""`
* Se pueden combinar con interpolación (`$@""`)

---

## 🤔 Reflexión (con respuestas)

**¿Por qué las rutas de Windows son un caso típico para usar verbatim?**
Porque contienen muchas barras invertidas (`\`).

**¿Una cadena verbatim procesa `\n` como salto de línea?**
No. Lo interpreta literalmente como texto.

**¿Cómo escribo comillas dentro de una cadena verbatim?**
Duplicando las comillas: `""`.

**¿Cuándo conviene usar `$@""`?**
Cuando necesitas interpolación y múltiples líneas al mismo tiempo.

---

## ✍️ Resumen

🧵 Las **cadenas verbatim** permiten escribir texto literal sin preocuparse por caracteres de escape.

Son especialmente útiles para:

* rutas de archivos
* consultas SQL largas
* textos multilínea
* plantillas

Combinadas con interpolación, se convierten en una herramienta muy poderosa y limpia para construir texto en C#.