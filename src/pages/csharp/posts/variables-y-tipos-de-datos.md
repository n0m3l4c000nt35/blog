---
layout: ../../../layouts/BlogLayout.astro
title: Variables y tipos de datos
---

# Variables y tipos de datos

En C#, una variable es un espacio en memoria donde almacenamos un valor con un nombre que nos permite acceder a él.
Una “caja” con etiqueta donde se guarda algo.

## Declaración de variables

En C#, toda variable necesita:

- Tipo de dato → Define qué clase de información almacena (números, texto, fechas, etc.).
- Nombre → Cómo vamos a referirnos a ella.
- Valor (opcional) → El dato que contiene.

```csharp
string name = "Esteban";
int age = 30;
```

## Tipos de datos principales en C#

| Tipo       | Descripción       | Ejemplo         |
| ---------- | ----------------- | --------------- |
| `string`   | Texto             | `"Hola"`        |
| `int`      | Números enteros   | `42`            |
| `double`   | Números decimales | `3.14`          |
| `bool`     | Verdadero/Falso   | `true`, `false` |
| `char`     | Un solo carácter  | `'A'`           |
| `DateTime` | Fechas y horas    | `DateTime.Now`  |

### Ejemplo práctico

Programa que pide el nombre y edad al usuario y luego muestre un mensaje.

```csharp
// Pedimos nombre al usuario
Console.WriteLine("¿Cuál es tu nombre?");
string name = Console.ReadLine(); // Lee el texto que el usuario escribe

// Pedimos edad al usuario
Console.WriteLine("¿Cuántos años tienes?");
int age = int.Parse(Console.ReadLine()); // Convierte el texto a número entero

// Mostramos el mensaje final
Console.WriteLine($"Hola {name}, tienes {age} años.");
```

Explicación:

- `Console.ReadLine()` → Lee una línea de texto de la consola.
- `int.Parse(...)` → Convierte el texto ingresado a un número entero.
- `$"Hola {name}..."` → Interpolación de cadenas, permite insertar variables dentro de un string usando {}.

⚠️ Si el usuario escribe algo que no es un número, `int.Parse` dará error.

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/csharp">Volver</a>
</p>
