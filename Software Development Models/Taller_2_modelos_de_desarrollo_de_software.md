# Taller Práctico Avanzado: Modelos de Desarrollo de Software

**Asignatura:** Ingeniería de Software  
**Basado en:** *Software Engineering* (9ª ed.) – Ian Sommerville  
**Duración estimada:** 3 a 4 horas lectivas / trabajo guiado  

---

## 1. Introducción y Objetivos del Taller

El objetivo de este taller es aplicar de manera pragmática los principios de los ciclos de vida de desarrollo de software. A través de escenarios reales, el estudiante analizará cómo estructurar proyectos bajo distintas filosofías metodológicas, gestionando requerimientos, riesgos y entregas de valor.

### Objetivos de Aprendizaje:
1. **Diferenciar** la aplicación práctica del Modelo Incremental/Iterativo frente a la Metodología de Prototipado y otros modelos clásicos y modernos.
2. **Desglosar** un sistema de información complejo en entregables funcionales (incrementos) y en componentes de exploración (prototipos).
3. **Seleccionar** el ciclo de vida óptimo según las restricciones de negocio, nivel de incertidumbre y requerimientos del cliente.

---

## 2. Marco de Uso de Inteligencia Artificial (Escala Nivel 0 a 5)

Para este taller se establece una escala normativa para el uso de herramientas de Inteligencia Artificial Generativa (LLMs, asistentes de código, generadores de maquetas). Cada fase del taller indicará el **Nivel de IA permitido/sugerido**:

* **Nivel 0 (Sin IA - 0%):** Prohibido el uso de IA. Trabajo 100% analítico, manual y reflexivo del estudiante.
* **Nivel 1 (Asistencia Básica - 20%):** Uso de IA limitado a corrección ortográfica, gramatical o aclaración de términos teóricos puntuales.
* **Nivel 2 (Brainstorming y Co-creación - 40%):** Uso de IA para generar ideas iniciales, validar alternativas o refinar la redacción de requerimientos redactados por el estudiante.
* **Nivel 3 (Sugerencia y Esbozo - 60%):** La IA propone estructuras de incrementos o historias de usuario iniciales, las cuales el estudiante debe auditar, corregir y adaptar.
* **Nivel 4 (Generación Asistida Avanzada - 80%):** La IA genera borradores completos de maquetas, código de prototipo o especificaciones, y el estudiante actúa como supervisor técnico y evaluador de calidad.
* **Nivel 5 (Automatización Total - 100%):** Delegación completa del entregable a la IA (Solo aplicable en ejercicios de prueba de concepto automatizada).

---

## 3. Ejemplos Prácticos Detallados por Modelo

---

### Caso Práctico A: Modelo Incremental e Iterativo

#### Escenario: Plataforma de Gestión Académica y Aprendizaje en Línea ("EduFlex")
Una institución universitaria requiere modernizar su plataforma académica. La universidad no puede esperar 12 meses a que el sistema esté terminado; necesita empezar a operar el próximo semestre con las funciones básicas e ir añadiendo módulos periódicamente.

#### Estrategia Incremental:

```
+-----------------------------------------------------------------------------------+
|                                  SISTEMA EDUFLEX                                  |
+-----------------------------------------------------------------------------------+
       |                                  |                                  |
       v                                  v                                  v
+-----------------------+      +-----------------------+      +-----------------------+
|     INCREMENTO 1      |      |     INCREMENTO 2      |      |     INCREMENTO 3      |
|  Núcleo & Inscripción | ---> | Aulas & Calificaciones| ---> | Integración & Analítica|
| (Despliegue: Mes 3)   |      | (Despliegue: Mes 6)   |      | (Despliegue: Mes 9)   |
+-----------------------+      +-----------------------+      +-----------------------+
```

