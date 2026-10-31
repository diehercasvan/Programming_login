# Documento Consolidado: 

### 5 Sistemas con Requerimientos Funcionales, No Funcionales y Criterios de Aceptación

---

## 1. Sistema de Gestión de Parqueadero con Visión por Computadora

**Problema:** No se cuenta con la sistematización de registros de vehículos en un parqueadero. Se requiere un sistema que, mediante fotos, permita conocer la disponibilidad de parqueaderos y validar la presencia de los vehículos.

### Requerimientos Funcionales (RF)

| Código       | Requerimiento                                                                                                                                           | Criterio de Aceptación                                                                                                                                                                                                              |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **RF1** | Registrar entrada y salida de vehículos mediante captura fotográfica (placa y/o reconocimiento visual), almacenando fecha, hora y número de espacio. | **Dado** un vehículo que ingresa, **cuando** la cámara captura la placa y el operario confirma, **entonces** el sistema almacena placa, fecha, hora y espacio, y lo muestra en el listado de vehículos activos. |
| **RF2** | Procesar imágenes de las zonas de parqueo para determinar y mostrar en tiempo real la disponibilidad (ocupado/libre).                                  | **Dado** un espacio monitoreado por cámara, **cuando** se captura una imagen, **entonces** el sistema actualiza el estado del espacio en el tablero en máximo 3 segundos.                                        |
| **RF3** | Validar mediante comparación de fotos si un vehículo registrado se encuentra en el espacio asignado.                                                  | **Dado** un vehículo con registro de entrada, **cuando** se procesa una nueva foto del espacio, **entonces** el sistema confirma si la placa coincide y marca "coincidente" o "no coincidente".                   |
| **RF4** | Generar reportes de ocupación, tiempos de permanencia y tarifas calculadas por vehículo.                                                              | **Dado** un vehículo que finaliza su permanencia, **cuando** se registra la salida, **entonces** el sistema calcula la tarifa y genera un reporte PDF descargable.                                                |
| **RF5** | Permitir consulta histórica de registros por placa, fecha o espacio, con visualización de fotos asociadas.                                            | **Dado** un usuario autorizado, **cuando** consulta por placa, fecha o espacio, **entonces** el sistema muestra el historial completo con las fotos asociadas.                                                     |

### Requerimientos No Funcionales (RNF)

| Código        | Requerimiento                                                                                                  |
| -------------- | -------------------------------------------------------------------------------------------------------------- |
| **RNF1** | El reconocimiento de placas debe tener precisión mínima del 95% en condiciones de iluminación normales.     |
| **RNF2** | La actualización de disponibilidad debe reflejarse en la interfaz en menos de 3 segundos tras la captura.     |
| **RNF3** | Las imágenes deben almacenarse cifradas y cumplir con la normativa de protección de datos personales.        |
| **RNF4** | El sistema debe estar disponible 24/7 con disponibilidad mínima del 99.5%.                                    |
| **RNF5** | La interfaz debe ser usable en móviles y pantallas de consulta, con tiempo de aprendizaje menor a 30 minutos. |

---

## 2. Sistema de Inventario con POS y Facturación

**Problema:** Se requiere un sistema de inventario que gestione proveedores y clientes, integre un sistema POS y permita la generación de facturas.

### Requerimientos Funcionales (RF)

| Código       | Requerimiento                                                                                                | Criterio de Aceptación                                                                                                                                                                                              |
| ------------- | ------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **RF1** | Registrar, editar y consultar proveedores y clientes con datos de contacto e historial.                      | **Dado** un administrador en el módulo de terceros, **cuando** registra un proveedor/cliente con campos obligatorios, **entonces** el sistema lo guarda y permite consultarlo y editarlo.         |
| **RF2** | Gestionar inventario (entradas, salidas, ajustes y alertas de stock mínimo) actualizándose con cada venta. | **Dado** un producto con stock mínimo definido, **cuando** una venta reduce el inventario por debajo del mínimo, **entonces** el sistema descuenta la cantidad y genera alerta de stock bajo.    |
| **RF3** | POS para registrar ventas, aplicar descuentos/impuestos y seleccionar métodos de pago.                      | **Dado** un cajero en el POS, **cuando** registra productos, aplica descuento/impuesto y selecciona pago, **entonces** el sistema confirma la venta y actualiza inventario en menos de 2 segundos. |
| **RF4** | Generar facturas en PDF con numeración consecutiva y datos fiscales, enviables por correo.                  | **Dado** una venta confirmada, **cuando** se solicita la factura, **entonces** el sistema genera un PDF con numeración consecutiva y datos fiscales, y permite su envío por correo.              |
| **RF5** | Emitir reportes de ventas, rotación de inventario y cuentas por pagar/cobrar por proveedor y cliente.       | **Dado** un usuario con permisos, **cuando** selecciona un rango de fechas, **entonces** el sistema genera reportes de ventas, rotación y cuentas por pagar/cobrar exportables.                   |

