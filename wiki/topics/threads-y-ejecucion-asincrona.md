---
title: "Threads y ejecución asíncrona"
aliases: ["hilos", "ExecutorService", "Future", "Callable", "Runnable"]
sources: [OFF-004, OFF-005, OFF-006, OFF-009, OFF-011]
related: ["seguridad-de-hilos-y-sincronizacion", "alternativas-a-la-sincronizacion"]
prerequisites: ["modelos-de-programacion"]
---

# Threads y ejecución asíncrona

## Overview

Un thread es una unidad de ejecución dentro de un proceso. Compartir el espacio de memoria del proceso hace eficiente su comunicación, pero exige coordinar y proteger el estado compartido. [OFF-005, pp. 4-5]

## Core concepts

`Runnable` representa una tarea sin resultado y `Callable<V>` una tarea que devuelve un valor. `Future<V>` representa el estado de una tarea asíncrona y permite consultar, cancelar o recuperar su resultado. [OFF-006, pp. 35-37]

`ExecutorService` ejecuta tareas `Runnable` o `Callable`, las asocia a `Future` y permite gestionar su ciclo de vida. La cátedra presenta el uso de pools para reutilizar threads en vez de crearlos repetidamente. [OFF-006, pp. 37-40]

Al finalizar un executor se debe controlar su terminación; los ejercicios del curso usan `shutdown`, `awaitTermination` y, ante timeout o interrupción, `shutdownNow`. [OFF-011, p. 3]

## How it works

`CompletableFuture` extiende la idea de `Future`: puede completarse de forma programática, encadenarse y combinarse mediante `CompletionStage`. Las variantes `*Async` pueden ejecutar acciones en otros threads mediante `ForkJoinPool` o un `ExecutorService`. [OFF-004, pp. 32-35]

Por ejemplo, dos cómputos independientes pueden iniciarse con `supplyAsync` y combinarse con `thenCombineAsync`; si solo importa el primero que termina, se puede aplicar `applyToEither`. [OFF-004, pp. 40-41]

## Relationships

La ejecución concurrente no implica que el acceso a estado compartido sea correcto: véase [seguridad de hilos y sincronización](seguridad-de-hilos-y-sincronizacion.md). También puede evitarse compartir estado mediante [alternativas a la sincronización](alternativas-a-la-sincronizacion.md).

## Exam relevance

Los trabajos prácticos piden analizar salidas concurrentes, estados de threads, distintos tipos de executor y el uso de `CompletableFuture` para ejecutar y combinar tareas. [OFF-009, pp. 1-2; OFF-011, pp. 1-5]

## Sources

* [OFF-004, pp. 32-41]
* [OFF-006, pp. 35-40]
* [OFF-009, pp. 1-2]
* [OFF-011, pp. 1-5]
