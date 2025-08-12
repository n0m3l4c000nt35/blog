---
layout: ../../../layouts/BlogLayout.astro
title: Control de flujo
---

# Control de flujo

## if-else

```csharp
int number = 10;

if (number > 0)
    Console.WriteLine("Positive");
else if (number < 0)
    Console.WriteLine("Negative");
else
    Console.WriteLine("Zero");
```

## switch

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

## for

```csharp
for (int i = 0; i < 5; i++)
Console.WriteLine(i);
```

## foreach

```csharp
var names = new List<string> { "Alice", "Bob" };
foreach (var name in names)
    Console.WriteLine(name);
```

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/csharp">Volver</a>
</p>
