---
layout: ../../../layouts/BlogLayout.astro
title: Herencia y Polimorfismo
---

# Herencia y Polimorfismo

## Herencia

La herencia permite que una clase (llamada clase hija o subclase) obtenga propiedades y métodos de otra clase (llamada clase base o superclase).

Esto ayuda a:

- Reutilizar código
- Crear jerarquías de clases
- Facilitar el mantenimiento

Sintaxis

```csharp
public class ClaseHija : ClaseBase
{
// Código adicional de la hija
}
```

Ejemplo

```csharp
// Clase base
public class Animal
{
    public string Nombre { get; set; }

    public void Comer()
    {
        Console.WriteLine($"{Nombre} está comiendo.");
    }

}

// Clase hija
public class Perro : Animal
{
    public void Ladrar()
    {
        Console.WriteLine($"{Nombre} dice: ¡Guau!");
    }
}
```

Uso

```csharp
Perro perro1 = new Perro();
perro1.Nombre = "Firulais";
perro1.Comer(); // Método heredado de Animal
perro1.Ladrar(); // Método propio de Perro
```

## Modificadores en herencia

- `public` → Accesible en cualquier lugar.
- `protected` → Accesible en la clase y en sus clases hijas.
- `private` → No accesible en la clase hija.

## Polimorfismo

El polimorfismo significa que una misma acción puede comportarse de diferentes maneras dependiendo del objeto que la ejecute.

En C#, para usar polimorfismo:

- El método en la clase base se marca como virtual.
- En la clase hija, se sobrescribe con override.

Ejemplo

```csharp
public class Animal
{
public string Nombre { get; set; }

    public virtual void HacerSonido()
    {
        Console.WriteLine($"{Nombre} hace un sonido.");
    }

}

public class Perro : Animal
{
    public override void HacerSonido()
    {
        Console.WriteLine($"{Nombre} dice: ¡Guau!");
    }
}

public class Gato : Animal
{
    public override void HacerSonido()
    {
        Console.WriteLine($"{Nombre} dice: ¡Miau!");
    }
}
```

Uso

```csharp
List<Animal> animales = new List<Animal>
{
    new Perro { Nombre = "Firulais" },
    new Gato { Nombre = "Michi" }
};

foreach (var animal in animales)
{
    animal.HacerSonido(); // Ejecuta la versión correspondiente
}
```

Salida

```plaintext
Firulais dice: ¡Guau!
Michi dice: ¡Miau!
```

## Clases abstractas

Una clase abstracta no puede instanciarse y sirve como plantilla para otras clases.

```csharp
public abstract class Figura
{
    public abstract double CalcularArea();
}

public class Rectangulo : Figura
{
    public double Ancho { get; set; }
    public double Alto { get; set; }

    public override double CalcularArea()
    {
        return Ancho * Alto;
    }

}
```

## Tarea

Crear una clase base Vehiculo con propiedades Marca y Modelo, y un método Conducir().

Crear clases hijas Auto y Moto que sobreescriban Conducir() con un mensaje personalizado.

Crear una lista de Vehiculo y recorrerla mostrando el comportamiento polimórfico.

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/csharp">Volver</a>
</p>
