# Patrón de diseño notificación incidencias rutas

* Status: accepted
* Deciders: Rodrigo Fernández de Córdoba García, Daniel Hernanz Corral y Marcos Hernández Martín
* Date: 2025-11-11

## Context and Problem Statement

La aplicación permite reportar incidencias ocurridas en el transporte de mercancía, por ejemplo, camión averiado o reparto no realizado.
Además de la incidencia, se guardarán la fecha y hora y el estado de la incidencia (resuelta, en tratamiento, no resuelta). Necesitamos notificar a los gestores de rutas cuando se produzca una incidencia para que estén informados lo antes posible.

## Decision Drivers

* RF7.2 Notificar incidencias ocurridas

## Considered Options

* Publisher-Subscriber

## Decision Outcome

Chosen option: "Publisher-Subscriber", because Encaja perfectamente con la notificación y recepción de incidencias.

### Positive Consequences

* Asegura la notificación de incidencias en tiempo real

## Pros and Cons of the Options

### Patrón publisher-subscriber

Patrón de diseño de comportamiento que permite lanzar notificaciones para que la reciban los suscriptores que estén interesados, ubicándose estos en sistemas separados.

* Good, because El emisor de incidencias no necesita conocer a los gestores, solo los notifica
* Good, because Cada gestor decide qué hacer cuando recibe la notificación
* Bad, because Si ocurren muchas incidencias pueden haber demasiadas notificaciones que pueden saturar el sistema.
