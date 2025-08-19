---
layout: ../../../layouts/BlogLayout.astro
title: Command-line interface (CLI)
---

# Command-line interface (CLI)

<a class="link-documentation" href="https://learn.microsoft.com/en-us/dotnet/core/tools/" target="_blank">Documentación</a>

<hr>

- `dotnet --info` — versión de SDK y runtime instalados
- `dotnet new <template>` — crear proyecto (ej. console, webapi)
- `dotnet restore` — resolver paquetes
- `dotnet build` — compilar
- `dotnet run` — compilar y ejecutar
- `dotnet test` — ejecutar pruebas
- `dotnet publish` — generar artefactos de despliegue
- `dotnet add package <id>` — agregar paquete NuGet
- `dotnet list package` — listar paquetes
- `dotnet tool install -g <tool>` — instalar herramientas globales

Crear template de aplicación de consola en C#

```powershell
dotnet new console -n HelloDotnet
```

Compilar y ejecutar la aplicación

```powershell
dotnet run
```

## Comprobar entorno .NET

Propósito: Mostrar cómo inspeccionar runtimes/SDK y versión de C# efectiva

- `dotnet --info`
- `dotnet --list-sdks`
- `dotnet --list-runtimes`

SALIDA

Información de .NET SDKs y runtimes instalados, TFM compatibles, ubicación del SDK.

EXPLICACIÓN

1. `dotnet --info` muestra SDK, runtimes, RID y ubicaciones.
2. `dotnet --list-sdks` enumera SDKs disponibles.
3. `dotnet --list-runtimes` confirma los runtimes de ejecución.

## Crear y ejecutar una app de consola

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

SALIDA

```plaintext
Hola .NET desde consola!
Args: 0
```

EXPLICACIÓN

1. `dotnet new console -n DemoConsole` crea el proyecto.
2. `dotnet run --project DemoConsole` compila y ejecuta.
3. `Console.WriteLine` imprime a stdout; Main es el entry point.

## Usar plantillas y parámetros de `dotnet new`

Propósito: Ver cómo se parametrizan proyectos

Comandos de terminal:

- `dotnet new webapi -n DemoApi --no-https`
- `dotnet new gitignore`
- `dotnet new editorconfig`

SALIDA

Carpetas y archivos de una Web API lista para ejecutar.

EXPLICACIÓN

1. `webapi` crea una API REST mínima con controladores.
2. `--no-https` desactiva certificado dev si no lo necesitas.
3. `gitignore` y `editorconfig` agregan buenas prácticas al repo.

## Agregar y administrar paquetes NuGet

Propósito: Incorporar una dependencia externa

Comandos de terminal:

- `dotnet new console -n DemoNuGet`
- `cd DemoNuGet`
- `dotnet add package Newtonsoft.Json`
- `dotnet restore`
- `dotnet run`

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

SALIDA

```csharp
{"Message":"Hola","Version":1}
```

EXPLICACIÓN

1. `dotnet add package` agrega PackageReference al .csproj.
2. `restore` descarga dependencias.
3. Se usa JsonConvert del paquete para serializar.

## Publicar (publish) una app lista para distribución

Propósito: Generar binarios optimizados y autocontenidos

Comandos de terminal:
`dotnet publish -c Release -r win-x64 --self-contained true -p:PublishSingleFile=true`
(Reemplazar RID según SO: linux-x64, osx-arm64, etc.)

SALIDA

Carpeta `/bin/Release/<TFM>/<RID>/publish` con un ejecutable único.

EXPLICACIÓN

1. `-c Release` usa configuración optimizada.
2. `-r <RID>` fija Runtime Identifier para publicar nativo.
3. `--self-contained true` incluye runtime .NET.
4. `PublishSingleFile=true` empaqueta en un solo archivo.

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/net">Volver</a>
</p>

<style>
  .link-documentation:hover {
    color: #00ff00;
  }
</style>
