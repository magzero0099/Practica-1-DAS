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

* Patrón Adapter
* Patrón Singleton

## Decision Outcome

Chosen option: "Patrón Singleton", because Garantiza que exista una única instancia de conexión al sistema de almacenamiento, centralizando la gestión de los clientes y pedidos almacenados.

### Positive Consequences

* Se reutiliza la misma conexión durante la vida de la aplicación, reduciendo el número de apertura y cierre de conexiones con el sistema de guardado.

### Negative Consequences

* La instancia permanece en memoria durante toda la ejecución, incluso si no se está usando activamente.

## Pros and Cons of the Options

### Patrón Adapter

Patrón de diseño estructural que permite comunicar el sistema de almacenamiento con nuestra aplicación a través de una interfaz.

* Good, because En el caso de que los datos personales tengan que ser guardados en otro formato, el patrón adapter traduciría ese formato al usado en la aplicación evitando errores de incompatibilidad.
* Bad, because Cada cambio en la base de datos o en la estructura de datos puede requerir actualizar el adaptador.

### Patrón Singleton

Patrón de diseño creacional que permite un punto de acceso global y único al sistema de almacenamiento de nuestra aplicación

* Good, because Evita abrir y cerrar conexiones constantemente, lo que reduce consumo de memoria y procesamiento.
* Good, because Al centralizar el acceso a la base de datos, se facilita la implementación de políticas de conexión segura y manejo de credenciales.
* Bad, because Si se concentra demasiada funcionalidad en la clase Singleton, se rompe el principio de responsabilidad única, haciendo la clase difícil de mantener.
