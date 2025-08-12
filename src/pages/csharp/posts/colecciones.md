---
layout: ../../../layouts/BlogLayout.astro
title: Colecciones
---

# Colecciones

## Array

```csharp
int[] numbers = { 1, 2, 3 };
Console.WriteLine(numbers[0]); // 1
```

## List

```csharp
var list = new List<string> { "A", "B" };
list.Add("C");
list.Remove("B");
```

## Dictionary

```csharp
var dict = new Dictionary<string, int>();
dict["Apples"] = 5;
dict["Oranges"] = 3;
Console.WriteLine(dict["Apples"]);
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
