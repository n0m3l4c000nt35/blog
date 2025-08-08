---
layout: ../../../layouts/BlogLayout.astro
title: Tipos de datos
---

# Tipos de datos

4 bytes

```csharp
int myNum = 5;
```

8 bytes

```csharp
long myNum = 854.775;
```

4 bytes

```csharp
float myNum = 85.775;
```

8 bytes

```csharp
double myDoubleNum = 5.99D;
```

2 bytes

```csharp
char myLetter = 'D';
```

1 byte

```csharp
bool myBool = true;
```

2 bytes por caracter

```csharp
string myText = "Hello";
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

  /* Estilos para el bloque de código */
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
pre code:hover {
  background: #343152ff;
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
