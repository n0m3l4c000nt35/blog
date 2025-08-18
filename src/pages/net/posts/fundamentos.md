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

## EJEMPLO 1.1.1: Comprobar entorno .NET

Propósito: Mostrar cómo inspeccionar runtimes/SDK y versión de C# efectiva

No hay código C#, son comandos a ejecutar en terminal:

```powershell
dotnet --info
dotnet --list-sdks
dotnet --list-runtimes
```

SALIDA ESPERADA:
Información de .NET SDKs y runtimes instalados, TFM compatibles, ubicación del SDK.

EXPLICACIÓN DETALLADA:

1. `dotnet --info` muestra SDK, runtimes, RID y ubicaciones.
2. `dotnet --list-sdks` enumera SDKs disponibles.
3. `dotnet --list-runtimes` confirma los runtimes de ejecución.

## EJEMPLO 1.1.2: Crear y ejecutar una app de consola

Propósito: Demostrar ciclo básico new/restore/build/run

```csharp
using System; // Namespaces de la BCL, proveen Console, etc.

namespace EjemploTema
{
    // Clase de entrada para el programa
    public class Program
    {
        // Punto de entrada
        public static void Main(string[] args)
        {
            // Escribe un saludo y el número de argumentos recibidos
            Console.WriteLine("Hola .NET desde consola!");
            Console.WriteLine($"Args: {args.Length}");
        }
    }
}
```

SALIDA ESPERADA:

```csharp
Hola .NET desde consola!
Args: 0
```

EXPLICACIÓN DETALLADA:

1. `dotnet new console -n DemoConsole` crea el proyecto.
2. `dotnet run --project DemoConsole` compila y ejecuta.
3. `Console.WriteLine` imprime a stdout; Main es el entry point.

## EJEMPLO 1.1.3: Usar plantillas y parámetros de 'dotnet new'

Propósito: Ver cómo se parametrizan proyectos

Comandos de terminal:

```csharp
dotnet new webapi -n DemoApi --no-https
dotnet new gitignore
dotnet new editorconfig
```

SALIDA ESPERADA:
Carpetas y archivos de una Web API lista para ejecutar.

EXPLICACIÓN DETALLADA:

1. `webapi` crea una API REST mínima con controladores.
2. `--no-https` desactiva certificado dev si no lo necesitas.
3. 'gitignore' y 'editorconfig' agregan buenas prácticas al repo.

## EJEMPLO 1.1.4: Agregar y administrar paquetes NuGet

Propósito: Incorporar una dependencia externa

Comandos de terminal:

```csharp
dotnet new console -n DemoNuGet
cd DemoNuGet
dotnet add package Newtonsoft.Json
dotnet restore
dotnet run
```

En Program.cs:

```csharp
using System;
using Newtonsoft.Json; // from NuGet

namespace EjemploTema
{
    public class Program
    {
        public static void Main()
        {
            var obj = new { Message = "Hola", Version = 1 };
            string json = JsonConvert.SerializeObject(obj);
            Console.WriteLine(json);
        }
    }
}
```

SALIDA ESPERADA:

```csharp
{"Message":"Hola","Version":1}
```

EXPLICACIÓN DETALLADA:

1. `dotnet add package` agrega PackageReference al .csproj.
2. 'restore' descarga dependencias.
3. Se usa JsonConvert del paquete para serializar.

## EJEMPLO 1.1.5: Publicar (publish) una app lista para distribución

Propósito: Generar binarios optimizados y autocontenidos

Comandos de terminal:

```csharp
dotnet publish -c Release -r win-x64 --self-contained true -p:PublishSingleFile=true
```

(Reemplazar RID según SO: linux-x64, osx-arm64, etc.)

SALIDA ESPERADA:
Carpeta `/bin/Release/<TFM>/<RID>/publish` con un ejecutable único.

EXPLICACIÓN DETALLADA:

1. `-c Release` usa configuración optimizada.
2. `-r <RID>` fija Runtime Identifier para publicar nativo.
3. `--self-contained true` incluye runtime .NET.
4. 'PublishSingleFile=true' empaqueta en un solo archivo.

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/net">Volver</a>
</p>

<style>
  .link-documentation:hover {
    color: #00ff00;
  }
</style>
