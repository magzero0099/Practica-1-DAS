# Patrón de diseño de reporte de incidencias

* Status: proposed
* Deciders: Daniel Hernanz Corral y Marcos Hernandez Martín
* Date: 2025-11-05

## Context and Problem Statement

Se tienen varios tipos fijos de incidencias (por ejemplo camión averiado o reparto no realizado), que se pueden reportar, y cada una va a causar un comportamiento diferente al gestor que la reciba (diferentes alertas, notificaciones, etc). Necesitamos un patrón de diseño que nos permita definir una clase que puede ejecutar diferentes comportamientos según el tipo de incidencia recibida.

## Decision Drivers

* RF7.1 Reportar incidencias de transporte.

## Considered Options

* Patrón command

## Decision Outcome

Chosen option: "Patrón command", because El patrón Command permite encapsular las incidencias como objetos, lo que facilita su validación, almacenamiento temporal y reenvío en caso de desconexión, garantizando fiabilidad en un entorno cliente-servidor.

### Positive Consequences

* Según el tipo de incidencia que llegue, el area de gestión de incidencias cambiará su comportamiento para poder gestionarlas adecuadamente.

## Pros and Cons of the Options

### Patrón command

Patrón de diseño de comportamiento que convierte una operación en un objeto independiente que contiene la información de dicha operación. En este caso sería la información de la incidencia.

* Good, because Garantiza que no se pierdan las incidencias a pesar de ocurrir un fallo en el servidor, ya que puede ser reenviada.
* Good, because Se pueden validar incidencias antes de ejecutarlas.
* Bad, because Si las incidencias se ponen en cola, puede que su ejecución no sea inmediata.
