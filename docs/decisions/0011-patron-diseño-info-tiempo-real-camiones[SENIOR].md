# Patron diseño info tiempo real estadisticas

* Status: proposed
* Date: 2025-11-05

## Context and Problem Statement

En el módulo de estadísticas, se necesita que los clientes que se conecten reciban información en tiempo real acerca del estado de los pedidos (preprocesado del pedido, autorización y aceptación) y la ubicación, tiempo para llegar y número de pedidos por entregar por parte de los camiones.

## Decision Drivers

* RF6.2 Proporcionar información en tiempo real de los camiones.
* RF6.1 Proporcionar estadísticas e información sobre el estado de los pedidos.

## Considered Options

* Patrón Observer

## Decision Outcome

Chosen option: "Patrón Observer", because permite notificar cambios en la ubicación, tiempo que le falta para llegar a destino, y el número de pedidos que les faltan por entregar a los camiones; así como la fase en la que se encuentran los pedidos, todo ello en tiempo real.

### Positive Consequences

* El sistema siempre muestra información actualizada

## Pros and Cons of the Options

### Patrón Observer

Patrón de diseño de comportamiento que permite notificar en tiempo real información acerca de los camiones y estados de los pedidos. Los suscriptores serán los clientes que se conecten al módulo de estadísticas, mientras que el notificador será el servidor de nuestro sistema.

* Good, because Los clientes reciben información en tiempo real aceca de los camiones y del estado del pedido sin necesidad de realizar consultas constantes.
* Good, because Los clientes reciben información en tiempo real aceca de los pedidos sin necesidad de realizar consultas constantes.
* Bad, because Si se conectan muchos clientes al módulo de estadisticas, pueden haber demasiados suscriptores que saturen el sistema.
