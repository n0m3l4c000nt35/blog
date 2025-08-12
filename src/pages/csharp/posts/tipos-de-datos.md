---
layout: ../../../layouts/BlogLayout.astro
title: Tipos de datos
---

# Tipos de datos

## Value types

Almacenan el valor directamente en memoria stack

- Numéricos enteros: `int`, `long`, `short`, `byte`
- Numéricos decimales: `float`, `double`, `decimal`
- Booleanos → `bool`
- Caracteres → `char`
- Estructuras → `struct`
- Enumeraciones → `enum`
- Otros → `DateTime`

```csharp
int edad = 25;
float altura = 1.75f;
bool esMayor = true;
char inicial = 'A';
```

## Rerefence types

Se guardan en memoria heap

Una variable almacena la referencia (dirección) al objeto

Si se copia la referencia se apunta al mismo objeto

- Cadenas de texto → `string`
- Objetos → `class`
- Arrays
- Colecciones
- Interfaces → `interface`

```csharp
string nombre = "Juan";
string otroNombre = nombre;
// Ambos apuntan al mismo texto
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
