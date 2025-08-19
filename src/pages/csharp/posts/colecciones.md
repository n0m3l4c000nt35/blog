---
layout: ../../../layouts/BlogLayout.astro
title: Colecciones
---

# Colecciones

En programación, colecciones son estructuras que permiten almacenar múltiples valores bajo una sola variable.
En C# las más básicas son arrays y listas.

## Arrays

Un array tiene un tamaño fijo y almacena elementos del mismo tipo

```csharp
// Declarar y asignar valores
int[] numeros = { 10, 20, 30, 40, 50 };

// Acceder a un elemento por su índice (comienza en 0)
Console.WriteLine(numeros[0]); // 10
Console.WriteLine(numeros[4]); // 50

// Modificar un valor
numeros[2] = 35;

// Recorrer con for
for (int i = 0; i < numeros.Length; i++)
{
    Console.WriteLine(numeros[i]);
}
```

- `numeros.Length` devuelve la cantidad de elementos.
- El tamaño del array no puede cambiar después de ser creado.

## Listas (`List<T>`)

Una lista es similar a un array pero dinámica, podemos agregar o quitar elementos.

```csharp
using System.Collections.Generic; // Necesario para List

List<string> nombres = new List<string>();

// Agregar elementos
nombres.Add("Ana");
nombres.Add("Luis");
nombres.Add("Pedro");

// Recorrer con foreach
foreach (string nombre in nombres)
{
    Console.WriteLine(nombre);
}
```

## Métodos útiles de `List<T>`

```csharp
nombres.Add("María");         // Agrega al final
nombres.Insert(1, "Carlos");  // Inserta en índice específico
nombres.Remove("Luis");       // Elimina por valor
nombres.RemoveAt(0);          // Elimina por índice
nombres.Clear();              // Elimina todos los elementos
bool contiene = nombres.Contains("Pedro"); // Verifica existencia
int cantidad = nombres.Count; // Cantidad de elementos
```

## Ejemplo práctico combinado

Programa que pide 3 números, los guarda en una lista y calcula el promedio

```csharp
using System.Collections.Generic;

List<int> numeros = new List<int>();

for (int i = 0; i < 3; i++)
{
    Console.WriteLine($"Ingrese el número {i + 1}:");
    int num = int.Parse(Console.ReadLine());
    numeros.Add(num);
}

int suma = 0;
foreach (int n in numeros)
{
    suma += n;
}

double promedio = (double)suma / numeros.Count;
Console.WriteLine($"El promedio es: {promedio}");
```

## Tarea práctica

Crear un programa que pida nombres indefinidamente hasta que el usuario escriba "fin". Luego mostrar todos los nombres ingresados.

Crear un programa que almacene 5 números en un array, los muestre y luego indique el número más grande.

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/csharp">Volver</a>
</p>
