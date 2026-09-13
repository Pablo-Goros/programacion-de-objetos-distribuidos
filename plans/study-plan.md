# Plan de estudio

**Creado:** 2026-09-13  
**Estado:** pendiente de inicio  
**Enfoque acordado:** repaso liviano, orientado a comprensión y aplicación. Se omiten explicaciones extensas sobre la definición y el funcionamiento básico de los threads, que el estudiante ya domina.

## Objetivo

Comprender los modelos de ejecución, la concurrencia práctica en Java y la comunicación distribuida con gRPC, con suficiente profundidad para analizar y diseñar soluciones de los trabajos prácticos.

## Recorrido

| Bloque | Tema | Propósito | Duración estimada | Estado |
| --- | --- | --- | --- | --- |
| 1 | Modelos y mapa general | Distinguir los modelos secuencial, concurrente y distribuido, y relacionarlos. | 30 min | Pendiente |
| 2 | Concurrencia práctica en Java | Repasar `ExecutorService`, pools, `Runnable`, `Callable`, `Future` y `CompletableFuture`. | 45 min | Pendiente |
| 3 | Estado compartido y sincronización | Razonar sobre condiciones de carrera, atomicidad, visibilidad, `synchronized`, `volatile` y `happens-before`. | 60 min | Pendiente |
| 4 | Progreso y alternativas a locks | Reconocer deadlock, livelock y starvation; comparar inmutabilidad, colas/pub-sub, partición de trabajo y `parallelStream`. | 45 min | Pendiente |
| 5 | Sistemas distribuidos y RPC | Entender cliente-servidor, APIs, request/response, eventos y la abstracción de RPC. | 45 min | Pendiente |
| 6 | gRPC y Protocol Buffers | Diseñar contratos `.proto` y comprender stubs, servidor, `StreamObserver`, streaming y `repeated`. | 75 min | Pendiente |
| 7 | Cierre integrador | Resolver un caso que combine concurrencia local y un servicio gRPC. | 30 min | Pendiente |

## Orden y prioridades

Seguir el orden `1 → 2 → 3 → 4 → 5 → 6 → 7`.

Los bloques 3 y 6 tienen prioridad: concentran el razonamiento de diseño y los contenidos solicitados explícitamente por los trabajos prácticos.

## Trazabilidad al wiki

- Bloque 1: [Modelos de programación](../wiki/topics/modelos-de-programacion.md)
- Bloque 2: [Threads y ejecución asíncrona](../wiki/topics/threads-y-ejecucion-asincrona.md)
- Bloque 3: [Seguridad de hilos y sincronización](../wiki/topics/seguridad-de-hilos-y-sincronizacion.md)
- Bloque 4: [Liveness](../wiki/topics/liveness.md) y [Alternativas a la sincronización](../wiki/topics/alternativas-a-la-sincronizacion.md)
- Bloque 5: [Sistemas distribuidos y cliente-servidor](../wiki/topics/sistemas-distribuidos-y-cliente-servidor.md)
- Bloque 6: [gRPC y Protocol Buffers](../wiki/topics/grpc-y-protobuf.md) y [Patrones de comunicación en gRPC](../wiki/topics/patrones-de-comunicacion-grpc.md)

## Registro de avance

| Fecha | Bloque | Resultado / notas |
| --- | --- | --- |
| — | — | — |
