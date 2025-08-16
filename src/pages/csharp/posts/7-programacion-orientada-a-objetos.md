---
layout: ../../../layouts/BlogLayout.astro
title: Programación Orientada a Objetos (POO)
---

# Programación Orientada a Objetos (POO)

La <abbr title="Programación Orientada a Objetos">POO</abbr> es un paradigma de programación que organiza el código en clases y objetos.
**C#** y todo **.NET** están construidos sobre este paradigma.

## Conceptos clave

- **Clase** → Es la “plantilla” o “molde” que define las características y comportamientos de un objeto.
- **Objeto** → Es una instancia (ejemplo real) de una clase.
- **Propiedades** → Datos que tiene un objeto (atributos).
- **Métodos** → Acciones que puede realizar un objeto.

Ejemplo:

- **Clase**: Auto (define que un auto tiene color, marca, modelo y puede arrancar o frenar).
- **Objeto**: Mi Toyota Corolla 2020 (instancia específica de la clase Auto).

## Creación de una clase en C#

```csharp
public class Persona
{
// Propiedades
public string Nombre { get; set; }
public int Edad { get; set; }

    // Método
    public void Saludar()
    {
        Console.WriteLine($"Hola, mi nombre es {Nombre} y tengo {Edad} años.");
    }

}
```

## Crear y usar un objeto

```csharp
Persona persona1 = new Persona();
persona1.Nombre = "Esteban";
persona1.Edad = 30;

persona1.Saludar();
```

Salida

Hola, mi nombre es Esteban y tengo 30 años.

## Constructor

Un constructor es un método especial que se ejecuta automáticamente al crear el objeto.

```csharp
public class Persona
{
public string Nombre { get; set; }
public int Edad { get; set; }

    // Constructor
    public Persona(string nombre, int edad)
    {
        Nombre = nombre;
        Edad = edad;
    }

    public void Saludar()
    {
        Console.WriteLine($"Hola, soy {Nombre} y tengo {Edad} años.");
    }

}
```

Uso

```csharp
Persona persona2 = new Persona("Luis", 25);
persona2.Saludar();
```

## Encapsulamiento

La POO recomienda proteger los datos internos usando modificadores de acceso:

- `public` → Accesible desde cualquier lugar.
- `private` → Solo accesible dentro de la clase.
- `protected` → Accesible dentro de la clase y sus herederas.
- `internal` → Accesible solo dentro del mismo proyecto.

Ejemplo

```csharp
public class CuentaBancaria
{
private double saldo;

    public CuentaBancaria(double saldoInicial)
    {
        saldo = saldoInicial;
    }

    public void Depositar(double monto)
    {
        saldo += monto;
    }

    public double ObtenerSaldo()
    {
        return saldo;
    }

}
```

## Tarea práctica

Crear una clase Libro con propiedades Titulo, Autor y Paginas, y un método que muestre la información del libro.

Crear una clase CuentaBancaria con constructor, métodos Depositar, Retirar y ObtenerSaldo, protegiendo el saldo con private.

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/csharp">Volver</a>
</p>
