---
title: "Seguridad de hilos y sincronización"
aliases: ["thread safety", "happens-before", "synchronized", "atomicidad"]
sources: [OFF-005, OFF-010]
related: ["liveness", "alternativas-a-la-sincronizacion"]
prerequisites: ["threads-y-ejecucion-asincrona"]
---

# Seguridad de hilos y sincronización

## Overview

La programación concurrente introduce problemas de coordinación, consistencia/sincronización y disponibilidad. Cuando varios threads comparten variables de instancia o estáticas, sus lecturas y escrituras pueden interferir. [OFF-005, pp. 3-6]

## Core concepts

Un error de consistencia puede ocurrir si un thread escribe sin observar una modificación concurrente, o si una lectura no ve una escritura que parecería anterior. La relación `happens-before` expresa las garantías de orden y visibilidad relevantes. [OFF-005, pp. 7-8]

Entre las garantías presentadas están: el orden de programa dentro del mismo thread; `unlock` antes de un `lock` posterior sobre el mismo monitor; escritura `volatile` antes de lectura del mismo campo; `start` antes de las acciones del thread iniciado; y acciones de un thread antes de las de otro que realizó `join` sobre él. [OFF-005, p. 8]

Las lecturas y escrituras de referencias y de la mayoría de primitivas, salvo `long` y `double`, son atómicas; también lo son los accesos a campos `volatile`. Esto no vuelve atómicas operaciones compuestas como `++`. [OFF-005, p. 9]

## How it works

Cada objeto Java puede tener un monitor. Un bloque `synchronized` adquiere el lock del objeto elegido: otro thread que intenta adquirir ese mismo lock queda bloqueado, y al liberarlo se establece la relación `happens-before` correspondiente. [OFF-005, pp. 10-11]

Un método de instancia sincronizado bloquea sobre `this`; para recursos de clase, el lock relevante puede ser el objeto `Class`. El TP solicita justificar la equivalencia entre un método `static synchronized` y un bloque sincronizado sobre `A.class`. [OFF-010, p. 1]

## Relationships

La sincronización puede introducir problemas de progreso, tratados en [liveness](liveness.md). Cuando el diseño lo permite, la inmutabilidad y la comunicación por colas reducen la necesidad de locks: [alternativas a la sincronización](alternativas-a-la-sincronizacion.md).

## Exam relevance

El TP requiere detectar inconsistencias de un stack no seguro para concurrencia, corregirlo y evaluar diseños concurrentes justificando errores y soluciones. [OFF-010, pp. 1-4]

## Sources

* [OFF-005, pp. 3-11]
* [OFF-010, pp. 1-4]
