---
title: "Alternativas a la sincronización"
aliases: ["inmutabilidad", "pub-sub", "publisher-subscriber", "ParallelStream", "CompletableFuture"]
sources: [OFF-004, OFF-009]
related: ["seguridad-de-hilos-y-sincronizacion", "threads-y-ejecucion-asincrona"]
prerequisites: ["threads-y-ejecucion-asincrona"]
---

# Alternativas a la sincronización

## Overview

La sobre-sincronización, los bloqueos y los problemas de memoria motivan alternativas basadas en inmutabilidad, comunicación pub/sub y subdivisión de tareas independientes. [OFF-004, pp. 2-3]

## Core concepts

Un objeto inmutable no cambia su estado después de crearse. Para construirlo, el material indica mantener campos privados y finales, impedir modificaciones por subclases y evitar que referencias mutables internas se modifiquen o escapen. Tales objetos no pueden corromperse por interferencia entre threads. [OFF-004, pp. 4-6]

En pub/sub, productor y consumidor comparten una cola: el productor publica un mensaje al terminar y el consumidor lo toma para iniciar su tarea. Esto reduce la dependencia entre threads y el riesgo asociado a `notifyAll` o locks bloqueantes. [OFF-004, pp. 7-9]

Para datos particionables, cada worker calcula un resultado parcial sobre una porción independiente y luego se combinan los resultados. Las particiones independientes evitan interferencia y permiten reutilizar workers. [OFF-004, pp. 18-21]

## How it works

Las colas disponibles incluyen `ArrayBlockingQueue`, `LinkedBlockingQueue`, `PriorityBlockingQueue`, `DelayQueue`, `LinkedTransferQueue`, `SynchronousQueue` y `ConcurrentLinkedQueue`; su elección cambia capacidad, orden y comportamiento de bloqueo. [OFF-004, pp. 10-11]

Java 8 permite paralelizar streams con `parallelStream`; la JVM divide el trabajo usando `ForkJoinPool`, una solución genérica que no necesariamente es la óptima. [OFF-004, pp. 22-23]

## Exam relevance

El TP pide aplicar `ParallelStream` y `CompletableFuture` para independizar notificaciones y combinar cálculos por archivo. [OFF-009, pp. 1-2]

## Sources

* [OFF-004, pp. 2-23]
* [OFF-009, pp. 1-2]
