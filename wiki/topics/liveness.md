---
title: "Liveness"
aliases: ["disponibilidad", "deadlock", "livelock", "starvation"]
sources: [OFF-005]
related: ["seguridad-de-hilos-y-sincronizacion", "alternativas-a-la-sincronizacion"]
prerequisites: ["seguridad-de-hilos-y-sincronizacion"]
---

# Liveness

## Overview

Liveness o disponibilidad refiere a que los threads puedan progresar y terminar. El uso de locks para coordinar puede impedirlo. [OFF-005, pp. 27-28]

## Core concepts

Hay deadlock cuando dos threads retienen un lock e intentan adquirir el del otro. Hay livelock cuando, intentando evitarlo, liberan y reintentan repetidamente sin avanzar. Hay starvation cuando un thread nunca logra obtener el lock o recurso que necesita porque otros lo ocupan. [OFF-005, p. 28]

La cátedra presenta `Semaphore`, `Condition`, `CountDownLatch` y `CyclicBarrier` como mecanismos de coordinación para casos más complejos. [OFF-005, pp. 29-30]

## How it works

Muchos métodos bloqueantes de `java.util.concurrent` tienen variantes con timeout. El material recomienda usarlas y manejar el timeout —por ejemplo, con reintentos limitados y luego una excepción—; los bloqueos sin timeout deben revisarse cuidadosamente. [OFF-005, p. 30]

## Sources

* [OFF-005, pp. 27-30]
