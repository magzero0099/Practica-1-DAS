# Patrón de diseño recibimiento de datos del tráfico

* Status: accepted
* Deciders: Daniel Hernanz Corral y Marcos Hernández Martín
* Date: 2025-11-01

## Context and Problem Statement

La aplicación recibe y manipula datos de tráfico en tiempo real desde un servicio externo, para el cálculo de rutas de reparto óptimas.

## Decision Drivers

* RF5.2 Recibir información del tráfico desde un servicio externo

## Considered Options

* Patrón Adapter
* Patrón Facade

## Decision Outcome

Chosen option: "Patrón Adapter", because Adapta el formato de los datos proporcionados por el servicio externo a nuestro modelo interno de datos

### Positive Consequences

* El cambio de formato por parte del servicio externo o de nuestra aplicación sería facil de solucionar
* Se puedrán crear adaptadores para diferentes servicios externos en caso de necesitarlos.

## Pros and Cons of the Options

### Patrón Adapter

Patrón de diseño que permite adaptar el formato de datos del servicio externo al de nuestro sistema.

* Good, because En el caso en el que el servicio externo cambie el formato sobre como estan expresados los datos del tráfico, es facil solucionar el problema de incompatibilidad.
* Good, because Es compatible con el uso de un patrón observer para recibir la información del servicio externo.
* Bad, because Hay que mantener más codigo.

### Patrón Facade

Patrón de diseño que proporciona una interfaz simplificada a una biblioteca con muchas funciones

* Good, because Simplifica la obtención de información del tráfico por parte del servicio externo.
* Good, because Permite recortar información y proporcionar solo lo necesario en tiempo real.
* Bad, because La información puede venir en otro formato y no ser compatible
* Bad, because No funciona si se quiere usar a la vez que el patrón observer. Si es el servicio externo el que envía información la aplicación no va a realizar consultas.

