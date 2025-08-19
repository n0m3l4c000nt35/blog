---
layout: ../../../layouts/BlogLayout.astro
title: Comentarios
---

# Comentarios

<hr>

## Etiquetas Principales

- `<summary>` - Descripción principal del elemento
- `<param>` - Describe parámetros de métodos
- `<returns>` - Describe el valor de retorno
- `<exception>` - Documenta excepciones que puede lanzar

## Etiquetas de Estructura

- `<para>` - Crear párrafos y saltos de línea
- `<list>` - Listas (bullet, number, table)
- `<item>` - Elementos de lista
- `<description>` - Descripción en elementos de lista

## Etiquetas de Referencias

- `<see cref="">` - Referencia a clases, métodos, propiedades
- `<seealso cref="">` - Referencias relacionadas
- `<paramref name="">` - Referencia a parámetros
- `<typeparam>` - Documenta parámetros genéricos

## Etiquetas de Código

- `<c>` - Código inline
- `<code>` - Bloques de código
- `<example>` - Ejemplos de uso

## Etiquetas Adicionales

- `<remarks>` - Información adicional o notas
- `<value>` - Para propiedades, describe el valor
- `<permission>` - Permisos de seguridad requeridos
- `<include>` - Incluir documentación externa

## Ejemplos

```csharp
using System;
using System.Collections.Generic;
using System.Threading.Tasks;

/// <summary>
/// Servicio para el manejo de transacciones financieras y cálculos contables.
/// <para>
/// Proporciona funcionalidades para procesar pagos, calcular impuestos y
/// generar reportes financieros con alta precisión decimal.
/// </para>
/// </summary>
/// <remarks>
/// Esta clase implementa patrones de diseño Repository y Unit of Work.
/// Todos los cálculos utilizan <see cref="decimal"/> para evitar errores de redondeo.
/// </remarks>
/// <example>
/// <code>
/// var servicio = new FinancialService(context);
/// var resultado = await servicio.ProcesarPagoAsync(100m, 0.21m);
/// </code>
/// </example>
public class FinancialService
{
    private readonly IDbContext _context;

    /// <summary>
    /// Inicializa una nueva instancia de <see cref="FinancialService"/>.
    /// </summary>
    /// <param name="context">Contexto de base de datos para operaciones CRUD.</param>
    /// <exception cref="ArgumentNullException">
    /// Se produce cuando <paramref name="context"/> es <c>null</c>.
    /// </exception>
    public FinancialService(IDbContext context)
    {
        _context = context ?? throw new ArgumentNullException(nameof(context));
    }

    /// <summary>
    /// Procesa un pago aplicando impuestos y comisiones bancarias.
    /// <para>
    /// El método calcula automáticamente todos los conceptos fiscales aplicables
    /// según la configuración regional del sistema.
    /// </para>
    /// </summary>
    /// <param name="monto">
    /// El monto base del pago sin impuestos. Debe ser mayor que cero.
    /// </param>
    /// <param name="tasaImpuesto">
    /// La tasa de impuesto como valor decimal (ej: 0.21 para 21%).
    /// Valor típico entre 0.0 y 1.0.
    /// </param>
    /// <param name="metodoPago">
    /// El método de pago seleccionado. Ver <see cref="MetodoPago"/> para opciones válidas.
    /// </param>
    /// <returns>
    /// Una tarea que representa la operación asíncrona.
    /// El valor de la tarea contiene un <see cref="ResultadoPago"/> con el detalle completo.
    /// </returns>
    /// <exception cref="ArgumentOutOfRangeException">
    /// Se produce cuando <paramref name="monto"/> es menor o igual a cero,
    /// o cuando <paramref name="tasaImpuesto"/> está fuera del rango válido.
    /// </exception>
    /// <exception cref="InvalidOperationException">
    /// Se produce cuando el <paramref name="metodoPago"/> no está disponible
    /// o cuando hay problemas de conectividad con el procesador de pagos.
    /// </exception>
    /// <exception cref="TimeoutException">
    /// Se produce cuando la operación excede el tiempo límite de 30 segundos.
    /// </exception>
    /// <example>
    /// <code>
    /// // Procesar un pago con tarjeta de crédito
    /// var resultado = await servicio.ProcesarPagoAsync(
    ///     monto: 1000m,
    ///     tasaImpuesto: 0.21m,
    ///     metodoPago: MetodoPago.TarjetaCredito
    /// );
    ///
    /// if (resultado.Exitoso)
    /// {
    ///     Console.WriteLine($"Pago procesado: {resultado.MontoTotal:C}");
    /// }
    /// </code>
    /// </example>
    /// <seealso cref="CalcularImpuestos(decimal, decimal)"/>
    /// <seealso cref="ValidarMetodoPago(MetodoPago)"/>
    public async Task<ResultadoPago> ProcesarPagoAsync(
        decimal monto,
        decimal tasaImpuesto,
        MetodoPago metodoPago = MetodoPago.Efectivo)
    {
        // Implementación del método...
        return new ResultadoPago();
    }

    /// <summary>
    /// Calcula los impuestos aplicables sobre un monto base.
    /// </summary>
    /// <param name="montoBase">El monto sobre el cual calcular impuestos.</param>
    /// <param name="tasa">La tasa de impuesto como decimal.</param>
    /// <returns>El monto de impuestos calculado.</returns>
    /// <remarks>
    /// Este método utiliza <see cref="Math.Round(decimal, int)"/> con
    /// <see cref="MidpointRounding.AwayFromZero"/> para el redondeo.
    /// </remarks>
    /// <example>
    /// <code>
    /// decimal impuesto = CalcularImpuestos(100m, 0.21m); // Resultado: 21.00
    /// </code>
    /// </example>
    private decimal CalcularImpuestos(decimal montoBase, decimal tasa)
    {
        return Math.Round(montoBase * tasa, 2, MidpointRounding.AwayFromZero);
    }

    /// <summary>
    /// Obtiene el historial de transacciones para un cliente específico.
    /// </summary>
    /// <param name="clienteId">ID único del cliente.</param>
    /// <param name="fechaInicio">Fecha de inicio del período de consulta (inclusive).</param>
    /// <param name="fechaFin">
    /// Fecha de fin del período de consulta (inclusive).
    /// Si es <c>null</c>, se usa la fecha actual.
    /// </param>
    /// <returns>
    /// Una colección de <see cref="Transaccion"/> ordenada por fecha descendente.
    /// Retorna una colección vacía si no se encuentran transacciones.
    /// </returns>
    /// <exception cref="ArgumentException">
    /// Se produce cuando <paramref name="clienteId"/> es menor que 1,
    /// o cuando <paramref name="fechaInicio"/> es posterior a <paramref name="fechaFin"/>.
    /// </exception>
    /// <permission cref="System.Security.Permissions.SecurityAction.Demand">
    /// Requiere permisos de lectura de datos financieros.
    /// </permission>
    /// <example>
    /// <code>
    /// var transacciones = await servicio.ObtenerHistorialAsync(
    ///     clienteId: 123,
    ///     fechaInicio: DateTime.Today.AddDays(-30),
    ///     fechaFin: DateTime.Today
    /// );
    ///
    /// foreach (var transaccion in transacciones)
    /// {
    ///     Console.WriteLine($"{transaccion.Fecha}: {transaccion.Monto:C}");
    /// }
    /// </code>
    /// </example>
    public async Task<IEnumerable<Transaccion>> ObtenerHistorialAsync(
        int clienteId,
        DateTime fechaInicio,
        DateTime? fechaFin = null)
    {
        // Implementación...
        return new List<Transaccion>();
    }

    /// <summary>
    /// Valida si un método de pago está disponible y configurado correctamente.
    /// </summary>
    /// <param name="metodo">El método de pago a validar.</param>
    /// <returns>
    /// <c>true</c> si el método de pago es válido y está disponible;
    /// de lo contrario, <c>false</c>.
    /// </returns>
    /// <remarks>
    /// <para>Criterios de validación:</para>
    /// <list type="bullet">
    /// <item><description>El método debe estar habilitado en la configuración</description></item>
    /// <item><description>Debe tener conexión con el procesador correspondiente</description></item>
    /// <item><description>Los certificados de seguridad deben estar vigentes</description></item>
    /// </list>
    /// </remarks>
    /// <example>
    /// <code>
    /// if (servicio.ValidarMetodoPago(MetodoPago.TarjetaCredito))
    /// {
    ///     // Proceder con el pago
    /// }
    /// else
    /// {
    ///     // Mostrar método no disponible
    /// }
    /// </code>
    /// </example>
    public bool ValidarMetodoPago(MetodoPago metodo)
    {
        // Implementación...
        return true;
    }

    /// <summary>
    /// Evento que se dispara cuando se completa una transacción exitosamente.
    /// </summary>
    /// <remarks>
    /// Los suscriptores deben manejar este evento de forma asíncrona para
    /// evitar bloquear el hilo principal de procesamiento.
    /// </remarks>
    /// <example>
    /// <code>
    /// servicio.TransaccionCompletada += (sender, args) =>
    /// {
    ///     Console.WriteLine($"Transacción {args.TransaccionId} completada");
    /// };
    /// </code>
    /// </example>
    public event EventHandler<TransaccionEventArgs> TransaccionCompletada;
}

/// <summary>
/// Define los métodos de pago disponibles en el sistema.
/// </summary>
/// <remarks>
/// Cada método de pago puede tener diferentes comisiones y tiempos de procesamiento.
/// </remarks>
public enum MetodoPago
{
    /// <summary>
    /// Pago en efectivo. Sin comisiones adicionales.
    /// </summary>
    Efectivo = 0,

    /// <summary>
    /// Pago con tarjeta de crédito. Comisión del 3%.
    /// </summary>
    TarjetaCredito = 1,

    /// <summary>
    /// Pago con tarjeta de débito. Comisión del 1.5%.
    /// </summary>
    TarjetaDebito = 2,

    /// <summary>
    /// Transferencia bancaria. Sin comisiones, procesamiento en 24-48hs.
    /// </summary>
    Transferencia = 3
}

/// <summary>
/// Representa el resultado de una operación de pago.
/// </summary>
/// <remarks>
/// Esta clase es inmutable una vez creada para garantizar la integridad de los datos.
/// </remarks>
public class ResultadoPago
{
    /// <summary>
    /// Obtiene un valor que indica si el pago fue procesado exitosamente.
    /// </summary>
    /// <value>
    /// <c>true</c> si el pago fue exitoso; de lo contrario, <c>false</c>.
    /// </value>
    public bool Exitoso { get; init; }

    /// <summary>
    /// Obtiene el monto total procesado, incluyendo impuestos y comisiones.
    /// </summary>
    /// <value>
    /// El monto total en la moneda del sistema.
    /// </value>
    public decimal MontoTotal { get; init; }

    /// <summary>
    /// Obtiene el identificador único de la transacción.
    /// </summary>
    /// <value>
    /// Un GUID que identifica únicamente esta transacción.
    /// Será <see cref="Guid.Empty"/> si el pago no fue exitoso.
    /// </value>
    public Guid TransaccionId { get; init; }
}

/// <summary>
/// Representa una transacción financiera en el sistema.
/// </summary>
public class Transaccion
{
    /// <summary>
    /// Obtiene o establece la fecha y hora de la transacción.
    /// </summary>
    public DateTime Fecha { get; set; }

    /// <summary>
    /// Obtiene o establece el monto de la transacción.
    /// </summary>
    public decimal Monto { get; set; }
}

/// <summary>
/// Proporciona datos para eventos relacionados con transacciones.
/// </summary>
/// <param name="transaccionId">El identificador de la transacción.</param>
/// <param name="monto">El monto de la transacción.</param>
public class TransaccionEventArgs(Guid transaccionId, decimal monto) : EventArgs
{
    /// <summary>
    /// Obtiene el identificador único de la transacción.
    /// </summary>
    public Guid TransaccionId { get; } = transaccionId;

    /// <summary>
    /// Obtiene el monto de la transacción.
    /// </summary>
    public decimal Monto { get; } = monto;
}

/// <summary>
/// Define el contrato para contextos de base de datos.
/// </summary>
public interface IDbContext
{
    // Definición de la interfaz...
}
```

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/csharp">Volver</a>
</p>
