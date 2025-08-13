---
layout: ../../../layouts/BlogLayout.astro
title: Tipos de datos
---

# Tipos de datos

## Value types

Almacenan el valor directamente en memoria stack

- Numéricos enteros: `int`, `long`, `short`, `byte`
- Numéricos decimales: `float`, `double`, `decimal`
- Booleanos → `bool` (`true` o `false`)
- Caracteres → `char` (un único carácter Unicode)
- Estructuras → `struct`
- Enumeraciones → `enum`
- Fechas → `DateTime`

```csharp
int edad = 25;
float altura = 1.75f;
bool esMayor = true;
char inicial = 'A';
DateTime hoy = DateTime.Now;
```

## Rerefence types

Se guardan en memoria heap

Una variable almacena la referencia (dirección) al objeto

Si se copia la referencia se apunta al mismo objeto

- Cadenas de texto → `string` (inmutable)
- Objetos → `class` (instancias de clases)
- Arrays → `int[]`, `string[]`
- Colecciones
- Interfaces → `interface`

```csharp
string nombre = "Juan";
string otroNombre = nombre;
// Ambos apuntan al mismo texto

int[] numeros = {1, 2, 3};
```

## Especiales

- `var`
- `dynamic`
- `nullable` → `int?`, `DateTime?` (permite `null` en value types)

## Conversiones

- Implícitas → seguras (ej. `int` → `long`)
- Explícitas (casting) → `(double)miEntero`
- Métodos: `Convert.ToInt32()`, `int.Parse()`, `int.TryParse()`

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/csharp">Volver</a>
</p>
