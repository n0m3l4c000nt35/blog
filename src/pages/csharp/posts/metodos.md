---
layout: ../../../layouts/BlogLayout.astro
title: Métodos
---

# Métodos

Un método (o función) es un bloque de código que realiza una tarea específica y que podemos llamar cuando lo necesitemos.

Esto nos ayuda a:

- Reutilizar código
- Mantenerlo ordenado
- Facilitar la lectura y el mantenimiento

## Sintaxis básica

```csharp
tipoDeRetorno NombreDelMetodo(parámetros)
{
    // Código del método
    return valor; // solo si el tipo de retorno no es void
}
```

- `tipoDeRetorno` → El tipo de dato que devuelve el método (`int`, `string`, `bool`, etc.). Si no devuelve nada, se usa `void`.
- `NombreDelMetodo` → Debe ser descriptivo y seguir PascalCase.
- `parámetros` → Datos que recibe el método (opcionales).
- `return` → Devuelve un valor (solo si no es void).

## Ejemplo de método sin parámetros y sin retorno

```csharp
void Saludar()
{
    Console.WriteLine("Hola desde el método Saludar()");
}
```

Uso

```csharp
Saludar();
```

## Ejemplo de método con parámetros

```csharp
void SaludarA(string nombre)
{
    Console.WriteLine($"Hola {nombre}");
}
```

Uso

```csharp
SaludarA("Esteban");
```

## Ejemplo de método con retorno

```csharp
int Sumar(int a, int b)
{
    return a + b;
}
```

Uso

```csharp
int resultado = Sumar(5, 3);
Console.WriteLine($"La suma es: {resultado}");
```

## Sobrecarga de métodos (Overloading)

Podemos tener varios métodos con el mismo nombre pero distintos parámetros.

```csharp
int Sumar(int a, int b)
{
    return a + b;
}

double Sumar(double a, double b)
{
    return a + b;
}
```

## Ejemplo práctico combinado

Programa que calcula el área de un rectángulo

```csharp
double CalcularArea(double ancho, double alto)
{
    return ancho * alto;
}

Console.WriteLine("Ingrese el ancho:");
double ancho = double.Parse(Console.ReadLine());

Console.WriteLine("Ingrese el alto:");
double alto = double.Parse(Console.ReadLine());

double area = CalcularArea(ancho, alto);
Console.WriteLine($"El área es: {area}");
```

## Tarea práctica

Crear un método que reciba un número y devuelva true si es par y false si es impar.

Crear un método que reciba una lista de enteros y devuelva el número más grande.

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/csharp">Volver</a>
</p>
