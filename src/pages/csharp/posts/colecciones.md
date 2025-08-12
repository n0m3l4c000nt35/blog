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

## Queue (cola FIFO)

```csharp
Queue<int> cola = new Queue<int>();
cola.Enqueue(1);
cola.Enqueue(2);
int primero = cola.Dequeue(); // saca el primero
```

## Stack (pila LIFO)

```csharp
Stack<int> pila = new Stack<int>();
pila.Push(1);
pila.Push(2);
int ultimo = pila.Pop(); // saca el último
```

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/csharp">Volver</a>
</p>
