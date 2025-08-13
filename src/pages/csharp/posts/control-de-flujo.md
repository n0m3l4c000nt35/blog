---
layout: ../../../layouts/BlogLayout.astro
title: Control de flujo
---

# Control de flujo

## Condicionales

### if-else

```csharp
int number = 10;

if (number > 0)
    Console.WriteLine("Positive");
else if (number < 0)
    Console.WriteLine("Negative");
else
    Console.WriteLine("Zero");
```

### switch

```csharp
switch (number)
{
    case > 0:
        Console.WriteLine("Positive");
        break;
    case < 0:
        Console.WriteLine("Negative");
        break;
    default:
        Console.WriteLine("Zero");
        break;
}
```

## Bucles

### for

```csharp
for (int i = 0; i < 5; i++)
Console.WriteLine(i);
```

### foreach

```csharp
var names = new List<string> { "Alice", "Bob" };
foreach (var name in names)
    Console.WriteLine(name);
```

### while

```csharp
int contador = 0;
while (contador < 5)
{
    Console.WriteLine(contador);
    contador++;
}
```

### do while

```csharp
do
{
    Console.WriteLine("Se ejecuta al menos una vez");
} while (condicion);
```

#### Interrupciones

`break` → sale del bucle

`continue` → salta a la siguiente iteración

`return` → sale del método

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/csharp">Volver</a>
</p>
