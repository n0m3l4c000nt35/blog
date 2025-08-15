---
layout: ../../../layouts/BlogLayout.astro
title: Bucles
---

# Bucles

Un bucle es una estructura que permite repetir un bloque de código varias veces, ya sea un número definido o mientras se cumpla una condición.

## for — Bucle con contador

Se usa cuando sabemos cuántas veces queremos repetir el código

```csharp
for (inicialización; condición; incremento)
{
    // Código que se repite
}
```

```csharp
for (int i = 1; i <= 5; i++)
{
    Console.WriteLine($"Iteración {i}");
}
```

- `int i = 1` → Inicializa el contador
- `i <= 5` → Condición para seguir ejecutando
- `i++` → Incrementa el contador

## while — Bucle condicional

Repite el código mientras se cumpla la condición

```csharp
int contador = 1;
while (contador <= 5)
{
    Console.WriteLine($"Contador: {contador}");
    contador++;
}
```

## do...while — Ejecuta al menos una vez

Primero ejecuta el bloque y luego evalúa la condición

```csharp
int numero;
do
{
    Console.WriteLine("Ingrese un número positivo:");
    numero = int.Parse(Console.ReadLine());
} while (numero <= 0);

Console.WriteLine($"Ingresaste {numero}");
```

## foreach — Recorrer colecciones

Ideal para recorrer listas, arrays u otras colecciones.

```csharp
string[] nombres = { "Ana", "Luis", "Pedro" };

foreach (string nombre in nombres)
{
    Console.WriteLine(nombre);
}
```

- `string nombre` → Variable que toma el valor de cada elemento.
- `in nombres` → Indica la colección a recorrer.

## Palabras clave de control

- `break` → Sale del bucle.
- `continue` → Salta a la siguiente iteración.

```csharp
for (int i = 1; i <= 5; i++)
{
    if (i == 3) continue; // Salta cuando i es 3
    Console.WriteLine(i);
}
```

Tarea práctica

Crear un programa que pida un número y muestre su tabla de multiplicar (del 1 al 10) usando for.

Crear un programa que lea 5 nombres y luego los muestre en orden inverso usando foreach.

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/csharp">Volver</a>
</p>
