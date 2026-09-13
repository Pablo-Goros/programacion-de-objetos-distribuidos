---
title: "Patrones de comunicación en gRPC"
aliases: ["RPC unario", "server streaming", "client streaming", "bidirectional streaming", "stream vs repeated"]
sources: [OFF-002, OFF-008]
related: ["grpc-y-protobuf", "sistemas-distribuidos-y-cliente-servidor"]
prerequisites: ["grpc-y-protobuf"]
---

# Patrones de comunicación en gRPC

## Overview

gRPC define cuatro tipos de métodos según cuántos mensajes se intercambian en request y response: unario, server streaming, client streaming y streaming bidireccional. [OFF-002, pp. 2-8]

## Core concepts

En RPC unario el cliente envía un único request y recibe un único response. Es el patrón de los ejemplos iniciales del curso. [OFF-002, pp. 4-5]

Streaming permite que request, response o ambos envíen más de un mensaje. En el contrato se expresa con `stream` sobre el mensaje de entrada o salida. [OFF-002, pp. 7-8]

`stream` y `repeated` no son equivalentes: `stream` modifica un mensaje de entrada o salida, mientras que `repeated` modifica un campo dentro de un mensaje. El material asocia habitualmente `repeated` a listas disponibles inmediatamente y `stream` a resultados que llegan progresivamente. [OFF-002, pp. 8-9]

## Example

El TP de recitales define una operación `requestTicket` que responde `stream TicketNotification`; ilustra notificaciones asíncronas al cliente durante la evolución de una reserva, confirmación, agotamiento o cancelación. [OFF-008, pp. 3-5]

## Exam relevance

La selección del patrón forma parte del diseño del contrato: el TP exige un servicio de notificaciones con server streaming y conservar la interfaz provista. [OFF-008, pp. 3-5]

## Sources

* [OFF-002, pp. 2-9]
* [OFF-008, pp. 3-5]
