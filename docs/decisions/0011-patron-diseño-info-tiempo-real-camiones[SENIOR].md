# Patron diseño info tiempo real camiones

* Status: proposed
* Date: 2025-11-05

## Context and Problem Statement

La aplicación proporciona información acerca de la ubicación del camión, el tiempo que le falta para llegar al siguiente destino y el número de pedidos que le faltan por entregar.
Para ello, necesitamos que nuestro sistema quede pendiente de la llegada de nueva información desde el servicio externo de tráfico.

## Decision Drivers

* RF6.2 Proporcionar información en tiempo real de los camiones.

## Considered Options

* Patrón Observer

## Decision Outcome

Chosen option: "Patrón Observer", because permite notificar cambios en la ubicación, tiempo que le falta para llegar a destino, y el número de pedidos que le faltan por entregar en tiempo real.

### Positive Consequences

* El sistema siempre muestra información actualizada

## Pros and Cons of the Options

### Patrón Observer

Patrón de diseño de comportamiento que permite notificar en tiempo real información acerca del camión de reparto. Los subscriptores serán los clientes que se conecten al módulo de estadísticas, mientras que el notificador será el servidor de nuestro sistema.

* Good, because Los clientes reciben información en tiempo real aceca de los camiones sin necesidad de realziar consultas constantes.
* Bad, because Si se conectan muchos clientes al módulo de estadisticas, pueden haber demasiados suscriptores que saturen el sistema.
