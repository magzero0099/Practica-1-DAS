# Patrón de Diseño Algoritmos Decisión de Rutas

* Status: proposed
* Deciders: Daniel Hernanz Corral y Marcos Hernandez Martín
* Date: 2025-10-29

## Context and Problem Statement

La aplicación ejecutará uno de los dos algoritmos de decisión en función del tipo de ruta y la capacidad del camión.

## Decision Drivers

* RF5.1 Selección de algoritmo de decisión de rutas de transporte

## Decision Outcome

Chosen option: "Strategy", because Strategy coloca los algoritmos en clases separadas, y hace los objetos sobre los que actúan intercambiables. Encaja perfectamente con nuestro sistema porque se plantean dos algoritmos que pueden ser seleccionados dependiendo del tipo de ruta y la capacidad del camión.

### Positive Consequences

* Permite cambiar de algoritmo fácilmente
* Reduce el acoplamiento
* Separa los códigos de cada algoritmo

### Negative Consequences

* Más clases que mantener.
