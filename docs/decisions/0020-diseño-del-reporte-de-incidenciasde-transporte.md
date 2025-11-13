# Diseño del reporte de incidenciasde transporte

* Status: proposed
* Date: 2025-11-13

## Context and Problem Statement

La aplicación permite reportar incidencias ocurridas en el transporte de mercancía, por ejemplo, camión averiado o reparto no realizado. Además de la incidencia, se guardarán la fecha y hora y el estado de la incidencia (resuelta, en tratamiento, no resuelta). Necesitamos encontrar una manera para que se puedan representar y reportar incidencias en el sistema

## Decision Drivers

* RF7.1 Reportar incidencias de transporte.

## Considered Options

* Representar el sistema de reporte de incidencias en el transporte mediante clases

## Decision Outcome

Chosen option: "Representar el sistema de reporte de incidencias en el transporte mediante clases", because Esta opción permite modelar de forma clara y mantenible los distintos elementos del proceso de gestión de incidencias.

### Positive Consequences

* Garantiza una estructura entendible y modular para el reporte de incidencias y su notificación.

## Pros and Cons of the Options

### Representar el sistema de reporte de incidencias en el transporte mediante clases

Se representará el sistema de reporte de incidencias en el transporte mediante las clases SistemaIncidencias, Incidencia y gestorRutas. La clase SistemaIncidencias es la que permite el reporte de incidencias y además notifica a los gestores de rutas cuando se haya reportado una. La clase incidencia contendrá la descripción, la fecha y el estado de la incidencia. Los estados en los que puede estar la incidencia son: Resuelta, en tratamiento, no resuelta. La clase gestorRutas contendrá la id del gestor de rutas. Al area de incidencias solo podrán acceder los gestores de rutas.

* Good, because Encapsulamiento de responsabilidades: cada clase cumple el principio de responsabilidad única
