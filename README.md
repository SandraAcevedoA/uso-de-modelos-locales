# Uso de Modelos Locales

Workshop práctico en español sobre cómo inspeccionar el hardware disponible, leer y elegir modelos de lenguaje locales, ejecutarlos, evaluar su comportamiento y decidir cuándo conviene trabajar en local, en la nube o con un flujo híbrido.

**Autora y facilitadora:** Sandra Acevedo  
**Escuela:** Multiverse School  
**Clase:** 245  
**Facilitación original:** 4 de septiembre de 2026  
**Duración:** 180 minutos  
**Nivel:** todos los niveles  
**Idioma:** español

## Qué enseña este workshop

El workshop sigue una cadena de decisión deliberadamente práctica:

> **TAREA → HARDWARE → LEER → COMPARAR → ELEGIR → CONFIGURAR → EJECUTAR → EVALUAR → DECIDIR**

Al terminar, una persona debería poder:

- distinguir inferencia local, en la nube e híbrida;
- identificar qué características de su equipo importan para ejecutar modelos locales;
- interpretar parámetros, tamaño, cuantización, contexto y requisitos de memoria;
- separar **Hardware Fit**, **Task Fit** y **Operational Fit**;
- elegir un modelo por tarea, hardware y concesiones aceptables, no sólo por popularidad o tamaño;
- recorrer o diagnosticar una ejecución local con un runner;
- evaluar velocidad, calidad y limitaciones mediante una prueba reproducible;
- justificar si una tarea conviene en local, cloud o un flujo híbrido;
- repetir el proceso con otro modelo, otra tarea o otra máquina.

La inferencia local exitosa en el computador del participante no es requisito para completar el workshop. Diagnosticar correctamente una restricción y seguir una ruta de respaldo también demuestra la capacidad de decisión que se enseña.

## Materiales principales

### Curriculum

[`curriculum/syllabus.md`](curriculum/syllabus.md) contiene la versión consolidada del curriculum del workshop: contenidos, objetivos, checkpoints, recorrido de 180 minutos y evidencia mínima de aprendizaje.

### Local Model Bench

`interactive/local-model-bench/` contiene **Local Model Bench**, la herramienta interactiva principal del workshop.

El Bench no intenta declarar cuál es “el mejor modelo”. Su función es hacer explícitas las restricciones, la evidencia, las concesiones y la incertidumbre detrás de una elección.

La versión live utilizada por el workshop está disponible en:

https://themultiverse.school/x/uso-de-modelos-locales

### Fuentes y procedencia

[`resources/sources.md`](resources/sources.md) documenta las fuentes curriculares, técnicas y de procedencia utilizadas para construir y alinear el workshop.

## Herramientas utilizadas en la facilitación

La versión consolidada del workshop utiliza:

- **Jan** como runner principal de práctica;
- **GPT4All** como alternativa más sencilla;
- **PocketPal** como demostración móvil;
- **Hugging Face** como referencia para leer información de modelos;
- **Local Model Bench** como superficie interactiva para conectar tarea, hardware, selección, ejecución, evaluación y routing.

Los runners son superficies de práctica, no el contenido conceptual del workshop. El proceso debe seguir siendo útil aunque cambien las herramientas concretas.

## Evidencia mínima de aprendizaje

El workshop organiza la evidencia en cinco piezas:

1. **Hardware Envelope** — recursos del equipo y qué implican.
2. **Model Choice** — modelo elegido y razones de la elección.
3. **Run Card / bitácora** — configuración, ejecución y diagnóstico.
4. **Evaluation** — velocidad, calidad y limitaciones observadas.
5. **Routing Decision** — Local / Cloud / Hybrid con una razón basada en evidencia.

Estas piezas terminan reunidas en **My Local Model Plan**, un registro reutilizable del proceso seguido.

## Alcance

Este workshop se concentra en ejecutar y evaluar modelos locales sobre hardware personal.

Quedan fuera de las tres horas, salvo como rutas de profundización:

- entrenamiento y fine-tuning;
- LoRA / PEFT;
- pipelines RAG;
- bases de datos vectoriales;
- embeddings en profundidad;
- frameworks de agentes;
- MCP y tool calling;
- APIs locales de producción;
- servidores dedicados;
- SBC, NPU y aceleradores especializados;
- benchmarking exhaustivo.

El objetivo no es demostrar que local “gana” frente a cloud. El objetivo es aprender a decidir dónde tiene sentido ejecutar una tarea concreta.

## Estructura del repositorio

```text
uso-de-modelos-locales/
├── README.md
├── CHANGELOG.md
├── LICENSE
├── curriculum/
│   └── syllabus.md
├── interactive/
│   └── local-model-bench/
└── resources/
    └── sources.md
```

El repositorio público contiene los artefactos necesarios para comprender y reutilizar el workshop. Historial operacional, notas internas, meeting notes, snapshots, material administrativo y documentos de producción permanecen fuera de este paquete.

## Licencia

La licencia del repositorio se define explícitamente en `LICENSE`. El contenido del workshop y el software del Bench pueden requerir términos distintos si así se establece en esa licencia.