##### 1. Incremento 1: Gestión de Usuarios y Matrícula (Meses 1 - 3)
* **Objetivo:** Permitir el registro de estudiantes, oferta de asignaturas e inscripción en línea antes del inicio de clases.
* **Componentes:**
  * Módulo de autenticación seguro (OAuth 2.0 / Roles: Estudiante, Docente, Admin).
  * Catálogo de asignaturas y horarios.
  * Motor de pre-inscripción y pago de matrícula.
* **Criterio de Aceptación:** Los estudiantes pueden matricular sus asignaturas de forma operativa y los administradores pueden generar listas de clase.

##### 2. Incremento 2: Aula Virtual y Entrega de Tareas (Meses 4 - 6)
* **Objetivo:** Facilitar la interacción académica diaria durante el semestre transcurrido.
* **Componentes:**
  * Publicación de guías y contenidos multimedia por asignatura.
  * Buzón de entrega de trabajos con timestamping.
  * Módulo de calificaciones preliminares y asistencia.
* **Criterio de Aceptación:** Profesores califican entregas en línea y estudiantes consultan notas parciales.

##### 3. Incremento 3: Analítica de Aprendizaje e Integración Administrativa (Meses 7 - 9)
* **Objetivo:** Agregar inteligencia institucional y conectar con sistemas externos de contabilidad.
* **Componentes:**
  * Dashboard de riesgo de deserción escolar basado en desempeño y asistencia.
  * Integración vía API con el sistema financiero y de facturación institucional.
  * Emisión de certificados digitales y boletas oficiales.
* **Criterio de Aceptación:** El equipo directivo genera reportes consolidados sin afectar la operación diaria del aula.

---

### Caso Práctico B: Metodología de Prototipado

#### Escenario: Aplicación Móvil de Logística y Rutas de Entrega ("FastTrack Express")
Una empresa de mensajería urbana desea crear una App móvil para que sus repartidores registren paquetes en tiempo real. Existe alta incertidumbre sobre la usabilidad del sistema en movimiento (mientras conducen o caminan) y sobre el comportamiento del GPS en zonas con mala conectividad.

#### Estrategia de Prototipado Desechable (Throwaway Prototyping):

```
+------------------+     +------------------+     +------------------+     +------------------+
|   Establecer     |     |   Desarrollar    |     |   Evaluación     |     |  Especificación  |
|   Objetivos      | --> |    Prototipo     | --> |   con Choferes   | --> |    Definitiva    |
| (Reducir Riesgo) |     |  (Figma + HTML)  |     |  (Prueba Campo)  |     |   (Para Código)  |
+------------------+     +------------------+     +------------------+     +------------------+
                                                        |
                                                        v (Feedback)
                                          [ Requisitos Modificados ]
```

##### Fases de Ejecución:

1. **Definición de Objetivos del Prototipo:**
   * Validar si la interfaz de usuario (UI) permite registrar la entrega de un paquete en menos de 10 segundos.
   * Probar el flujo de captura de firma digital en pantalla táctil con una sola mano.

2. **Construcción Rápida del Prototipo:**
   * Se crea una maqueta interactiva funcional en Figma/HTML5 rápido, omitiendo la base de datos real.
   * Se simula el seguimiento GPS utilizando coordenadas estáticas codificadas en un archivo `JSON`.

3. **Prueba en Campo y Evaluación por Usuarios (Piloto):**
   * Se entrega el prototipo a 10 repartidores durante una jornada laboral de prueba.
   * **Hallazgos del Feedback:**
     * Los botones estándar de 44px resultan demasiado pequeños cuando el usuario usa guantes.
     * La pantalla blanca deslumbra por las noches y agota rápido la batería.
     * El botón de "Escanear Código QR" se ubica en un menú desplegable muy oculto.

4. **Refinamiento de Especificaciones y Descarte del Prototipo:**
   * Se documentan las especificaciones reales aprendidas: botones de mínimo 64px, tema oscuro automático (Dark Mode), y botón de escaneo en la barra de acceso rápido.
   * Se desecha el código del prototipo y se inicia el desarrollo final sobre una arquitectura móvil sólida (React Native / Flutter) garantizando un diseño estructurado.

