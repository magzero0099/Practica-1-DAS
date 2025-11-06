# Patrón de diseño de acceso al almacenamiento de datos personales

* Status: proposed
* Deciders: Gonzalo Fernández de Córdoba García y Rodrigo Fernández de Córdoba García
* Date: 2025-11-05

## Context and Problem Statement

La aplicación almacenará los datos personales del cliente: ID, nombre, apellidos y correo electrónico; y dará opciones de tratamiento: consulta y modificación y los pedidos de los clientes: ID, lista de productos, peso del bulto y fase en la que se encuentra; y permitirá opciones de tratamiento: consulta y devolución. La aplicación podra usar estos datos obteniendolos del sistema de almacenamiento.

## Decision Drivers

* RF2
* RF3

## Considered Options

* Patrón Singleton
* Acceso a un singleton mediante proxy

## Decision Outcome

Chosen option: "Acceso a un singleton mediante proxy", because no requiere que el almacen de datos gestione el acceso ni los permisos manteniendo las ventajas de tener 1 único objeto de la base de datos en memoria

### Positive Consequences

* Se reutiliza la misma conexión durante la vida de la aplicación, reduciendo el número de apertura y cierre de conexiones con el sistema de guardado.
* Se pueden instanciar varios procesos que accedan a la base de datos y que el Proxy gestione el acceso.
* Permite hacer "caching" en el proxy (ejemplo: El proxy guarda los datos de tu perfil o numero de usuarios de la aplicación), reduciendo el tráfico a la base de datos.
* Permite hacer copias de seguridad y que el proxy cuando se clonan los datos
* Permite utilizar almacenes de apoyo si se cae el principal.

### Negative Consequences

* La instancia permanece en memoria durante toda la ejecución, incluso si no se está usando activamente.

## Pros and Cons of the Options

### Proxy+Singleton

Crear un proxy que controle el acceso a la base de datos, que es un singleton, gestionando accesos concurrentes de varios procesos y clientes, permisos del usuario y disponibilidad del singleton

* Good, because Permite que varios elementos o clientes llamen a la base de datos sin que el singleton o el cliente tengan que gestionar la concurrencia o los conflictos
* Good, because Permite comprobar permisos desde el backed antes de acceder a la base de datos
* Bad, because introduce latencia
* Bad, because Si se concentra demasiada funcionalidad en la clase Singleton, se rompe el principio de responsabilidad única, haciendo la clase difícil de mantener.


### Patrón Singleton

Patrón de diseño creacional que permite un punto de acceso global y único al sistema de almacenamiento de nuestra aplicación

* Good, because Evita abrir y cerrar conexiones constantemente, lo que reduce consumo de memoria y procesamiento.
* Good, because Al centralizar el acceso a la base de datos, se facilita la implementación de políticas de conexión segura y manejo de credenciales.
* Bad, because Si se concentra demasiada funcionalidad en la clase Singleton, se rompe el principio de responsabilidad única, haciendo la clase difícil de mantener.
