---
layout: ../../../layouts/BlogLayout.astro
title: Operadores
---

# Operadores

Los operadores son símbolos que indican al compilador que realice una operación sobre uno o más valores (operandos).

En C# tenemos tres grandes grupos:

## Operadores aritméticos

Se usan para hacer operaciones matemáticas.

| Operador | Uso                        | Ejemplo  | Resultado |
| -------- | -------------------------- | -------- | --------- |
| `+`      | Suma                       | `5 + 3`  | `8`       |
| `-`      | Resta                      | `10 - 4` | `6`       |
| `*`      | Multiplicación             | `2 * 3`  | `6`       |
| `/`      | División                   | `8 / 2`  | `4`       |
| `%`      | Módulo (resto de división) | `7 % 3`  | `1`       |

Ejemplo práctico

```csharp
int a = 10;
int b = 3;

Console.WriteLine(a + b); // 13
Console.WriteLine(a - b); // 7
Console.WriteLine(a * b); // 30
Console.WriteLine(a / b); // 3 (división entera)
Console.WriteLine(a % b); // 1 (resto)
```

## Operadores de asignación

Sirven para asignar valores a variables y también combinarlos con operaciones.

| Operador | Ejemplo  | Equivalente a |
| -------- | -------- | ------------- |
| `=`      | `x = 5`  | —             |
| `+=`     | `x += 3` | `x = x + 3`   |
| `-=`     | `x -= 2` | `x = x - 2`   |
| `*=`     | `x *= 4` | `x = x * 4`   |
| `/=`     | `x /= 2` | `x = x / 2`   |

### Ejemplo práctico

```csharp
int x = 5;
x += 3; // ahora x es 8
x *= 2; // ahora x es 16
Console.WriteLine(x);
```

## Operadores de comparación

Se usan para comparar valores. Devuelven un bool (true o false).

| Operador | Ejemplo  | Resultado |
| -------- | -------- | --------- |
| `==`     | `5 == 5` | `true`    |
| `!=`     | `5 != 3` | `true`    |
| `>`      | `7 > 4`  | `true`    |
| `<`      | `2 < 5`  | `true`    |
| `>=`     | `5 >= 5` | `true`    |
| `<=`     | `3 <= 4` | `true`    |

### Ejemplo práctico

```csharp
int edad = 18;
Console.WriteLine(edad >= 18); // true
Console.WriteLine(edad < 18);  // false
```

## Operadores lógicos

Se usan para combinar condiciones.

| Operador | Significado | Ejemplo                | Resultado |
| -------- | ----------- | ---------------------- | --------- |
| `&&`     | AND (y)     | `(5 > 3) && (2 < 4)`   | `true`    |
| `\|\|`   | OR (o)      | `(5 > 3) \|\| (2 > 4)` | `true`    |
| `!`      | NOT (no)    | `!(5 > 3)`             | `false`   |

## Ejemplo práctico combinado

Programa que verifique si una persona puede votar.

```csharp
Console.WriteLine("¿Cuál es tu edad?");
int edad = int.Parse(Console.ReadLine());

bool puedeVotar = edad >= 16 && edad <= 120;

Console.WriteLine($"¿Puede votar? {puedeVotar}");
```

### Explicación

- `edad >= 16` → Comprueba si la edad es mayor o igual a 16.
- `edad <= 120` → Comprueba que no sea una edad irrealmente alta.
- `&&` → Ambas condiciones deben cumplirse para que el resultado sea true.

### Tarea práctica

Programa que pida dos números y muestre:

- La suma
- La resta
- La multiplicación
- El mayor de los dos números

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/csharp">Volver</a>
</p>
