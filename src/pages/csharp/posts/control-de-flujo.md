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

<style>
  .link-back-container {
    margin: 0;
  }

  .link-back {
    color: var(--color-text);
    text-decoration: none;
    cursor: pointer;
  }

  .link-back:hover {
    color: crimson
  }

pre code {
  background: #232136;
  color: #fff;
  border-radius: 8px;
  padding: 1rem 1.2rem;
  display: block;
  font-size: 1.05rem;
  font-family: 'Fira Mono', 'Consolas', 'Menlo', monospace;
  line-height: 1.6;
  box-shadow: 0 2px 8px rgba(0,0,0,0.04);
  overflow-x: auto;
}
pre {
  background: #232136;
  border-radius: 8px;
  margin: 1.2rem 0;
  padding: 0;
  box-shadow: 0 2px 8px rgba(0,0,0,0.04);
  overflow-x: auto;
}
</style>
