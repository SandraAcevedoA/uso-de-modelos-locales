<a id="inicio"></a>

# Uso de Modelos Locales

**Autora:** Sandra Acevedo · [GitHub](https://github.com/SandraAcevedoA)
**Escuela:** Multiverse School
**Clase 245 · 4 de septiembre de 2026 · 180 minutos · español · todos los niveles**

<a id="nav"></a>

## Mapa de navegación

[Qué significa local](#local) · [Hardware](#hardware) · [Leer modelos](#modelos) · [Local Model Bench](#bench) · [Ejecutar](#ejecutar) · [Evaluar](#evaluar) · [Local / Cloud / Hybrid](#routing) · [Local Model Plan](#plan) · [Profundización](#profundizar)

---

<a id="local"></a>

## Sección I — ¿Qué significa correr un modelo localmente?


### Video Raw Workshop Sept/04
https://drive.google.com/file/d/1CVZrUS8faYMiOBKWOcj5DV7dRNVS3Fzw/view

*Empezaremos por entender la relacion entre tipo tarea y hardware, para luego decidir cual modelo descargar.*

### Objetivos · Local

* Distinguir entre inferencia local, inferencia en la nube y flujos híbridos.
* Reconocer cuándo una aplicación instalada en el computador todavía depende de un modelo ejecutándose remotamente.
* Entender qué cambia cuando la inferencia ocurre en nuestro propio dispositivo.
* Identificar razones prácticas, ventajas y desventajas de las tres modalidades. 

### Puntos clave · Local

* **Local**  describe dónde ocurre la inferencia ademas de dónde está instalada la interfaz.
* Una aplicación de escritorio puede seguir enviando datos a un servicio remoto.
* Ejecutar localmente puede ofrecer ventajas de privacidad, continuidad, control de costos, experimentación y acceso sin conexión una vez que los componentes necesarios están disponibles.
* Esas ventajas tienen un costo: hardware limitado, modelos más pequeños, configuración, almacenamiento y rendimiento.
* El workshop busca ayudarte a decidir **qué arquitectura corresponde a una tarea concreta**.

### El punto de partida: la tarea

Antes de elegir un modelo, define algo que realmente quieras hacer.
Abrir [Mapa de Compatibilidad LLM](https://aelius23.github.io/intro-ia-hispanohablantes/mapa-compatibilidad-llm.html)

Puede ser, por ejemplo:

* resumir documentos;
* reescribir o transformar texto;
* extraer información;
* clasificar contenido;
* generar ideas;
* trabajar con material privado;
* producir borradores repetidamente;
* experimentar con modelos sin depender de una API.

La pregunta inicial no es:

> **¿Qué modelo debería descargar?**

Es:

> **¿Qué quiero hacer y qué condiciones importan para esa tarea?**

Algunas condiciones pueden cambiar completamente la decisión:

* privacidad de los datos;
* necesidad de información actual;
* idioma;
* longitud del material;
* velocidad necesaria;
* calidad esperada;
* posibilidad de trabajar offline;
* costo de equivocarse.

**Output:** una tarea candidata y las condiciones que importan para realizarla.

*[Volver al mapa](#nav)*

---

<a id="hardware"></a>

## Sección II — ¿Qué puede correr mi máquina?

*El hardware como límite operativo*
Abrir [Deck Interactivo](https://themultiverse.school/x/uso-de-modelos-locales)
### Objetivos · Hardware

* Identificar las características del computador que importan para inferencia local.
* Entender RAM, VRAM y memoria compartida o unificada a un nivel práctico.
* Reconocer que cargar un modelo no es lo mismo que ejecutarlo cómodamente.
* Construir un **Hardware Envelope** que permita descartar opciones inviables antes de descargar modelos.

### Puntos clave · Hardware

* Los modelos locales compiten por recursos con el sistema operativo y las demás aplicaciones abiertas.
* La memoria disponible importa tanto como el tamaño nominal del modelo.
* Una GPU puede acelerar considerablemente la inferencia, pero una GPU dedicada no es requisito para aprender ni para ejecutar todos los modelos.
* CPU, RAM, GPU, VRAM, almacenamiento y contexto intervienen de formas distintas.
* El objetivo no es ocupar hasta el último megabyte disponible. Necesitamos **headroom** para que el resto de la máquina siga funcionando.

### Hardware Envelope

Para este workshop registraremos al menos:

* sistema operativo;
* RAM disponible;
* GPU, si existe;
* VRAM o memoria gráfica disponible, cuando corresponda;
* memoria unificada o compartida, cuando corresponda;
* almacenamiento libre relevante;
* cualquier restricción práctica del equipo durante la clase.

A partir de ese perfil podemos comenzar a responder:

> **¿Qué rango de modelos tiene sentido mirar en esta máquina?**

No estamos construyendo una guía de compra.

Estamos aprendiendo a leer el computador que ya tenemos.

### Checkpoint · Perfil de hardware

Al terminar esta sección debes poder describir tu equipo y decir, en términos prácticos, qué implica para ejecutar modelos locales.

**Output:** Hardware Envelope.

*[Volver al mapa](#nav)*

---

<a id="modelos"></a>

## Sección III — Cómo leer un modelo antes de descargarlo

*Del nombre del archivo a una decisión*

### Objetivos · Modelos

* Interpretar la información mínima necesaria para evaluar un modelo local.
* Entender qué significan parámetros, tamaño, cuantización y contexto en una decisión práctica.
* Separar compatibilidad con el hardware de utilidad para una tarea.
* Evitar elegir automáticamente el modelo más grande o más popular.

### Puntos clave · Modelos

Un nombre o una ficha de modelo puede contener mucha información. No toda importa de la misma manera.

Para este workshop nos concentraremos en:

* **Familia y publisher:** de dónde viene el modelo.
* **Cantidad de parámetros:** una señal aproximada de escala, no una puntuación universal de calidad.
* **Tamaño del archivo:** cuánto debemos almacenar y cargar.
* **Cuantización:** con qué precisión se representan los pesos.
* **Contexto:** cuánto material puede mantenerse disponible durante una interacción.
* **Idiomas y capacidades declaradas.**
* **Uso previsto y restricciones conocidas.**

### Parámetros no equivalen a “mejor”

Un modelo más grande puede ofrecer capacidades adicionales y, al mismo tiempo:

* no caber en nuestra máquina;
* ejecutarse demasiado lentamente;
* consumir recursos innecesarios;
* no ser especialmente bueno para nuestra tarea;
* producir una experiencia peor que un modelo más pequeño bien elegido.

La pregunta correcta no es:

> **¿Cuál es el modelo más poderoso?**

Sino:

> **¿Cuál es suficientemente capaz para esta tarea dentro de las restricciones de esta máquina?**

### Cuantización

La cuantización reduce la precisión utilizada para representar los pesos del modelo.

En términos prácticos puede permitir:

* archivos más pequeños;
* menor consumo de memoria;
* ejecutar modelos que de otra forma no cabrían en determinado hardware.

La concesión potencial es pérdida de calidad o capacidad.

Por eso una cuantización no se elige aislada del modelo, la tarea y el computador.

### Contexto

El contexto también consume recursos.

Que un modelo declare una ventana de contexto muy grande no significa que debamos utilizarla completa.

La configuración correcta es la que permite resolver la tarea con suficiente margen, no necesariamente la cifra máxima admitida.

### Tres tipos de encaje

Durante el workshop mantendremos separadas tres preguntas:

#### Hardware Fit

**¿Puede ejecutarse razonablemente en esta máquina?**

#### Task Fit

**¿Tiene capacidades apropiadas para lo que quiero hacer?**

#### Operational Fit

**Aunque pueda ejecutarlo y pueda realizar la tarea, tiene sentido hacerlo localmente bajo estas condiciones?**

Confundir esas tres preguntas es una de las maneras más rápidas de terminar con el modelo equivocado.

*[Volver al mapa](#nav)*

---

<a id="bench"></a>

## Local Model Bench

*Convertir hardware + tarea + modelo en una decisión examinable*

Local Model Bench es la herramienta interactiva principal de este workshop.

No reemplaza la lectura de modelos ni toma automáticamente la decisión final. Organiza la información necesaria para poder tomarla.

El recorrido sigue esta secuencia:

> **TAREA → HARDWARE → LEER → COMPARAR → ELEGIR → CONFIGURAR → EJECUTAR → EVALUAR → DECIDIR**

### Qué hace el Bench

A medida que avanzas, el Bench acumula:

* tu escenario de uso;
* tu Hardware Envelope;
* candidatos compatibles;
* modelo elegido;
* cuantización;
* contexto;
* runner;
* prueba;
* observaciones;
* evaluación;
* decisión de routing.

### Qué no hace

El Bench no entrega un ranking universal de modelos.

Tampoco pretende decidir por ti cuál es “el mejor”.

Su función es volver visibles:

* restricciones;
* evidencia;
* concesiones;
* incertidumbre;
* razones detrás de una elección.

### Herramienta interactiva

<iframe
  src="https://themultiverse.school/x/uso-de-modelos-locales"
  width="100%"
  height="750"
  frameborder="0"
  style="border:1px solid #30363d; border-radius:12px;">
</iframe>

> **Si el Bench no carga arriba**, ábrelo directamente:
> [Local Model Bench](https://themultiverse.school/x/uso-de-modelos-locales)

El Bench será desplegado primero en **acevedology** como implementación de prueba. La versión estabilizada del workshop podrá posteriormente alojarse en infraestructura de Multiverse.

*[Volver al mapa](#nav)*

---

<a id="ejecutar"></a>

## Sección IV — Ejecutar un modelo local

*Del modelo elegido a inferencia real*

### Objetivos · Ejecución

* Entender qué función cumple un runner.
* Recorrer una ejecución local completa con Jan, y con GPT4All como alternativa más sencilla.
* Reconocer las configuraciones que materialmente afectan la prueba.
* Diagnosticar cuándo una limitación pertenece al modelo, al hardware, al runner o a las condiciones de ejecución.

### Puntos clave · Ejecución

Un archivo de modelo no se ejecuta solo.

Necesitamos software capaz de:

* cargarlo;
* administrar memoria;
* enviarle prompts;
* ejecutar inferencia;
* mostrar la respuesta;
* exponer, cuando sea posible, información sobre rendimiento y configuración.

A esa capa la llamaremos **runner**.

### Jan y GPT4All · ruta práctica principal

Durante el workshop utilizaremos principalmente Jan, y GPT4All como alternativa más sencilla y amigable para usuarios de Windows, para recorrer el flujo completo:

1. abrir el runner;
2. localizar o seleccionar el modelo;
3. cargarlo;
4. revisar la configuración relevante;
5. introducir el prompt;
6. generar una respuesta;
7. observar el comportamiento de la ejecución.

Jan y GPT4All son nuestra superficie práctica, no el contenido conceptual del workshop.

El mismo razonamiento sobre hardware, modelos, cuantización, contexto y evaluación debe poder trasladarse a otros runners.

### Preparación y descargas

Descargar un modelo antes de la sesión es **recomendado, no obligatorio**.

La clase no esperará colectivamente una descarga grande.

La facilitación utilizará modelos previamente descargados y probados para que la demostración pueda continuar independientemente del estado de las descargas individuales.

### Si tu equipo no puede ejecutar el modelo durante la clase

Eso no elimina el aprendizaje.

La evidencia consiste en poder documentar:

* hasta qué punto llegaste;
* qué ocurrió;
* qué restricción encontraste;
* cómo la identificaste;
* qué alternativa corresponde.

Por ejemplo:

> “Este modelo podría ejecutarse en mi computador bajo otras condiciones, pero no tengo suficiente memoria disponible mientras mantengo abierta la videollamada de la clase.”

Eso es un diagnóstico.

No es un fracaso del ejercicio.

### PocketPal

PocketPal aparecerá como demostración móvil del facilitador.

No será una instalación colectiva ni un checkpoint requerido.

**Output:** Run Card o bitácora de ejecución.

*[Volver al mapa](#nav)*

---

<a id="evaluar"></a>

## Sección V — Que corra no significa que sirva

*Evaluar antes de adoptar*

### Objetivos · Evaluación

* Separar éxito técnico de utilidad.
* Evaluar calidad, velocidad y limitaciones como dimensiones distintas.
* Utilizar una prueba reproducible en vez de una impresión general.
* Observar diferencias entre modelos o configuraciones sin convertir una sola prueba en un benchmark universal.

### Puntos clave · Evaluación

La primera generación de texto solo demuestra una cosa:

> **El pipeline produjo una salida.**

Todavía no sabemos si esa salida es adecuada.

Por eso la prueba registra dimensiones separadas.

### Calidad y comportamiento

Podemos observar:

* seguimiento de instrucciones;
* información relevante recuperada;
* omisiones;
* contradicciones;
* estructura;
* idioma;
* afirmaciones no sustentadas;
* errores importantes para la tarea.

### Rendimiento

Cuando el runner lo permita podemos observar:

* tiempo hasta comenzar a responder;
* tiempo total;
* tokens por segundo u otras métricas disponibles;
* estabilidad;
* presión sobre el sistema;
* experiencia práctica de uso.

### Limitaciones

También registramos qué no funcionó.

Una respuesta aparentemente buena puede revelar:

* incapacidad para manejar determinado contexto;
* debilidad en español;
* instrucciones ignoradas;
* pérdida de información;
* velocidad insuficiente;
* errores factuales;
* comportamiento inestable.

### Ejemplos del workshop

Las respuestas mostradas como ejemplos en este workshop provienen de ejecuciones reales de modelos locales realizadas durante la preparación de la clase.

No se utilizarán outputs sintéticos presentados como si hubieran sido generados por esos modelos.

### Checkpoint · Evaluación

**Output:** ficha con observaciones de velocidad, calidad y limitaciones.

*[Volver al mapa](#nav)*

---

<a id="routing"></a>

## Sección VI — ¿Dónde debería vivir esta tarea?

*Local / Cloud / Hybrid como decisión de routing*

### Objetivos · Routing

* Convertir las observaciones anteriores en una decisión operacional.
* Reconocer que la misma persona puede usar diferentes arquitecturas para diferentes tareas.
* Evitar presentar local y cloud como bandos opuestos.
* Justificar una elección con evidencia de la prueba.

### Puntos clave · Routing

Después de ejecutar y evaluar podemos volver a la pregunta inicial:

> **¿Dónde tiene sentido realizar esta tarea?**

### Local

Puede tener sentido cuando pesan especialmente:

* privacidad;
* ubicación de los datos;
* trabajo offline;
* repetibilidad;
* control de costos;
* independencia de un proveedor;
* automatizaciones acotadas;
* capacidad suficiente del hardware disponible.

### Cloud

Puede ser preferible cuando necesitamos:

* capacidades superiores a las disponibles localmente;
* información actual o herramientas externas;
* contextos o cargas que exceden nuestro equipo;
* velocidad o calidad que el hardware local no entrega;
* evitar administrar modelos y recursos localmente.

### Hybrid

Muchas tareas no necesitan elegir un solo lado.

Por ejemplo:

* clasificación local + síntesis final en cloud;
* preparación privada local + investigación externa remota;
* borrador local + revisión con un modelo de mayor capacidad;
* procesamiento rutinario local + escalamiento de casos difíciles.

El punto no es maximizar el porcentaje de trabajo local.

Es colocar cada parte del trabajo donde sus restricciones y beneficios tengan sentido.

### Checkpoint · Decisión

Formula tu decisión:

**Local / Cloud / Hybrid**

y acompáñala con al menos una razón proveniente de lo que observaste.

**Output:** decisión de routing fundamentada.

*[Volver al mapa](#nav)*

---

<a id="plan"></a>

## My Local Model Plan

*El artefacto que queda después del workshop*

Local Model Bench reúne las decisiones tomadas durante la sesión en un plan reutilizable.

Tu Local Model Plan registra:

* tarea;
* condiciones importantes;
* Hardware Envelope;
* modelo seleccionado;
* razones de la selección;
* cuantización;
* contexto;
* runner;
* configuración de prueba;
* resultados disponibles;
* observaciones;
* limitaciones;
* decisión Local / Cloud / Hybrid.

El valor del plan no está en congelar una recomendación.

Los modelos cambiarán.

Los runners cambiarán.

Tu hardware también puede cambiar.

Lo durable es poder repetir el proceso:

> **inspeccionar → leer → elegir → ejecutar → observar → decidir**

con otro modelo, otra tarea o otra máquina.

*[Volver al mapa](#nav)*

---

<a id="profundizar"></a>

## Líneas de profundización posibles

Este workshop se concentra deliberadamente en ejecutar y evaluar modelos locales sobre hardware personal.

Algunos temas relacionados quedan fuera de estas tres horas y pueden convertirse en rutas posteriores:

* otros runners y ecosistemas de ejecución local;
* GGUF y formatos de modelos con mayor profundidad técnica;
* inferencia y sampling;
* embeddings;
* RAG;
* vector databases;
* fine-tuning y LoRA;
* APIs locales;
* agentes y tool calling;
* MCP;
* servidores locales dedicados;
* aceleradores especializados, NPU y SBC;
* evaluación y benchmarking más sistemáticos.

Estos temas no son prerequisitos para utilizar el proceso aprendido aquí.

*[Volver al mapa](#nav)*

---

## Recorrido de la sesión

| Bloque                                 |      Tiempo |
| -------------------------------------- | ----------: |
| Tarea + qué significa local            |      30 min |
| Hardware Envelope                      |      25 min |
| Leer y elegir modelos                  |      25 min |
| **Break**                              |  **15 min** |
| Runner y ejecución                     |      35 min |
| Alternativas de escritorio + PocketPal |      10 min |
| Prueba y evaluación                    |      25 min |
| Local / Cloud / Hybrid + cierre        |      15 min |
| **Total**                              | **180 min** |

---

## Evidencia mínima de aprendizaje

Al terminar habrás producido cinco piezas de evidencia:

1. **Hardware Envelope** — qué recursos tiene tu equipo y qué implican.
2. **Model Choice** — qué modelo elegiste y por qué.
3. **Run Card / bitácora** — cómo se configuró la prueba y hasta dónde llegó la ejecución.
4. **Evaluation** — velocidad, calidad y limitaciones observadas.
5. **Routing Decision** — Local / Cloud / Hybrid y la evidencia que sostiene esa decisión.

Estas piezas terminan reunidas en **My Local Model Plan**.

La inferencia local exitosa en el computador del participante no es requisito para completar el workshop. Diagnosticar correctamente una restricción y seguir la ruta de respaldo demuestra la misma capacidad de decisión que estamos enseñando.

---

<details>
<summary><strong>Uso de Modelos Locales — Syllabus</strong></summary>

Este syllabus organiza el workshop en tres bloques de facilitación. El curriculum completo desarrolla los conceptos, ejercicios y checkpoints enlazados desde cada bloque.

## Bloque 1 — Entender qué estamos corriendo
**Duración:** 55 min + 5 min break

### Lecciones
- [¿Qué significa correr un modelo localmente?](#local)
- [El punto de partida: la tarea](#local)
- [¿Qué puede correr mi máquina?](#hardware)

### Ejercicio
- **Hardware Envelope**

---

## Bloque 2 — Elegir y ejecutar
**Duración:** 55 min + 5 min break

### Lecciones
- [Cómo leer un modelo antes de descargarlo](#modelos)
- Hardware Fit
- Task Fit
- Operational Fit
- [Local Model Bench](#bench)
- [Ejecutar un modelo local](#ejecutar)

### Ejercicios
- **Model Choice**
- **Run Card / bitácora de ejecución**

---

## Bloque 3 — Evaluar y decidir
**Duración:** 60 min

### Lecciones
- Alternativas de escritorio y PocketPal
- [Que corra no significa que sirva](#evaluar)
- [¿Dónde debería vivir esta tarea?](#routing)
- [My Local Model Plan](#plan)

### Ejercicios
- **Capability Evaluation**
- **Routing Decision**
- **My Local Model Plan**

---

## Resources

* [Local Model Bench](https://themultiverse.school/x/uso-de-modelos-locales)
* [Mapa de Compatibilidad LLM](https://aelius23.github.io/intro-ia-hispanohablantes/mapa-compatibilidad-llm.html)

    - Materiales de referencia y profundización:
* [HuggingFace Homepage](https://huggingface.co/)

</details>

---

*Contenido © Sandra Acevedo · Multiverse School.*

