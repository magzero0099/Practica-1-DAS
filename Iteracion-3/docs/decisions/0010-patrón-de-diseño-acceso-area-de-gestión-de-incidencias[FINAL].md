# Patrón de diseño de area de incidencias

* Status: accepted
* Deciders: Daniel Hernanz Corral y Marcos Hernandez Martín
* Date: 2025-11-04

## Context and Problem Statement

La aplicación implementará un área de gestión de rutas e incidencias, a la cual sólo pueden acceder los gestores con credenciales (usuario y contraseña) específicas. Queremos por tanto gestionar el acceso para que solo puedan acceder los gestores

## Decision Drivers

* RF7 Área de gestión de rutas e incidencias.

## Considered Options

* Patrón proxy

## Decision Outcome

Chosen option: "Patrón proxy", because permite controlar el acceso al área de gestión, limitando el acceso solo a los gestores de incidencias.

### Positive Consequences

* No se puede acceder al área de gestión hasta que el proxy valide el acceso

### Negative Consequences

* Requiere implementar funciones intermediarias en el proxy

## Pros and Cons of the Options

### Patrón proxy

Patrón de diseño estructural que proporciona un sustituto o marcador de posición para otro objeto. El patrón permite controlar el acceso al objeto original

* Good, because Evita que usuarios normales entren al área de gestión
* Good, because Facilita el mantenimiento ya que si cambian las reglas de acceso (por ejemplo, roles nuevos), solo se modifica el Proxy.
* Bad, because Hay que crear funciones intermedias en el Proxy para redirigir a las operaciones correspondientes en la incidencia (más código que mantener)