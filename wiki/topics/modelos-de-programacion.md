---
title: "Modelos de programación"
aliases: ["programación secuencial", "programación concurrente", "programación distribuida"]
sources: [OFF-003, OFF-006]
related: ["threads-y-ejecucion-asincrona", "sistemas-distribuidos-y-cliente-servidor"]
prerequisites: []
---

# Modelos de programación

## Overview

El curso distingue modelos secuencial, concurrente y distribuido. Cada uno organiza la ejecución y los recursos de manera diferente. [OFF-006, pp. 3-4]

## Core concepts

Un programa es una secuencia estática de instrucciones; un proceso es ese programa en ejecución, al que el sistema operativo asigna recursos. [OFF-006, p. 3]

En el modelo secuencial un procesador ejecuta un proceso completo antes de continuar con otro. La elección del scheduler afecta el tiempo de finalización de cada proceso. [OFF-006, pp. 5-8]

La concurrencia permite organizar varias tareas en ejecución dentro de los recursos de una computadora. El modelo distribuido se utiliza cuando hacen falta más recursos, potencia o eficiencia de los disponibles en un único sistema. [OFF-003, pp. 3-5]

## Relationships

La concurrencia se materializa en Java mediante [threads y ejecución asíncrona](threads-y-ejecucion-asincrona.md); al compartir memoria aparecen los requisitos de [seguridad de hilos y sincronización](seguridad-de-hilos-y-sincronizacion.md). El modelo distribuido se explica desde el vínculo [sistemas distribuidos y cliente-servidor](sistemas-distribuidos-y-cliente-servidor.md).

## Sources

* [OFF-003, pp. 3-5]
* [OFF-006, pp. 3-8]
