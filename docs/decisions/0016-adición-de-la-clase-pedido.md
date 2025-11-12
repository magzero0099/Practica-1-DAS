# Adición-de-la-clase-Pedido

* Status: proposed
* Deciders: Marcos Hernández Martín, Daniel Hernanz Corral
* Date: 2025-11-12

## Context and Problem Statement

La aplicación dará opciones de tratamiento (consulta y modificación) para los pedidos de los clientes: ID, lista de productos, peso del bulto y fase en la que se encuentra.Necesitamos una clase pedido en la lógica de negocio para poder almacenar y acceder a los datos importantes de estos.
Necesitamos encontrar alguna manera de representar los pedidos.

## Decision Drivers

* RF3 Tratamiento de los pedidos de los clientes.

## Considered Options

* Representar pedido mediante una clase

## Decision Outcome

Chosen option: "Representar pedido mediante una clase", because simplifica la representación de los pedidos en el sistema

### Positive Consequences

* No hay que consultar diferentes clases para llevar a cabo el tratamiento de datos de los pedidos.

### Negative Consequences

* Toda la lógica de pedidos concentrada en una sola clase, sube el acoplamiento.

## Pros and Cons of the Options

### Representar pedido mediante una clase

Se representarán los pedidos mediante una clase que tendrá por propiedades ID, lista de productos, peso del bulto, fase en la que se encuentra; y los métodos necesarios para el tratamiento: consulta y modificación.

* Good, because Mayor sencillez de implementación.
* Good, because Cumple con el principio de responsabilidad única: la clase de pedidos contendrá únicamente la lógica de negocio correspondiente al tratamiento de datos de los pedidos.