### Requerimientos No Funcionales (RNF)

| Código        | Requerimiento                                                                                    |
| -------------- | ------------------------------------------------------------------------------------------------ |
| **RNF1** | Debe soportar al menos 50 usuarios concurrentes y 10 cajas POS simultáneas sin degradación.    |
| **RNF2** | Las transacciones de venta deben completarse en menos de 2 segundos y ser atómicas (ACID).      |
| **RNF3** | Respaldos automáticos diarios y recuperación ante fallos en menos de 1 hora.                   |
| **RNF4** | La facturación debe cumplir con los requisitos tributarios locales (facturación electrónica). |
| **RNF5** | Autenticación por roles y registro de auditoría de todas las operaciones sensibles.            |

---

## 3. Sistema PQRS con Chatbot

**Problema:** Se necesita un sistema de Peticiones, Quejas, Reclamos y Sugerencias (PQRS) que incorpore chatbots para la atención y radicación automática.

### Requerimientos Funcionales (RF)

| Código       | Requerimiento                                                                                             | Criterio de Aceptación                                                                                                                                                                                                |
| ------------- | --------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **RF1** | Radicar PQRS por múltiples canales (web, chatbot, correo) generando número de radicado único.          | **Dado** un ciudadano que radica una PQRS por cualquier canal, **cuando** completa los datos requeridos, **entonces** el sistema genera un número de radicado único y lo notifica.                 |
| **RF2** | El chatbot debe interpretar la solicitud, clasificar el tipo de PQRS y guiar la radicación.              | **Dado** un usuario interactuando con el chatbot, **cuando** describe su solicitud, **entonces** el chatbot clasifica el tipo de PQRS, guía la radicación y escala a humano si no comprende.       |
| **RF3** | Asignar y enrutar cada PQRS al área responsable según reglas configurables, con seguimiento de estados. | **Dado** una PQRS radicada, **cuando** el sistema aplica reglas de enrutamiento, **entonces** la asigna al área responsable y permite visualizar y actualizar su estado.                            |
| **RF4** | Notificar al usuario por correo/SMS sobre el avance y respuesta de su PQRS.                               | **Dado** un cambio de estado en una PQRS, **cuando** ocurre la transición, **entonces** el sistema notifica al usuario con el nuevo estado y la respuesta si existe.                                |
| **RF5** | Generar indicadores (tiempos de respuesta, volumen por tipo, satisfacción) y reportes de cumplimiento.   | **Dado** un administrador, **cuando** solicita indicadores del periodo, **entonces** el sistema genera reportes de tiempos, volumen por tipo y satisfacción, con cumplimiento de términos legales. |

### Requerimientos No Funcionales (RNF)

| Código        | Requerimiento                                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **RNF1** | El chatbot debe responder en menos de 2 segundos y resolver al menos el 70% de consultas frecuentes sin escalamiento humano. |
| **RNF2** | Trazabilidad completa de cada PQRS con logs inmutables por al menos 5 años.                                                 |
| **RNF3** | Cumplir con términos legales de respuesta (p. ej., 15 días hábiles) mediante alertas automáticas.                        |
| **RNF4** | Interfaz accesible (WCAG 2.1 AA) y adaptable a dispositivos móviles.                                                        |
| **RNF5** | Soportar picos de 500 radicaciones simultáneas con disponibilidad del 99%.                                                  |

---

## 4. Sistema de Gestión de Asistencias a Eventos con Registro Fotográfico

**Problema:** Se requiere un sistema para gestionar asistencias a eventos, con conteo y registro de participantes mediante fotos.

### Requerimientos Funcionales (RF)

| Código       | Requerimiento                                                                                                        | Criterio de Aceptación                                                                                                                                                                           |
| ------------- | -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **RF1** | Crear eventos, definir cupos, fechas y generar códigos QR de registro para asistentes.                              | **Dado** un organizador, **cuando** crea un evento con cupos y fechas, **entonces** el sistema lo registra y genera códigos QR de inscripción.                                |
| **RF2** | Registrar asistencia mediante captura fotográfica y/o reconocimiento facial, asociándola al participante inscrito. | **Dado** un participante inscrito, **cuando** se captura su foto en el punto de registro, **entonces** el sistema lo asocia al participante y marca su asistencia.              |
| **RF3** | Realizar conteo automático en tiempo real de asistentes y compararlo con el aforo autorizado.                       | **Dado** un evento en curso, **cuando** se registran asistentes, **entonces** el sistema muestra el conteo en tiempo real y alerta si se supera el aforo.                       |
| **RF4** | Emitir certificados de asistencia personalizados y exportables.                                                      | **Dado** un evento finalizado, **cuando** el organizador solicita certificados, **entonces** el sistema genera certificados personalizados y exportables por asistente.         |
| **RF5** | Generar reportes de asistencia por evento, sesión y participante, con evidencia fotográfica.                       | **Dado** un organizador, **cuando** solicita el reporte de un evento, **entonces** el sistema muestra asistencia por evento, sesión y participante con evidencia fotográfica. |

