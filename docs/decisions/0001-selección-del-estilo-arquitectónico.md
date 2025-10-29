# Selección del Estilo Arquitectónico

* Status: proposed
* Deciders: Marcos Hernández Martín y Daniel Hernanz Corral
* Date: 2025-10-25

## Context and Problem Statement

Diseñar una aplicación que gestione los procesos de compra de la compañía y que se divida en diferentes módulos: Datos de Clientes, Datos de Pedidos, Rutas y Repartos, Estadísticas, Incidencias y Pagos.

## Decision Drivers

* RF1 Plataforma de compra de productos alimenticios online.

## Considered Options

* Estilo Cliente-Servidor
* Monolito Modular

## Decision Outcome

Chosen option: "Estilo Cliente-Servidor", because En un contexto en el que los requisitos no funcionales no se consideran, un estilo arquitectónico de microservicios o SOA quedaría pobre al orientarse sus patrones principalmente a esta clase de requisitos.

### Positive Consequences

* Organización del backend más centralizada.
* Soporta múltiples clientes con distintas interfaces según el tipo de usuario.
* No es necesario comunicar los módulos mediante APIs

### Negative Consequences

* Mayor complejidad de seguridad.

## Pros and Cons of the Options

### Estilo Cliente-Servidor

Estilo arquitectónico en el que un servidor ofrece el servicio y un cliente le realiza peticiones.

* Good, because La centralización encaja en nuestro contexto porque se trata de ofrecer un servicio de compra-venta y seguimiento de pedidos a un conjunto de clientes.
* Good, because Podemos diseñar un servidor que contenga los diferentes módulos como clases con responsabilidad.
* Bad, because Despliegue más complejo.
* Bad, because Infraestructura más costosa.

### Monolito Modular

Toda la lógica de negocio se centra en un mismo bloque, es decir, el código del cliente y del servidor se encuentran en un mismo monolito lógico. La lógica de negocio se organiza en módulos, dentro del monolito.

* Good, because Menos complejidad de despliegue.
* Good, because No hay que preocuparse por la comunicación cliente-servidor.
* Bad, because El servicio depende de un sólo sistema.
* Bad, because No apto para muchos usuarios concurrentes.
* Bad, because Integración con servicios de terceros complicada.
