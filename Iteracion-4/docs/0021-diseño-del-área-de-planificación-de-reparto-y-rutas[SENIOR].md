# Diseño del Área de planificación de reparto y rutas

* Status: proposed
* Deciders: Marcos Hernandez, Daniel Hernanz Corral
* Date: 2025-11-13

## Context and Problem Statement

La aplicación implementará un área de planificación de reparto y rutas que se encargará de asignar repartos a la flota de repartidores y planificar las rutas óptimas de reparto de los camiones. Necesitamos encontrar una manera de representar las rutas de los repartos.

## Decision Drivers

* RF5 Área de planificación de reparto y rutas.

## Considered Options

* Representar el área de planificación de reparto y rutas mediante clases

## Decision Outcome

Chosen option: "Representar el área de planificación de reparto y rutas mediante clases", because proporciona una estructura más clara, mantenible y extensible para modelar los distintas clases (camión, ruta y reparto)

### Positive Consequences

* Garantiza una estructura entendible y modular para la planificación de los repartos.
* Esta separación facilita la incorporación de nuevos algoritmos de reparto
* Mejora la reutilización en otros módulos como el de incidencias

## Pros and Cons of the Options

### Representar el área de planificación de reparto y rutas mediante clases

Se representará el area de planificación de reparto y rutas mediante las clases ruta,camión y reparto. La clase reparto contendra la ruta, y el camión del reparto. La clase camión contendra el espacio que tiene disponible para repartir. La clase ruta contendrá la ruta escogida, el tiempo que tardará en hacer la ruta. Además la clase ruta calculará la ruta óptima en función del tipo de ruta y la capacidad del camión.

* Good, because Cada clase (ruta, camión, reparto) tiene una responsabilidad bien definida, lo que mejora la cohesión y reduce el acoplamiento.
* Good, because Facilita la depuración y pruebas unitarias, ya que cada clase se puede testear de forma independiente
* Good, because Implementación sencilla
* Good, because facilita reutilización
* Bad, because Cambios en la lógica de una clase pueden afectar a otras partes del sistema si no se mantiene una separación clara
