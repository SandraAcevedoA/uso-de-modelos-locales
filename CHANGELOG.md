# Changelog

Este archivo registra cambios relevantes en la versión pública de **Uso de Modelos Locales**. No intenta reproducir el historial completo de diseño, investigación, QA o despliegue interno.

## [1.0.0] — 2026-09-24

### Added

- Primera publicación consolidada del workshop como paquete público identificable.
- `README.md` como puerta de entrada al workshop.
- `curriculum/syllabus.md` a partir de la versión final descargada de HedgeDoc.
- `resources/sources.md` como registro público de fuentes y procedencia.
- Estructura reservada para publicar el clon validado de **Local Model Bench** en `interactive/local-model-bench/`.

### Documented

- Autoría, clase, fecha, duración, nivel e idioma del workshop.
- Cadena pedagógica basada en tarea → hardware → modelo → ejecución → evaluación → routing.
- Cinco piezas de evidencia mínima de aprendizaje.
- Alcance explícito y rutas de profundización fuera de las tres horas.
- Separación entre artefactos públicos del workshop e historial operacional interno.

## Workshop snapshot — 2026-09-04

Versión correspondiente a la facilitación original de la Clase 245 en Multiverse School.

### Delivered

- Workshop en vivo de 180 minutos, en español y para todos los niveles.
- Hardware Envelope como punto de partida para selección de modelos.
- Lectura práctica de parámetros, tamaño, cuantización y contexto.
- Separación entre Hardware Fit, Task Fit y Operational Fit.
- Uso de **Jan** como runner principal de práctica.
- **GPT4All** como alternativa más sencilla.
- Demostración móvil con **PocketPal**.
- Evaluación separada de velocidad, calidad y limitaciones.
- Decisión final Local / Cloud / Hybrid basada en evidencia.
- Uso de **Local Model Bench** como herramienta interactiva principal.

### Changed from earlier internal design

- El runner principal pasó de GPT4All a **Jan** en la versión consolidada del workshop.
- GPT4All quedó como alternativa de práctica, no como runner principal.
- La evidencia mínima de aprendizaje quedó definida de forma que una persona puede completar el workshop aun cuando su hardware no permita inferencia local exitosa durante la sesión.

## Nota de mantenimiento

Los cambios futuros deben registrar únicamente modificaciones que alteren el workshop público, su curriculum, su Bench, sus fuentes o su forma de facilitación. Cambios de notas internas, research scratchpads, scripts de despliegue o QA no necesitan aparecer aquí salvo que modifiquen el artefacto publicado.