---

## 4. Cuadro Comparativo Extendido de Modelos de Desarrollo

| Modelo de Desarrollo | Filosofía y Enfoque | Gestión de Requisitos | Gestión del Cambio | Ventajas Clave | Desventajas / Riesgos | Caso de Uso Ideal |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Cascada (Waterfall)** | Secuencial y rígido. Avance por etapas cerradas. | Congelados al inicio del proyecto. | Muy costoso y complejo de aplicar. | • Alta predictibilidad de costos.<br>• Documentación exhaustiva.<br>• Estructura clara para equipos grandes. | • Sin software funcional hasta etapas finales.<br>• Alto riesgo de falla si los requisitos cambian. | Sistemas críticos de seguridad (aeroespacial, médico) o infraestructura con requisitos normativos fijos. |
| **Incremental e Iterativo** | Construcción por partes operativas (incrementos) mediante ciclos repetitivos. | Priorizados y evolutivos por incremento. | Flexible entre incrementos. | • Entrega temprana de valor de negocio.<br>• Feedback constante del cliente.<br>• Menor costo en cambios moderados. | • Requiere arquitectura sólida inicial.<br>• Riesgo de degradación structural si no se refactoriza. | Portales web corporativos, software SaaS, plataformas educativas o comerciales. |
| **Prototipado** | Exploratorio. Creación de versiones preliminares para validación. | Inciertos; se descubren durante el proceso. | Altamente adaptable durante el diseño. | • Aclara la usabilidad y los requisitos.<br>• Reduce el riesgo de construir el producto equivocado. | • El cliente puede exigir el prototipo como versión final.<br>• No prioriza la calidad del código interno. | Sistemas con alta interacción de usuario (UI/UX compleja) o tecnologías emergentes no probadas. |
| **Modelo en Espiral (Boehm)** | Iterativo orientado y guiado por la evaluación constante de riesgos. | Variables y detallados por ciclo en la espiral. | Planificado al inicio de cada espiral. | • Excelente control de riesgos de negocio y técnicos.<br>• Integra actividades de verificación en todo el ciclo. | • Modelo complejo y de alto costo.<br>• Depende fuertemente de expertos en gestión de riesgos. | Proyectos gigantes de defensa, desarrollo de nuevos sistemas operativos o suites complejas. |
| **Desarrollo Ágil (Scrum)** | Adaptativo, centrado en personas, colaborativo y de iteración muy corta (Sprints). | Dinámicos (Backlog de producto en cambio continuo). | Es la norma básica (el cambio se abraza). | • Máxima velocidad de adaptación.<br>• Entrega de incrementos útiles cada 2-4 semanas.<br>• Transparencia total. | • Menor enfoque en documentación técnica formal.<br>• Riesgo de desvío de alcance si no hay un Product Owner fuerte. | Startups, desarrollo de aplicaciones móviles, productos digitales de mercado cambiante. |

---

## 5. Guía de Trabajo y Actividad Práctica para el Estudiante

### Instrucciones:
Formen equipos de 3 o 4 integrantes. Seleccionen **uno** de los tres problemas de software propuestos y completen las fases de la actividad aplicando los niveles de IA permitidos para cada etapa.

#### Problemas a elegir:
* **Opción A:** Sistema de reserva de turnos y telemedicina para una red de clínicas locales.
* **Opción B:** Plataforma de comercio electrónico (E-commerce) con inventario en tiempo real para una cadena de supermercados.
* **Opción C:** Sistema de monitoreo agrícola IoT que recopila datos de humedad y temperatura en cultivos.

---

### Fase 1: Justificación del Modelo Seleccionado
* **Nivel de IA permitido: Nivel 1 (Asistencia Básica - 20%)** *(El estudiante debe realizar la elección y argumentación técnica; la IA solo puede usarse para corrección ortográfica o validar terminología del libro de Sommerville).*

