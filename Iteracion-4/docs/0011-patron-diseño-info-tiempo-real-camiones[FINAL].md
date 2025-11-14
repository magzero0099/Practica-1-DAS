# Patron diseño info tiempo real estadisticas

* Status: rejected
* Deciders: Rodrigo Fernández de Córdoba García, Daniel Hernanz Corral y Marcos Hernandez Martín
* Date: 2025-11-11

## Context and Problem Statement

En el módulo de estadísticas, se necesita que los clientes que se conecten reciban información en tiempo real acerca del estado de los pedidos (preprocesado del pedido, autorización y aceptación) y la ubicación, tiempo para llegar y número de pedidos por entregar por parte de los camiones.

## Decision Drivers

* RF6.2 Proporcionar información en tiempo real de los camiones.
* RF6.1 Proporcionar estadísticas e información sobre el estado de los pedidos.

## Considered Options

* Patrón Observer

## Decision Outcome

Chosen option: "Patrón Observer", because Permite notificar cambios en la ubicación, tiempo que le falta para llegar a destino, y el número de pedidos que les faltan por entregar a los camiones; así como la fase en la que se encuentran los pedidos, todo ello en tiempo real.

### Positive Consequences

* El sistema siempre muestra información actualizada
* Se pueden aportar los datos del sistema de tráfico externo para el cálculo de tiempo restante
* El sistema permite enviar notificaciones a los clientes sobre sus pedidos. (Se ha entregado, está en reparto...) sin que tengan que acceder al área de estadísticas


## Pros and Cons of the Options

### Patrón Observer

Patrón de diseño de comportamiento que permite notificar en tiempo real información acerca de los camiones y estados de los pedidos. Los suscriptores serán los clientes que se conecten al módulo de estadísticas, mientras que el notificador será el servidor de nuestro sistema.

* Good, because Los clientes reciben información en tiempo real aceca de los camiones y del estado del pedido sin necesidad de realizar consultas constantes.
* Good, because Los clientes reciben información en tiempo real aceca de los pedidos sin necesidad de realizar consultas constantes.
* Bad, because Si se conectan muchos clientes al módulo de estadisticas, puede haber demasiados suscriptores que saturen el sistema.
* Bad, because Si se producen demasiados cambios de ruta o entregas se puede saturar el sistema de notificaciones
