# Patrón de Diseño 2 Fases Pedidos

* Status: proposed
* Deciders: Daniel Hernanz Corral y Marcos Hernandez Martín
* Date: 2025-10-29

## Context and Problem Statement

La realización de los pedidos se dividirá en fases con un orden fijo sin opción de retorno, siendo estas fases: preprocesado del pedido, autorización y aceptación.

## Decision Drivers

* RF4 Almacenamiento y tratamiento de los pedidos de los 

## Considered Options

* Chain of Responsability
* State
* Template Method

## Decision Outcome

Chosen option: "Template Method", because Garantiza el orden de ejecución y define la estructura general del comportamiento de cada una de las fases.

### Positive Consequences

* Evita saltos entre fases inconexas
* Define la estructura

### Negative Consequences

* No es posible establecer comportamiento para cada uno de los estados.

## Pros and Cons of the Options

### Chain of Responsability

Patrón de diseño de comportamiento, en el que se pasan solicitudes entre una cadena de manejadores que pueden decidir si procesarlas o pasarlas al siguiente.

* Good, because Flujo entre los manejadores con un orden concreto.
* Good, because Bajo acoplamiento entre los manejadores.
* Good, because Flexibilidad: es fácil añadir o quitar fases sin modificar el resto del código.
* Bad, because No impide retrocesos: un pedido podría volver a estados anteriores no deseados.
* Bad, because No hay control de estado del pedido: el patrón no recuerda en qué estado se encuentra el pedido.
* Bad, because Difícil de depurar: si hay un error hay que buscarlo por toda la cadena.

### State

Patrón de diseño de comportamiento que permite alterar el comportamiento de un objeto cuando su estado interno cambia, traduciéndose cada uno de los estados en clases que implementan la misma interfaz.

* Good, because Garantiza que los pedidos avancen al siguiente estado permitido, sin posibilidad de vuelta atrás.
* Good, because Es más sencillo controlar en qué estado se encuentra el pedido.
* Bad, because Más cantidad de clases, al ser cada clase un estado.
* Bad, because Sólo controla las transiciones entre estados: no define el comprtamiento de cada uno de ellos.

### Template Method

Patrón de diseño de comportamiento que define la estructura de una algoritmo, permitiendo que las sublcases sobrescriban los pasos del algoritmo sin alterar la estructura.

* Good, because Código reutilizable.
* Good, because Garantiza el orden entre fases.
* Bad, because Difícil de probar individualmente.
