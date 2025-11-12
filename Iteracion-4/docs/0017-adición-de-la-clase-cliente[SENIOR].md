# Adición-de-la-clase-Cliente

* Status: proposed
* Deciders: Marcos Hernández Martín, Daniel Hernanz Corral
* Date: 2025-11-12

## Context and Problem Statement

La aplicación dará opciones de tratamiento (consulta y modificación) para los datos personales del cliente: ID, nombre, apellidos y correo electrónico.
Necesitamos encontrar alguna manera de representar los clientes.

## Decision Drivers

* RF2 Tratamiento de los datos personales de los clientes.

## Considered Options

* Representar clientes mediante una clase

## Decision Outcome

Chosen option: "Representar clientes mediante una clase", because La aplicación contará con una clase Cliente que incluirá las propiedades ID, nombre, apellidos y correo_electrónico, así como los métodos necesarios para la consulta y modificación de dichos datos.

### Positive Consequences

* Se garantiza una estructura coherente para el manejo de los datos personales del cliente.

### Negative Consequences

* Puede generar dependencia entre módulos si no se definen interfaces claras.

## Pros and Cons of the Options

### Representar clientes mediante una clase

Se representarán los clientes mediante una clase que tendrá por propiedades ID, nombre, apellidos y correo electrónico; y los métodos necesarios para el tratamiento: consulta y modificación.

* Good, because Facilita la validación y el control de acceso a los datos
* Good, because Facilita la encapsulación de datos y métodos relacionados con el cliente.
