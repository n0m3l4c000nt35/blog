---
layout: ../../../layouts/BlogLayout.astro
title: Estructuras de control
---

# Estructuras de control

Las estructuras de control permiten decidir qué partes del código se ejecutan dependiendo de ciertas condiciones.

## if y else

Sirven para ejecutar código solo si una condición es verdadera.

```csharp
if (condición)
{
    // Código si la condición es verdadera
}
else
{
    // Código si la condición es falsa
}
```

```csharp
Console.WriteLine("Ingrese su edad:");
int edad = int.Parse(Console.ReadLine());

if (edad >= 18)
{
    Console.WriteLine("Eres mayor de edad.");
}
else
{
    Console.WriteLine("Eres menor de edad.");
}
```

## else if

Permite evaluar múltiples condiciones.

```csharp
Console.WriteLine("Ingrese su nota (0-10):");
int nota = int.Parse(Console.ReadLine());

if (nota >= 9)
{
    Console.WriteLine("Excelente");
}
else if (nota >= 7)
{
    Console.WriteLine("Muy bien");
}
else if (nota >= 6)
{
    Console.WriteLine("Aprobado");
}
else
{
    Console.WriteLine("Reprobado");
}
```

## switch

Se usa cuando hay muchas opciones posibles para una misma variable.

```csharp
Console.WriteLine("Ingrese un número del 1 al 3:");
int opcion = int.Parse(Console.ReadLine());

switch (opcion)
{
    case 1:
        Console.WriteLine("Opción uno seleccionada");
        break;
    case 2:
        Console.WriteLine("Opción dos seleccionada");
        break;
    case 3:
        Console.WriteLine("Opción tres seleccionada");
        break;
    default:
        Console.WriteLine("Opción inválida");
        break;
}
```

Cada `case` debe terminar con `break` para evitar que el flujo continúe a la siguiente opción.

`default` es opcional y se ejecuta si ninguna condición coincide.

## Operador ternario

Forma corta de escribir un `if` simple.

```csharp
condición ? valor_si_true : valor_si_false;
```

```csharp
int edad = 20;
string mensaje = edad >= 18 ? "Mayor de edad" : "Menor de edad";
Console.WriteLine(mensaje);
```

### Tarea práctica

Programa que pida un número del 1 al 7 y muestre el día de la semana (1 = lunes, etc.) usando switch.

Programa que pregunte la temperatura y muestre:

- "Frío" si es menor a 10°C
- "Templado" si está entre 10°C y 25°C
- "Caluroso" si es mayor a 25°C

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/csharp">Volver</a>
</p>
