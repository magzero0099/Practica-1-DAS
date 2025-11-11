# Patrón de Diseño 1 Fases Pedidos

* Status: proposed
* Deciders: Gonzalo Fernández de Córdoba García, Daniel Hernanz Corral y Marcos Hernández Martín
* Date: 2025-10-29

## Context and Problem Statement

La realización de los pedidos se dividirá en fases con un orden fijo sin opción de retorno, siendo estas fases: preprocesado del pedido, autorización y aceptación.

## Decision Drivers

* RF4 División en fases de los pedidos.

## Considered Options

* Chain of Responsability
* State
* Template Method
* Strategy

## Decision Outcome

Chosen option: "State", because Permite al objeto saber la fase en la que se encuentra y define transiciones controladas y ordenadas

### Positive Consequences

* Control absoluto sobre las transiciones
* Es fácil controlar en qué fase se encuentra el pedido.
* Permite añadir estados sin modificar la clase pedido

### Negative Consequences

* Requiere implementar y mantener una clase por cada fase
* La interfaz común causa poca flexibilidad

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
* Bad, because Poca flexibilidad para añadir funciones

### Template Method

Patrón de diseño de comportamiento que define la estructura de una algoritmo, permitiendo que las sublcases sobrescriban los pasos del algoritmo sin alterar la estructura.

* Good, because Código reutilizable.
* Good, because Garantiza el orden entre fases.
* Good, because No utiliza una interfaz común, más flexible
* Bad, because Difícil de probar individualmente.
* Bad, because Requiere cambiar la clase del pedido según su fase

### Strategy

Permite definir varios algoritmos entre los que el objeto puede decidir en tiempo de ejecución

* Good, because Permite cambiar de algoritmo facilmente
* Good, because Reduce el acoplamiento
* Good, because Permite añadir algoritmos sin modificar el pedido u otros algoritmos
* Bad, because No guarda información de la fase en la que se encuentra
* Bad, because El objeto debe gestionar las transiciones de fase
* Bad, because Requiere implementar y mantener varias clases