1. Analicen las características del problema elegido.
2. Definan si el enfoque primario debe ser **Incremental**, **Prototipado** o un **Híbrido**. Justifiquen su respuesta respondiendo:
   * ¿Qué tan claros están los requisitos del cliente desde el primer día?
   * ¿Cuál es el riesgo técnico o de usabilidad más alto?
   * ¿Qué tan urgente es la fecha de lanzamiento para el negocio?

---

### Fase 2: Diseño de la Solución

#### Si eligieron el Modelo Incremental:
* **Nivel de IA permitido: Nivel 2 (Co-creación - 40%)** *(Se permite solicitar a la IA sugerencias de historias de usuario o desgloses, pero el grupo debe auditar, reordenar y definir la prioridad final).*
* Diseñen un **Plan de 3 Incrementos**.
* Para cada incremento completen la siguiente ficha:
  * **Nombre del Incremento:**
  * **Objetivo principal:**
  * **Lista de 3 a 4 funcionalidades incluidas:**
  * **Criterio de Aceptación / Entregable para el usuario:**

#### Si eligieron la Metodología de Prototipado:
* **Nivel de IA permitido: Nivel 3 (Sugerencia y Esbozo - 60%)** *(Pueden utilizar asistentes de IA para generar maquetas interactivas en HTML/Tailwind o guiones de prueba iniciales, debiendo refinar manualmente la interacción de usuario).*
* Identifiquen **3 Incertidumbres Principales** (de requisitos, interfaz o tecnología).
* Diseñen en papel o herramienta digital (Wireframe rápido) **2 Pantallas Clave** para evaluar esas incertidumbres.
* Redacten un **Guión de Pruebas de Usuario** de 4 pasos para validar el prototipo con el cliente final.

---

### Fase 3: Matriz de Riesgo y Evaluación Metodológica
* **Nivel de IA permitido: Nivel 0 (Sin IA - 0%)** *(Reflexión técnica obligatoria en equipo sin asistencia de herramientas automatizadas).*

Responda a las siguientes preguntas de reflexión técnica:
1. Si durante el desarrollo del proyecto el cliente solicita un cambio drástico en el módulo central, ¿cómo responde su modelo seleccionado ante esta eventualidad?
2. Indique dos medidas concretas para evitar que la arquitectura del sistema se degrade con el tiempo.
3. Declaración de transparencia: Indique qué prompts y herramientas de IA utilizó durante las Fases 1 y 2 (si aplica).

---

## 6. Rúbrica de Evaluación

| Criterio | Excepcional (5.0) | Satisfactorio (3.5 - 4.5) | Necesita Mejorar (1.0 - 3.0) |
| :--- | :--- | :--- | :--- |
| **Justificación del Modelo (Nivel 1 IA)** | Argumentación propia y sólida basada en Sommerville, demostrando criterio humano frente al contexto del problema. | Selección correcta del modelo pero con justificación teórica superficial. | Selección inadecuada del modelo para el tipo de problema propuesto. |
| **Desglose Práctico (Nivel 2/3 IA)** | Incrementos claramente acotados con criterios de aceptación verificables, o prototipos bien estructurados auditados críticamente post-IA. | Desglose funcional claro pero con límites ambiguos entre entregables o dependencia excesiva del output directo de la IA. | Desglose confuso, incrementos superpuestos o prototipo generado por IA sin filtrado ni adaptación del alumno. |
| **Análisis de Riesgos y Declaración (Nivel 0 IA)** | Identifica con precisión los riesgos arquitectónicos y plantea medidas concretas sin asistencia de IA. Declara éticamente el uso de herramientas. | Identifica riesgos básicos sin proponer soluciones técnicas profundas. | No reconoce los riesgos ni el impacto de los cambios metodológicos. Oculta el uso de IA. |