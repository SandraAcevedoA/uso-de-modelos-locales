# Fuentes y procedencia

Este documento registra las fuentes que sustentan **Uso de Modelos Locales** y distingue entre:

1. el contrato público de la clase;
2. el curriculum existente de Multiverse utilizado como fuente de alineación;
3. las decisiones y materiales propios del workshop;
4. referencias técnicas y herramientas utilizadas durante la facilitación.

No es una copia del curriculum de Multiverse ni del historial interno de diseño.

## 1. Contrato público del workshop

### Multiverse School — Clase 245: Uso de Modelos Locales

Página de clase:

https://themultiverse.school/classes/245

La oferta pública de la Clase 245 funcionó como piso mínimo del workshop. De allí provienen los compromisos centrales de:

- explicar qué es un modelo local;
- evaluar qué modelos puede ejecutar el hardware disponible;
- elegir según hardware, tarea y cuantización;
- instalar y ejecutar modelos usando runners locales;
- comparar opciones de escritorio;
- mostrar PocketPal brevemente;
- evaluar velocidad, calidad y limitaciones;
- decidir entre local, cloud o un flujo híbrido.

## 2. Fuentes de alineación curricular de Multiverse

El workshop no es una copia de un único curso previo. Combina y adapta material distribuido en distintas partes del curriculum de Multiverse.

Las rutas siguientes se registran como **fuentes de alineación**, no como archivos incluidos en este repositorio.

### Local models como workflow práctico

`Curriculum/Autonomous Agents/Control AI Spend/Control AI Spend Syllabus.md`

Aportó material sobre:

- razones prácticas para ejecutar localmente;
- hardware y memoria;
- tamaño de modelos;
- runners;
- opciones desktop/mobile;
- relación entre hardware, modelo y ejecución.

### Hardware, tamaño de modelo y cuantización

`Curriculum/Autonomous Agents/Prompt Engineering/Prework Day 1.md`

Aportó material sobre:

- local vs. remote;
- hardware self-assessment;
- notación de tamaño de modelos;
- cuantización;
- relación entre recursos y calidad;
- ejecución local frente a endpoints remotos.

### Explicación compacta de ejecución local

`Curriculum/Interactive Tutors/Run AI Locally 🌎 🌲.md`

Aportó material sobre:

- razones para ejecutar localmente;
- CPU/GPU;
- contexto;
- troubleshooting por memoria;
- fallback CPU-only.

### Selección de modelos por tarea

`Curriculum/Generative AI/0 - Using Large Language Models/Workshop 1 - Foundations and Setup/1.2 LLM Model Comparison and Selection.md`

Aportó el framing de selección por tarea y el uso estratégico de distintos modelos según necesidades y restricciones.

### Local dentro del panorama general de modelos

`Curriculum/Autonomous Agents/plans/Revised LLM Course Structure.md`

Aportó una visión donde los modelos locales son una ruta dentro de un ecosistema más amplio, no un reemplazo universal de los modelos comerciales.

### Comparación local / remoto sobre una misma tarea

`Curriculum/Autonomous Agents/Intro to Agents/Building Your Own Agent Framework/Exercise - Local Model Testing.md`

Aportó el patrón de ejecutar tareas comparables en local y remoto para observar diferencias de calidad, velocidad y trade-offs.

### Tokens, embeddings y fundamentos

`Curriculum/Autonomous Agents/Context Engineering/Workshop 1 - Tokens, Embeddings, and Vector Math.md`

Utilizado sólo como apoyo conceptual para tokens, contexto y técnicas adyacentes. El workshop no enseña matemática de vectores en profundidad.

### Inferencia y sampling

`Curriculum/Autonomous Agents/Context Engineering/Workshop 2 - Inference, Temperature, and Sampling.md`

Utilizado como grounding conceptual para inferencia y controles que pueden aparecer en runners.

### Context windows

`Curriculum/Autonomous Agents/Context Engineering/Workshop 3 - Context Windows and Token Management.md`

Utilizado para explicar contexto como una restricción operacional y de recursos.

### RAG

Fuentes del curriculum de Context Engineering y Prompt Engineering sobre RAG se utilizaron únicamente para delimitar conceptos y evitar confundir:

- ejecutar un modelo;
- darle contexto;
- conectarlo a documentos;
- entrenarlo o ajustarlo.

RAG no forma parte del núcleo de este workshop.

### Fine-tuning

Materiales de Context Engineering sobre fine-tuning se utilizaron como frontera conceptual. El workshop no enseña implementación de fine-tuning.

### Estándares de capacidades LLM

`Programs/standards/llm/README.md`

Se utilizó para comprobar alineación con capacidades existentes de Multiverse relacionadas con:

- modelos open-source;
- inferencia;
- benchmarking;
- ejecución en hardware personal;
- ejecución de modelos abiertos en infraestructura remota.

## 3. Artefactos propios que consolidan el workshop

Los siguientes documentos internos fueron utilizados durante el diseño y consolidación del workshop, pero no forman parte necesariamente del paquete público:

- `00 - Research & Adaptation Notes - Local Models.md`
- `01 - Spec Design - Local Models.md`
- `Local-Models_outline.md`

La versión pública consolidada del curriculum es:

- `curriculum/syllabus.md`

El syllabus público prevalece como representación del workshop impartido cuando un documento histórico de diseño conserva decisiones posteriormente modificadas.

## 4. Herramientas y referencias públicas utilizadas

### Local Model Bench

Versión live utilizada por el workshop:

https://themultiverse.school/x/uso-de-modelos-locales

El Bench organiza el recorrido tarea → hardware → selección → ejecución → evaluación → routing.

La implementación publicada en este repositorio conserva su propio registro de fuentes y evidencia técnica dentro de sus datos.

### Mapa de Compatibilidad LLM

https://aelius23.github.io/intro-ia-hispanohablantes/mapa-compatibilidad-llm.html

Utilizado como superficie complementaria para relacionar tarea, capacidades y selección de modelos.

### Hugging Face

https://huggingface.co/

Utilizado como referencia para leer repositorios y fichas de modelos.

### Jan

Runner principal de práctica en la versión consolidada del workshop.

### GPT4All

Runner alternativo utilizado como ruta más sencilla durante la práctica.

### PocketPal

Utilizado como demostración móvil del facilitador. No constituye un checkpoint obligatorio ni una instalación colectiva.

## 5. Evidencia técnica del Bench

El clon público de Local Model Bench incluye su propia capa de procedencia técnica. En la implementación validada existen registros separados para:

- catálogo de modelos;
- runners;
- reglas de hardware;
- benchmark / prueba fija;
- troubleshooting;
- referencias;
- fuentes y tipos de evidencia.

Ese material viaja con el Bench y no se duplica aquí. Este archivo documenta la procedencia curricular y conceptual del workshop completo.

## 6. Regla para fuentes volátiles

Recomendaciones de modelos, versiones de runners, compatibilidad, requisitos de hardware, benchmarks, velocidades y pasos de interfaz pueden cambiar.

Cuando se actualice o vuelva a facilitar el workshop:

- verificar nuevamente las afirmaciones técnicas que dependan de versiones actuales;
- registrar la fecha de la verificación cuando corresponda;
- mantener separada la evidencia histórica de la recomendación vigente;
- actualizar este archivo sólo cuando cambie la procedencia pública del workshop.