### Requerimientos No Funcionales (RNF)

| Código        | Requerimiento                                                                                                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------ |
| **RNF1** | El reconocimiento facial debe alcanzar al menos 98% de precisión y procesar cada registro en menos de 2 segundos. |
| **RNF2** | Operar en modo offline en el punto de registro y sincronizar al recuperar conexión.                               |
| **RNF3** | Fotos y datos biométricos con consentimiento explícito y cifrado conforme a la ley de protección de datos.      |
| **RNF4** | Soportar eventos de hasta 5,000 asistentes con registros concurrentes sin pérdida de datos.                       |
| **RNF5** | Usable por personal sin formación técnica, con interfaz táctil y flujo de máximo 3 pasos por registro.         |

---

## 5. Sistema de Evaluación de Condiciones de Cultivos por Foto

**Problema:** Se necesita un sistema que, a partir de una foto, determine si un cultivo se encuentra en buenas o malas condiciones.

### Requerimientos Funcionales (RF)

| Código       | Requerimiento                                                                                               | Criterio de Aceptación                                                                                                                                                                           |
| ------------- | ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **RF1** | Permitir cargar fotos del cultivo (móvil o cámara) asociándolas a lote, fecha y ubicación.              | **Dado** un agricultor en campo, **cuando** carga una foto e indica lote, fecha y ubicación, **entonces** el sistema almacena la imagen asociada a esos datos.                 |
| **RF2** | Analizar la imagen con IA y clasificar el estado del cultivo (bueno/malo) con nivel de confianza.           | **Dado** una imagen cargada, **cuando** el sistema la procesa con el modelo de IA, **entonces** devuelve la clasificación con su nivel de confianza en máximo 5 segundos.     |
| **RF3** | Identificar problemáticas visibles (plagas, enfermedades, deficiencias) y emitir recomendaciones básicas. | **Dado** un resultado de análisis, **cuando** el modelo detecta problemáticas visibles, **entonces** el sistema las lista y emite recomendaciones básicas.                   |
| **RF4** | Registrar historial de evaluaciones por lote y mostrar evolución temporal del estado.                      | **Dado** un lote con evaluaciones previas, **cuando** el usuario consulta su historial, **entonces** el sistema muestra la evolución temporal con fotos y fechas.              |
| **RF5** | Generar alertas ante condiciones desfavorables y reportes exportables por lote o finca.                     | **Dado** una evaluación con resultado desfavorable, **cuando** el sistema la registra, **entonces** genera una alerta al usuario y permite exportar reportes por lote o finca. |

### Requerimientos No Funcionales (RNF)

| Código        | Requerimiento                                                                                                               |
| -------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **RNF1** | El modelo de IA debe alcanzar exactitud mínima del 90% validada con expertos agrónomos.                                   |
| **RNF2** | El análisis de cada imagen debe completarse en menos de 5 segundos y funcionar en móviles de gama media.                  |
| **RNF3** | Funcionar en zonas rurales con conectividad limitada (modo offline con análisis en dispositivo o cola de sincronización). |
| **RNF4** | Escalable para procesar al menos 10,000 imágenes diarias con respaldo.                                                     |
| **RNF5** | Interfaz intuitiva para usuarios con baja alfabetización digital, con iconografía clara y soporte multiidioma.            |

---

## Resumen General

| #               | Sistema                                         | RF           | RNF          | Criterios de Aceptación |
| --------------- | ----------------------------------------------- | ------------ | ------------ | ------------------------ |
| 1               | Parqueadero con Visión por Computadora         | 5            | 5            | 5                        |
| 2               | Inventario con POS y Facturación               | 5            | 5            | 5                        |
| 3               | PQRS con Chatbot                                | 5            | 5            | 5                        |
| 4               | Asistencias a Eventos con Registro Fotográfico | 5            | 5            | 5                        |
| 5               | Evaluación de Cultivos por Foto                | 5            | 5            | 5                        |
| **Total** |                                                 | **25** | **25** | **25**             |

---

**Nota:** Los criterios de aceptación están redactados en formato **Dado/Cuando/Entonces** para los requerimientos funcionales. Los requerimientos no funcionales son verificables mediante pruebas de precisión, carga, seguridad, disponibilidad y usabilidad según las métricas indicadas.
