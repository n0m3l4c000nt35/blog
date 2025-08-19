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

## Tipos de datos

| Tipo       | Descripción       | Ejemplo                |
| ---------- | ----------------- | ---------------------- |
| `string`   | Texto             | `"Hola"`               |
| `int`      | Números enteros   | `42`                   |
| `long`     | Números enteros   | `1234567890123456789L` |
| `byte`     | Números enteros   | `255`                  |
| `float`    | Números decimales | `5.5f`                 |
| `double`   | Números decimales | `3.14`                 |
| `decimal`  | Números decimales | `19.99m`               |
| `bool`     | Verdadero/Falso   | `true`, `false`        |
| `char`     | Un solo carácter  | `'A'`                  |
| `DateTime` | Fechas y horas    | `DateTime.Now`         |

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/csharp">Volver</a>
</p>
