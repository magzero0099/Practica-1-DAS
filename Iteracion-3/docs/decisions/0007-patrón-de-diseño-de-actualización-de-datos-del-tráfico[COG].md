# Patrón de diseño actualización de datos del tráfico

* Status: proposed
* Deciders: Gonzalo Fernández de Córdoba García y Rodrigo Fernández de Córdoba García
* Date: 2025-11-05

## Context and Problem Statement

La aplicación recibe y manipula datos de tráfico en tiempo real desde un servicio externo, para el cálculo de rutas de reparto óptimas.

## Decision Drivers

* RF5.2 Recibir información del tráfico desde un servicio externo

## Considered Options

* Patrón Observer

## Decision Outcome

Chosen option: "Patrón Observer", because Permite que nuestra aplicación reaccione automáticamente cuando llegan nuevos datos de tráfico en tiempo real

### Positive Consequences

* Evita la consulta constante del servicio externo para la obtención de datos

## Pros and Cons of the Options

### Patrón Observer

Patrón de diseño de comportamiento que permite que diferentes partes del sistema se mantengan actualizadas automáticamente cuando se reciben datos del tráfico.

* Good, because Mantiene actualizado en tiempo real los datos del tráfico en nuestro sistema
* Good, because Evita consultas de los datos del tráfico innecesarias
* Good, because Notifica a los componentes de nuestro sistema que hay nuevos datos y deben actualizarse.
* Bad, because Poco recomendado si se reciben muchos datos del tráfico en poco tiempo
