# Patrón de diseño de almacenamiento y tratamiento de datos personales

* Status: proposed
* Deciders: Daniel Hernanz Corral y Marcos Hernandez Martín
* Date: 2025-11-01

## Context and Problem Statement

La aplicación almacenará los datos personales del cliente: ID, nombre, apellidos y correo electrónico; y dará opciones de tratamiento: consulta y modificación y los pedidos de los clientes: ID, lista de productos, peso del bulto y fase en la que se encuentra; y permitirá opciones de tratamiento: consulta y devolución. La aplicación podra usar estos datos obteniendolos del sistema de almacenamiento.

## Decision Drivers

* RF2 Almacenamiento y tratamiento de los datos personales de los clientes.
* RF3 Almacenamiento y tratamiento de los pedidos de los clientes.


## Considered Options

* Patrón adapter
* Patrón Singleton

## Decision Outcome

Chosen option: "Patrón adapter", because Permite utilizar sistemas de almacenamiento que tengan cualquier formato ya que lo podremos adaptar a través de este patrón a nuestra aplicación.

### Positive Consequences

* Permite cambiar la base de datos sin modificar la lógica de negocio.
* Todas las operaciones pasan por el adaptador, estandarizando la comunicación y evitando duplicación de código.

### Negative Consequences

* Cada cambio en la base de datos puede requerir la modificación/actualización del adaptador

## Pros and Cons of the Options

### Patrón adapter

Patrón de diseño estructural que permite comunicar el sistema de almacenamiento con nuestra aplicación a través de una interfaz.

* Good, because En el caso de que los datos personales tengan que ser guardados en otro formato, el patrón adapter traduciría ese formato al usado en la aplicación evitando errores de incompatibilidad.
* Bad, because Cada cambio en la base de datos o en la estructura de datos puede requerir actualizar el adaptador.

### Patrón Singleton

Patrón de diseño creacional que permite un punto de acceso global y único al sistema de almacenamiento de nuestra aplicación

* Good, because Evita abrir y cerrar conexiones constantemente, lo que reduce consumo de memoria y procesamiento.
* Good, because Al centralizar el acceso a la base de datos, se facilita la implementación de políticas de conexión segura y manejo de credenciales.
* Bad, because Si se concentra demasiada funcionalidad en la clase Singleton, se rompe el principio de responsabilidad única, haciendo la clase difícil de mantener.
