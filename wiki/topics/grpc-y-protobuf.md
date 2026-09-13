---
title: "gRPC y Protocol Buffers"
aliases: ["gRPC", "Protocol Buffers", "protobuf", "IDL", ".proto", "stub", "servant"]
sources: [OFF-001, OFF-003, OFF-007, OFF-008]
related: ["sistemas-distribuidos-y-cliente-servidor", "patrones-de-comunicacion-grpc"]
prerequisites: ["sistemas-distribuidos-y-cliente-servidor"]
---

# gRPC y Protocol Buffers

## Overview

gRPC es un sistema de comunicación RPC de código abierto. Se basa en Protocol Buffers como lenguaje de definición de interfaces y formato de serialización. [OFF-003, pp. 30-31]

## Core concepts

El contrato `.proto` define servicios, métodos y mensajes. Cada método se declara con `rpc` y tiene exactamente un mensaje de entrada y uno de salida; un mensaje puede contener campos `repeated`. [OFF-003, pp. 43-45]

El código Java generado incluye una clase `<Servicio>Grpc`, que provee el middleware y los tipos de stub. El material distingue stub bloqueante, un stub futuro y un stub asíncrono basado en observers. [OFF-003, pp. 40-42]

El servidor implementa el servicio extendiendo `<Servicio>Grpc.<Servicio>ImplBase`; el cliente crea el stub sobre un channel. En Spring gRPC, el material muestra `GrpcChannelFactory` y la anotación `@Service` para integrar estos roles. [OFF-003, pp. 50-56]

## How it works

La implementación del servant entrega valores mediante un `StreamObserver`: `onCompleted` señala finalización y `onError` se usa ante error. [OFF-003, pp. 57-60]

Para evitar duplicar el contrato entre equipos, la cátedra propone separar los módulos `api`, `client` y `server`: `api` contiene el `.proto` y el código generado, del cual dependen cliente y servidor. [OFF-001, pp. 2-3]

## Exam relevance

Los TP solicitan detectar errores en contratos `.proto`, implementar el contrato, un servant y un cliente con stub bloqueante; también exigen preservar la interfaz suministrada y, en un caso, capturar errores esperados con un interceptor del servidor. [OFF-007, pp. 1-2; OFF-008, pp. 1-5]

## Sources

* [OFF-001, pp. 2-3]
* [OFF-003, pp. 30-31, 40-60]
* [OFF-007, pp. 1-2]
* [OFF-008, pp. 1-5]
