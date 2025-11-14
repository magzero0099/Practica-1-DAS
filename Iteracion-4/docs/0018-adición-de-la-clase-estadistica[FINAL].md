# Adición-de-la-clase-Estadistica

* Status: accepted
* Deciders: Marcos Hernández Martín, Daniel Hernanz Corral y Gonzalo Fernández de Córdoba García
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

Chosen option: "Representar módulo de estadísticas mediante una clase", because permite centralizar la lógica y los datos estadísticos en un único punto del sistema, mejorando la mantenibilidad y la coherencia.

### Positive Consequences

* Se garantiza una estructura coherente y modular para el manejo de las estadísticas del sistema.
* Se facilita la evolución y optimización de las estadísticas al unificarse en un único punto.
* Facilita la realización de pruebas en el módulo de estadísticas, al estar concentrado alrededor de esta clase
  
### Negative Consequences

* Posible incremento en el acoplamiento entre módulos si no se gestionan correctamente las dependencias.
* Riesgo de crear una clase que concentre demasiada funcionalidad, influyendo negativamente en el acoplamiento

## Pros and Cons of the Options

### Representar módulo de estadísticas mediante una clase

Se representará el módulo de estadísticas del sistema mediante una clase que contenga información sobre pedidos, clientes y ubicaciones de camiones. Además, estará asociada a las clases cliente y pedido.

* Good, because Implementación sencilla
* Good, because Acceso directo, sin intermediarios, a los datos de estadísticas.
* Facilita realización de pruebas
* Bad, because Si se añaden nuevas estadísticas, la clase puede volverse demasiado compleja
