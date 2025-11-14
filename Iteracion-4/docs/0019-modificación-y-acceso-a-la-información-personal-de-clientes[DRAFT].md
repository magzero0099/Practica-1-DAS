# Patrón de diseño de modificación y acceso a la información personal de clientes

* Status: proposed
* Deciders: Rodrigo Fernández de Córdoba García
* Date: 2025-11-12

## Context and Problem Statement

Los datos personales de los clientes guardados por la aplicación son necesarios para guardar información sobre los usuarios, permitiéndoles rastrear sus pedidos, comprobar su historial de pedidos, etc. Por eso es conveniente definir un mecanismo seguro de consulta y modificación de los datos guardados.

## Decision Drivers

* RF2 Almacenamiento y tratamiento de los datos personales de los clientes.

## Considered Options

* Uso de un patrón proxy

## Decision Outcome

Chosen option: "Uso de un patrón proxy", because aporta un mecanismo de consulta de los datos responsable del control del tráfico, permisos etc. Reduciendo el acomplamiento con los elementos que requieren información de los clientes

### Positive Consequences

* Permite guardar los datos relevantes al proceso en el proxy para reducir el número de consultas a la base de datos
* Permite guardar temporalmente las consultas o modificaciones que se quieran realizar en el caso de que no sea posible acceder al fichero necesario
* Permite a los proxy implementar métodos para manejar conflictos o problemas de concurrencia

### Negative Consequences

* Más latencia cuando no hay varios accesos abiertos al fichero
* Aumenta el uso de memoria principal

## Pros and Cons of the Options

### Uso de un patrón proxy

Patrón de diseño que proporciona intermediarios para gestionar el acceso y tratamiento de los datos personales de los clientes abstrayendose de la estructura en la que se almacenan los datos.

* Good, because Permite a los proxy implementar métodos para manejar conflictos o problemas de concurrencia
* Good, because Permite al resto del sistema abstraerse del método de almacenamiento o tratamiento de los datos.
* Good, because Permite hacer es más rápido cuando se va a acceder a un mismo conjunto de datos varias veces (caching).
* Bad, because aumenta el uso de memoria.
