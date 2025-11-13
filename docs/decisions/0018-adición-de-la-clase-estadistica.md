# Adición-de-la-clase-Estadistica

* Status: proposed
* Deciders: Marcos Hernández Martín, Daniel Hernanz Corral
* Date: 2025-11-12

## Context and Problem Statement

La aplicación implementará un área de estadísticas que proporciona información relevante para sus clientes.
Además, la aplicación proporciona las estadísticas de compra de los clientes, incluyendo la dirección de entrega e historial de compras.
Necesitamos encontrar alguna manera de modularizar el acceso a las estadísticas.

## Decision Drivers

* RF6 Área de estadísticas
* RF6.3 Proporcionar información variada de los clientes.

## Considered Options

* Representar módulo de estadísticas mediante una clase

## Decision Outcome

Chosen option: "Representar módulo de estadísticas mediante una clase", because permite centralizar la lógica y los datos estadísticos en un único punto del sistema, mejorando la mantenibilidad y la coherencia del código.

### Positive Consequences

* Se garantiza una estructura coherente y modular para el manejo de las estadísticas del sistema.

### Negative Consequences

* Posible incremento en el acoplamiento entre módulos si no se gestionan correctamente las dependencias.

## Pros and Cons of the Options

### Representar módulo de estadísticas mediante una clase

Se representará el módulo de estadísticas del sistema mediante una clase que contenga información sobre pedidos, clientes y ubicaciones de camiones. Además, estará asociada a las clases cliente y pedido.

* Good, because Implementación sencilla
* Good, because Acceso directo, sin intermediarios, a los datos de estadísticas.
* Bad, because Si se añaden nuevas estadísticas, la clase puede volverse demasiado compleja
