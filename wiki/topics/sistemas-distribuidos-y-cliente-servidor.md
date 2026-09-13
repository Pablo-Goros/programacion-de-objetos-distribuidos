---
title: "Sistemas distribuidos y cliente-servidor"
aliases: ["sistema distribuido", "cliente/servidor", "IPC", "sockets", "RPC"]
sources: [OFF-003]
related: ["grpc-y-protobuf", "modelos-de-programacion"]
prerequisites: ["modelos-de-programacion"]
---

# Sistemas distribuidos y cliente-servidor

## Overview

Un sistema distribuido tiene componentes en computadoras distintas que se comunican mediante mensajes de red y se presenta al usuario como un sistema coherente. Su objetivo es dividir una tarea y coordinar recursos para completarla más eficientemente que en una sola computadora. [OFF-003, pp. 4-5]

## Core concepts

En cliente-servidor, el servidor ejecuta las operaciones de una API y el cliente solicita su ejecución. Cliente y servidor son roles de una interacción, no identidades permanentes de un proceso. [OFF-003, pp. 8-10]

Un servicio administra recursos y expone una funcionalidad limitada a operaciones definidas por una API. La interfaz describe modos de llamado, nombres, parámetros, respuestas y errores. [OFF-003, pp. 11-14]

El patrón request/response procesa una solicitud y devuelve una respuesta; el estilo basado en eventos registra clientes para recibir eventos de forma asíncrona. [OFF-003, p. 12]

## How it works

En IPC sobre red, los nodos se ubican por IP y puerto y se conectan mediante sockets para intercambiar mensajes binarios sobre TCP/IP o UDP/IP. [OFF-003, pp. 16-18]

RPC incorpora middleware que establece la comunicación, traduce mensajes y aísla al cliente de detalles de comunicación y errores, para que la invocación remota se parezca a una local. [OFF-003, pp. 24-28]

## Relationships

[gRPC y Protocol Buffers](grpc-y-protobuf.md) aplica RPC con un contrato IDL. La concurrencia local es tratada en [threads y ejecución asíncrona](threads-y-ejecucion-asincrona.md).

## Sources

* [OFF-003, pp. 4-28]
