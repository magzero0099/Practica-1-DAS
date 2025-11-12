# Patrón de diseño notificación incidencias rutas

* Status: Rejected
* Deciders: Rodrigo Fernández de Córdoba García, Daniel Hernanz Corral y Marcos Hernández Martín
* Date: 2025-11-01

## Context and Problem Statement

La aplicación permite reportar incidencias ocurridas en el transporte de mercancía, por ejemplo, camión averiado o reparto no realizado.
Además de la incidencia, se guardarán la fecha y hora y el estado de la incidencia (resuelta, en tratamiento, no resuelta). Necesitamos notificar a los gestores de rutas cuando se produzca una incidencia para que estén informados lo antes posible.

## Decision Drivers

* RF7.2 Notificar incidencias ocurridas

## Considered Options

* Patrón observer

## Decision Outcome

Chosen option: "Patrón observer", because Encaja perfectamente con la notificación y recepción de incidencias

### Positive Consequences

* Asegura la notificación de incidencias en tiempo real

## Pros and Cons of the Options

### Patrón observer

Patrón de diseño de comportamiento que permite lanzar notificaciones para que la reciban los suscriptores que estén interesados.

* Good, because El emisor de incidencias no necesita conocer a los gestores, solo los notifica
* Good, because Cada gestor decide qué hacer cuando recibe la notificación
* Bad, because Si ocurren muchas incidencias pueden haber demasiadas notificaciones que pueden saturar el sistema.
