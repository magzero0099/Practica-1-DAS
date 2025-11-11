# Patrón de diseño de area de incidencias

* Status: proposed
* Deciders: Daniel Hernanz Corral y Marcos Hernández Martín
* Date: 2025-11-04

## Context and Problem Statement

La aplicación implementará un área de gestión de rutas e incidencias, a la cual sólo pueden acceder los gestores con credenciales (usuario y contraseña) específicas. Queremos por tanto gestionar el acceso para que solo puedan acceder los gestores

## Decision Drivers

* RF7

## Considered Options

* Patrón proxy

## Decision Outcome

Chosen option: "Patrón proxy", because permite controlar el acceso al área de gestión, limitando el acceso solo a los gestores de incidencias.

### Positive Consequences

* No se puede acceder al área de gestión hasta que el proxy valide el acceso

## Pros and Cons of the Options

### Patrón proxy

Patrón de diseño estructural que proporciona un sustituto o marcador de posición para otro objeto. El patrón permite controlar el acceso al objeto original

* Good, because Evita que usuarios normales entren al área de gestión
* Good, because Facilita el mantenimiento ya que si cambian las reglas de acceso (por ejemplo, roles nuevos), solo se modifica el Proxy.
