# Patrón de diseño recibimiento de datos del tráfico

* Status: proposed
* Deciders: Daniel Hernanz Corral y Marcos Hernandez Martín
* Date: 2025-11-01

## Context and Problem Statement

La aplicación recibe y manipula datos de tráfico en tiempo real desde un servicio externo, para el cálculo de rutas de reparto óptimas.

## Decision Drivers

* RF5.2 Recibir información del tráfico desde un servicio externo

## Considered Options

* Patrón Facade
* Patrón Adapter
* Patrón Observer

## Decision Outcome

Chosen option: "Patrón observer", because Permite que nuestra aplicación reaccione automáticamente cuando llegan nuevos datos de tráfico en tiempo real

### Positive Consequences

* Evita la consulta constante del servicio externo para la obtención de datos

## Pros and Cons of the Options

### Patrón Facade

Patrón de diseño que proporciona una interfaz simplificada a una biblioteca con muchas funciones

* Good, because Simplifica la obtención de información del tráfico por parte del servicio externo
* Bad, because La información puede venir en otro formato y no ser compatible
* Bad, because Si el servicio externo no proporciona demasiadas opciones para la extracción de datos del tráfico, este patrón puede no ser tan necesario.

### Patrón Adapter

Patrón de diseño que permite adaptar el formato de datos del servicio externo al de nuestro sistema.

* Good, because En el caso en el que el servicio externo cambie el formato sobre como estan expresados los datos del tráfico, es facil solucionar el problema de incompatibilidad.
* Bad, because Hay que mantener más codigo.

### Patrón Observer

Patrón de diseño de comportamiento que permite que diferentes partes del sistema se mantengan actualizadas automáticamente cuando se reciben datos del tráfico.

* Good, because Mantiene actualizado en tiempo real los datos del tráfico en nuestro sistema
* Good, because Evita consultas de los datos del tráfico innecesarias
* Good, because Notifica a los componentes de nuestro sistema que hay nuevos datos y deben actualizarse.
* Bad, because Poco recomendado si se reciben muchos datos del tráfico en poco tiempo
