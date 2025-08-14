---
layout: ../../../layouts/BlogLayout.astro
title: Fundamentos
---

# Fundamentos

## ¿Qué es .NET?

**.NET** es una plataforma de desarrollo creada por Microsoft para construir aplicaciones de todo tipo:

- Aplicaciones de consola (programas que se ejecutan en terminal)
- Aplicaciones de escritorio (Windows Forms, WPF, MAUI)
- Aplicaciones web (con ASP.NET Core)
- APIs para backend
- Aplicaciones móviles (con MAUI)
- Servicios en la nube (Azure Functions, microservicios).

Es multiplataforma: se ejecuta en Windows, Linux y macOS, y permite escribir código en varios lenguajes, siendo C# el más usado.

## Ecosistema actual de .NET

Desde **.NET** 5, Microsoft unificó todo bajo el nombre **.NET** (ya no existen **.NET Framework**, **.NET Core** como productos separados).

### Actualmente, el ciclo es anual:

- .NET 6 → LTS (Soporte Largo)
- .NET 7 → STS (Soporte Corto)
- .NET 8 → LTS (actual estable, hasta noviembre 2026)

### Componentes clave del ecosistema

- CLR (Common Language Runtime) → El motor que ejecuta el código.
- BCL (Base Class Library) → Biblioteca de clases base con funcionalidades listas para usar (manejo de archivos, fechas, colecciones, etc.).
- SDK → Herramientas para compilar, ejecutar y publicar aplicaciones.

Lenguajes soportados: C#, F#, VB.NET (C# es el estándar de la industria hoy).

NuGet → Gestor de paquetes para agregar librerías externas a tu proyecto.

## ¿Cómo se ejecuta un programa en .NET?

El flujo es así:

1. Se escribe el código en C# (`.cs`).
2. El compilador lo convierte en IL (Intermediate Language).
3. El CLR traduce ese IL a código máquina y lo ejecuta.

Esto permite que el código sea portátil y funcione igual en cualquier sistema operativo que tenga **.NET** instalado.

## Primer ejemplo práctico: "Hello, World!"

Proyecto de consola y primer programa.

Pasos en la terminal:

```powershell
dotnet new console -n HelloWorldApp
cd HelloWorldApp
dotnet run
```

Esto creará un proyecto base y lo ejecutará.

```csharp
// Programa principal en C#
Console.WriteLine("Hello, World!");
```

Explicación línea por línea:

`Console` → Clase de la **BCL** que permite interactuar con la consola.

`WriteLine(...)` → Método que imprime un texto seguido de un salto de línea.

`"Hello, World!"` → Cadena de texto (string) que se muestra.

En **.NET** moderno no es necesario escribir `class Program` y `static void Main()` explícitamente para programas simples: el compilador lo genera por ti (top-level statements).

Escenario real:

Aunque `“Hello, World!”` es básico, todo programa en **.NET** inicia con código como este:

- Lectura y escritura de datos en consola.
- Responder a eventos.
- Mostrar mensajes al usuario.

Aunque `“Hello, World!”` es básico, todo programa en **.NET** inicia con código como este:

- Lectura y escritura de datos en consola.
- Responder a eventos.
- Mostrar mensajes al usuario.

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/net">Volver</a>
</p>

<style>
  .link-documentation:hover {
    color: #00ff00;
  }
</style>
