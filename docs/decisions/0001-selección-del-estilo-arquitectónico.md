# Selección del Estilo Arquitectónico

* Status: proposed
* Deciders: Marcos Hernández Martín y Daniel Hernanz Corral
* Date: 2025-10-25

## Context and Problem Statement

Diseñar una aplicación que gestione los procesos de compra de la compañía y que se divida en diferentes módulos: Datos de Clientes, Datos de Pedidos, Rutas y Repartos, Estadísticas, Incidencias y Pagos.

## Decision Drivers

* RF1 Plataforma de compra de productos alimenticios online.

## Considered Options

* Estilo Orientado a Servicios (SOA)
* Estilo por Microservicios
* Estilo Cliente-Servidor

## Decision Outcome

Chosen option: "Estilo Cliente-Servidor", because En un contexto en el que los requisitos no funcionales no son relevantes, un estilo arquitectónico de microservicios o SOA quedaría pobre al orientarse sus patrones principalmente de esta clase de requisitos.

### Positive Consequences

* División de la lógica de negocio en microservicios con bajo acomplamiento.
* Al ser módulos aislados, el diseño de cada microservicio será más cómodo.
* Fallos aislados que en un servicio no comprometerían al resto de servicios de la lógica de negocio.

### Negative Consequences

* Para trabajar con servicios de terceros como STRIPE o la plataforma de tráfico será necesario implementar un microservicio específico que comunique el microservicio adecuado con el servicio externo.

## Pros and Cons of the Options

### Estilo Orientado a Servicios

Arquitectura que separa las diferentes funciones del sistema en servicios, con baja acoplación y capacidad de coumincación entre servicios.

* Good, because La lógica de negocio del sistema se divide en diferentes áreas, que pueden establecerse como servicios.
* Good, because Independencia de cada servicio con el resto del sistema, incluyendo recursos o infraestructura.
* Good, because Adecuado para comunicación con servicios de terceros, debido a que los módulos son centralizados en sí mismos.
* Bad, because Fallos en un servicio pueden afectar a varias funciones, al tratarse de servicios grandes que se corresponden con las áreas que se pretende que cubra el sistema.
* Bad, because Existencia de servicio orquestador que comunica el flujo de negocio entre todos los servicios: existe cierto grado de acoplamiento.

### Estilo por Microservicios

División de la lógica de negocio en servicios muy pequeños.

* Good, because La lógica de negocio de nuetro contexto se puede dividir en microservicios, incluso las diferentes áreas de las que el enunciado habla pueden subdividirse en microservicios en lugar de hacer una correspondencia directa área-servicio.
* Good, because Muy sencillo añadir nuevos servicios o módulos
* Good, because los errores son aislados al estar las funciones de la lógica de negocio separadas en microservicios.
* Bad, because Comunicación con terceros complicada: cada microservicio debe integrarse con el servicio de terceros o incluso necesitarse un microservicio dedicado a la comunicación externa.
* Bad, because Generaría problemas de diseño adicionales para gestionar correctamente los microservicios.
* Bad, because Los patrones de diseño de microservicios se orientan en su mayoría en requsitos no funcionales, los cuales no son relevantes en nuestro problema.

### Estilo Cliente-Servidor

Estilo arquitectónico en el que un servidor ofrece el servicio y un cliente le realiza peticiones.

* Good, because La centralización encaja en nuestro contexto porque se trata de ofrecer un servicio de compra-venta y seguimiento de pedidos a un conjunto de clientes.
* Good because, porque podemos diseñar un monolito que contenga los diferentes módulos como clases con responsabilidad.
* Bad, because Arquitectura monolítica: la lógica de negocio está en el servidor. Aunque se pueda modularizar la lógica de negocio, el acoplamiento es muy alto.
* Bad, because Integración con terceros muy complicada, al tener que integrarse el sistema completo y no sólo un módulo.