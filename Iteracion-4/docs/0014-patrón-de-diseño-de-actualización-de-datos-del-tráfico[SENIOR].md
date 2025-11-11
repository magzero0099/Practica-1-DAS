# Patrón de diseño actualización de datos del tráfico

* Status: proposed
* Deciders: Daniel Hernanz Corral y Marcos Hernandez Martín
* Date: 2025-11-11

## Context and Problem Statement

La aplicación recibe y manipula datos de tráfico en tiempo real desde un servicio externo, para el cálculo de rutas de reparto óptimas.

## Decision Drivers

* RF5.2 Recibir información del tráfico desde un servicio externo

## Considered Options

* Publisher-Subscriber

## Decision Outcome

Chosen option: "Publisher-Subscriber", because Permite que nuestra aplicación reaccione automáticamente cuando llegan nuevos datos de tráfico en tiempo real

### Positive Consequences

* Evita la consulta constante del servicio externo para la obtención de datos, por lo que sólo accederá al mismo cuando hayan nuevos datos disponibles.

## Pros and Cons of the Options

### Patrón observer

Patrón de diseño que permite que diferentes sistemas puedan monitorizar sus datos y comunicarse entre sí. Encaja en nuestro problema, pues debemos importar y monitorizar datos desde un sistema externo.
* Good, because Mantiene actualizado en tiempo real los datos del tráfico en nuestro sistema.
* Good, because Evita consultas de los datos del tráfico innecesarias
* Good, because Notifica a los componentes de nuestro sistema que hay nuevos datos y deben actualizarse.
* Bad, because Poco recomendado si se reciben muchos datos del tráfico en poco tiempo
