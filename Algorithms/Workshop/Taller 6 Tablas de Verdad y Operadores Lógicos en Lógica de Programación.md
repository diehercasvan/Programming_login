
# 📝 Taller: Tablas de Verdad y Operadores Lógicos en Lógica de Programación

**Asignatura:** Lógica de Programación
**Tema:** Operadores Booleanos y Tablas de Verdad
**Basado en:** *Lógica de programación* de Omar Iván Trejos Buriticá (Capítulo 4.4.3)
**Modalidad:** Individual
**Fecha de entrega:** [Insertar fecha]

---

## 🎯 Objetivo del Taller

Comprender el funcionamiento de los operadores lógicos (Y, O, NO) a través de sus tablas de verdad, y aplicar este conocimiento en la construcción de condiciones complejas dentro de algoritmos. El estudiante aprenderá a evaluar expresiones lógicas y a determinar cuándo una condición compuesta es verdadera o falsa.

---

## 📖 Parte 1: Contextualización Teórica

### 1.1. ¿Qué es una tabla de verdad?

Una **tabla de verdad** es una herramienta que muestra todos los resultados posibles de una expresión lógica, combinando los valores de verdad (Verdadero o Falso) de sus componentes. En programación, se usa para evaluar condiciones que involucran más de un operador lógico.

### 1.2. Los operadores lógicos básicos

En lógica de programación, los operadores booleanos permiten conectar expresiones relacionales (como `a > b`, `x = 5`, etc.). Los tres operadores fundamentales son:

| Operador     | Nombre            | Símbolo en pseudocódigo | Ejemplo                |
| :----------- | :---------------- | :------------------------ | :--------------------- |
| **Y**  | AND (conjunción) | `Y`                     | `(a > 5) Y (b < 10)` |
| **O**  | OR (disyunción)  | `O`                     | `(a > 5) O (b < 10)` |
| **NO** | NOT (negación)   | `NO`                    | `NO (a > 5)`         |

### 1.3. Tablas de verdad de los operadores

#### 🔹 Operador Y (AND)

La expresión es **Verdadera** solo si **ambas** condiciones son Verdaderas.

| Condición 1 | Condición 2 | Condición 1 **Y** Condición 2 |
| :----------: | :----------: | :-----------------------------------: |
|      F      |      F      |              **F**              |
|      F      |      V      |              **F**              |
|      V      |      F      |              **F**              |
|      V      |      V      |              **V**              |

**Ejemplo del libro:** "Tráigame una gaseosa **Y** un pan de $1000". Solo se cumple la orden si se traen ambas cosas.

#### 🔹 Operador O (OR)

La expresión es **Verdadera** si **al menos una** de las condiciones es Verdadera.

| Condición 1 | Condición 2 | Condición 1 **O** Condición 2 |
| :----------: | :----------: | :-----------------------------------: |
|      F      |      F      |              **F**              |
|      F      |      V      |              **V**              |
|      V      |      F      |              **V**              |
|      V      |      V      |              **V**              |

**Ejemplo del libro:** "Tráigame una gaseosa **O** una bolsa de leche". Se cumple la orden si se trae al menos una de las dos cosas.

#### 🔹 Operador NO (NOT)

Invierte el valor de verdad de una condición.

| Condición | **NO** Condición |
| :--------: | :---------------------: |
|     F     |       **V**       |
|     V     |       **F**       |

**Ejemplo:** `NO (a > 5)` es Verdadero cuando `a` NO es mayor que 5 (es decir, cuando `a <= 5`).

### 1.4. Combinación de operadores

Las tablas de verdad se pueden extender para expresiones con más de dos condiciones. Por ejemplo, para `(A Y B) O C`, se evalúa primero `A Y B` y luego se combina con `C` usando `O`.

| A | B | C | A Y B | (A Y B) O C |
| :-: | :-: | :-: | :---: | :---------: |
| F | F | F |   F   | **F** |
| F | F | V |   F   | **V** |
| F | V | F |   F   | **F** |
| F | V | V |   F   | **V** |
| V | F | F |   F   | **F** |
| V | F | V |   F   | **V** |
| V | V | F |   V   | **V** |
| V | V | V |   V   | **V** |

---

## 🔍 Parte 2: Ejemplos Resueltos

### 📌 Ejemplo 1: Evaluación de una condición con Y

**Enunciado:** Un usuario puede ingresar a un evento si tiene entrada **Y** es mayor de edad. Dado `tiene_entrada = Verdadero` y `es_mayor = Falso`, ¿puede ingresar?

**Solución:**

- `tiene_entrada = V`
- `es_mayor = F`
- `V Y F = F`

**Conclusión:** No puede ingresar, porque aunque tiene entrada, no es mayor de edad. La condición `Y` exige que ambas sean Verdaderas.

---

### 📌 Ejemplo 2: Evaluación de una condición con O

**Enunciado:** Un estudiante aprueba si saca más de 7 en el examen **O** si entrega todos los trabajos. Dado `nota = 6` (Falso, porque no es > 7) y `trabajos_entregados = Verdadero`, ¿aprueba?

**Solución:**

- `nota > 7 = F`
- `trabajos_entregados = V`
- `F O V = V`

**Conclusión:** Sí aprueba, porque aunque la nota no es suficiente, entregó todos los trabajos. La condición `O` solo necesita que una sea Verdadera.

---

### 📌 Ejemplo 3: Evaluación con NO

**Enunciado:** Un sistema muestra un mensaje si el usuario **NO** está registrado. Dado `registrado = Falso`, ¿se muestra el mensaje?

**Solución:**

- `registrado = F`
- `NO (registrado) = NO (F) = V`

**Conclusión:** Sí se muestra el mensaje, porque el usuario no está registrado.

---

### 📌 Ejemplo 4: Condición compuesta en un algoritmo

**Pseudocódigo:**

```text
Algoritmo Evaluar_Acceso
Variables
    Lógico: tiene_entrada, es_mayor, tiene_permiso
Inicio
    Escriba "¿Tiene entrada? (Verdadero/Falso):"
    Lea tiene_entrada
    Escriba "¿Es mayor de edad? (Verdadero/Falso):"
    Lea es_mayor
    Escriba "¿Tiene permiso de sus padres? (Verdadero/Falso):"
    Lea tiene_permiso
  
    Si (tiene_entrada Y es_mayor) O tiene_permiso Entonces
        Escriba "Puede ingresar al evento."
    Sino
        Escriba "No puede ingresar al evento."
    Fin_Si
Fin
```

**Tabla de verdad para la condición `(tiene_entrada Y es_mayor) O tiene_permiso`:**

| tiene_entrada | es_mayor | tiene_permiso | (tiene_entrada Y es_mayor) | Resultado final |
| :-----------: | :------: | :-----------: | :------------------------: | :-------------: |
|       F       |    F    |       F       |             F             |   **F**   |
|       F       |    F    |       V       |             F             |   **V**   |
|       F       |    V    |       F       |             F             |   **F**   |
|       F       |    V    |       V       |             F             |   **V**   |
|       V       |    F    |       F       |             F             |   **F**   |
|       V       |    F    |       V       |             F             |   **V**   |
|       V       |    V    |       F       |             V             |   **V**   |
|       V       |    V    |       V       |             V             |   **V**   |

**Conclusión:** El usuario puede ingresar si tiene entrada y es mayor de edad, o si tiene permiso de sus padres (aunque no tenga entrada o no sea mayor).

---

### 📌 Ejemplo 5: Aplicación en un algoritmo de calificaciones

**Enunciado:** Un estudiante aprueba si su nota es mayor o igual a 7 **Y** asistió al 80% de las clases, **O** si su nota es mayor o igual a 9 (sin importar la asistencia).

**Pseudocódigo:**

```text
Algoritmo Aprobar_Estudiante
Variables
    Real: nota
    Real: asistencia
Inicio
    Escriba "Digite la nota del estudiante:"
    Lea nota
    Escriba "Digite el porcentaje de asistencia (0 a 100):"
    Lea asistencia
  
    Si (nota >= 7 Y asistencia >= 80) O (nota >= 9) Entonces
        Escriba "El estudiante APROBÓ."
    Sino
        Escriba "El estudiante REPROBÓ."
    Fin_Si
Fin
```

**Tabla de verdad (simplificada):**

| nota >= 7 | asistencia >= 80 | nota >= 9 | (nota>=7 Y asist>=80) | Resultado final |
| :-------: | :--------------: | :-------: | :-------------------: | :-------------: |
|     F     |        F        |     F     |           F           |   **F**   |
|     F     |        F        |     V     |           F           |   **V**   |
|     F     |        V        |     F     |           F           |   **F**   |
|     F     |        V        |     V     |           F           |   **V**   |
|     V     |        F        |     F     |           F           |   **F**   |
|     V     |        F        |     V     |           F           |   **V**   |
|     V     |        V        |     F     |           V           |   **V**   |
|     V     |        V        |     V     |           V           |   **V**   |

---

## ✏️ Parte 3: Ejercicios Propuestos

**Instrucción:** Para cada ejercicio, construye la tabla de verdad correspondiente y determina el resultado final. Luego, escribe el pseudocódigo del algoritmo que evalúa la condición.

### 🟢 Nivel Básico (Operadores simples)

**Ejercicio 1: Operador Y**

- Condición: `(edad >= 18) Y (tiene_licencia = Verdadero)`
- Completa la tabla de verdad y determina en qué casos una persona puede conducir.

**Ejercicio 2: Operador O**

- Condición: `(dia = "sábado") O (dia = "domingo")`
- Completa la tabla de verdad y determina en qué casos es fin de semana.

**Ejercicio 3: Operador NO**

- Condición: `NO (esta_lloviendo)`
- Completa la tabla de verdad y determina en qué casos se puede salir sin paraguas.

**Ejercicio 4: Combinación de Y con NO**

- Condición: `(tengo_dinero) Y NO (esta_cerrado)`
- Completa la tabla de verdad y determina en qué casos puedo comprar en la tienda.

**Ejercicio 5: Combinación de O con NO**

- Condición: `NO (tengo_tarea) O (es_fin_de_semana)`
- Completa la tabla de verdad y determina en qué casos puedo salir a jugar.

---

### 🟡 Nivel Intermedio (Condiciones compuestas)

**Ejercicio 6: Acceso a un sistema**

- Un usuario puede acceder si su contraseña es correcta **Y** su cuenta no está bloqueada.
- Variables: `password_correcta`, `cuenta_bloqueada`.
- Condición: `password_correcta Y NO (cuenta_bloqueada)`.
- Construye la tabla de verdad y escribe el pseudocódigo.

**Ejercicio 7: Descuento en una tienda**

- Un cliente recibe descuento si su compra es mayor a $100 **Y** es cliente frecuente, **O** si su compra es mayor a $200.
- Variables: `compra_mayor_100`, `cliente_frecuente`, `compra_mayor_200`.
- Condición: `(compra_mayor_100 Y cliente_frecuente) O compra_mayor_200`.
- Construye la tabla de verdad y escribe el pseudocódigo.

**Ejercicio 8: Aprobación de un crédito**

- Un crédito se aprueba si el solicitante tiene ingresos mayores a $1000 **Y** no tiene deudas, **O** si tiene un fiador.
- Variables: `ingresos_mayores_1000`, `sin_deudas`, `tiene_fiador`.
- Condición: `(ingresos_mayores_1000 Y sin_deudas) O tiene_fiador`.
- Construye la tabla de verdad y escribe el pseudocódigo.

**Ejercicio 9: Validación de un triángulo**

- Tres lados forman un triángulo si la suma de dos de ellos es mayor que el tercero. Para los lados `a`, `b`, `c`, la condición es: `(a + b > c) Y (a + c > b) Y (b + c > a)`.
- Construye la tabla de verdad (puedes simplificarla) y escribe el pseudocódigo.

**Ejercicio 10: Clasificación de un número**

- Un número es "especial" si es positivo **Y** es par, **O** si es negativo **Y** es impar.
- Variables: `es_positivo`, `es_par`, `es_negativo`, `es_impar`.
- Condición: `(es_positivo Y es_par) O (es_negativo Y es_impar)`.
- Construye la tabla de verdad y escribe el pseudocódigo.

---

### 🔴 Nivel Avanzado (Aplicación en algoritmos)

**Ejercicio 11: Sistema de login con múltiples condiciones**

- Un usuario puede iniciar sesión si:
  - Su nombre de usuario es correcto **Y** su contraseña es correcta, **Y**
  - Su cuenta no está bloqueada, **Y**
  - Ha verificado su correo electrónico **O** ha verificado su teléfono.
- Variables: `usuario_correcto`, `password_correcta`, `cuenta_bloqueada`, `correo_verificado`, `telefono_verificado`.
- Condición: `usuario_correcto Y password_correcta Y NO (cuenta_bloqueada) Y (correo_verificado O telefono_verificado)`.
- Construye la tabla de verdad (puedes agrupar variables) y escribe el pseudocódigo.

**Ejercicio 12: Elegibilidad para una beca**

- Un estudiante es elegible para una beca si:
  - Tiene un promedio mayor o igual a 8.5 **Y** no tiene materias reprobadas, **O**
  - Tiene un promedio mayor o igual a 9.0 **Y** tiene al menos 2 publicaciones.
- Variables: `promedio_ge_8_5`, `sin_reprobadas`, `promedio_ge_9_0`, `tiene_publicaciones`.
- Condición: `(promedio_ge_8_5 Y sin_reprobadas) O (promedio_ge_9_0 Y tiene_publicaciones)`.
- Construye la tabla de verdad y escribe el pseudocódigo.

**Ejercicio 13: Control de acceso a una sala VIP**

- Una persona puede entrar a la sala VIP si:
  - Tiene invitación **Y** es mayor de edad, **O**
  - Es socio del club **Y** NO está acompañado de menores.
- Variables: `tiene_invitacion`, `es_mayor`, `es_socio`, `acompanado_menores`.
- Condición: `(tiene_invitacion Y es_mayor) O (es_socio Y NO (acompanado_menores))`.
- Construye la tabla de verdad y escribe el pseudocódigo.

**Ejercicio 14: Validación de una contraseña segura**

- Una contraseña es segura si:
  - Tiene al menos 8 caracteres **Y** contiene al menos una mayúscula, **Y**
  - Contiene al menos un número, **Y**
  - Contiene al menos un carácter especial.
- Variables: `longitud_ok`, `tiene_mayuscula`, `tiene_numero`, `tiene_especial`.
- Condición: `longitud_ok Y tiene_mayuscula Y tiene_numero Y tiene_especial`.
- Construye la tabla de verdad (puedes simplificarla) y escribe el pseudocódigo.

**Ejercicio 15: Sistema de alerta de temperatura**

- Se activa una alarma si:
  - La temperatura es mayor a 40°C **Y** la humedad es mayor al 80%, **O**
  - La temperatura es menor a 0°C **Y** hay viento fuerte.
- Variables: `temp_mayor_40`, `humedad_mayor_80`, `temp_menor_0`, `viento_fuerte`.
- Condición: `(temp_mayor_40 Y humedad_mayor_80) O (temp_menor_0 Y viento_fuerte)`.
- Construye la tabla de verdad y escribe el pseudocódigo.

---

## 📦 Entregables

El estudiante debe entregar un documento (Word, PDF o Markdown) con:

1. **Portada** (nombre, fecha, título del taller).
2. **Parte 1:** Un resumen de media página sobre qué es una tabla de verdad y para qué sirve en lógica de programación (basado en el libro y en tu investigación).
3. **Parte 2:** Los **15 ejercicios propuestos** resueltos, cada uno con:
   - La tabla de verdad completa.
   - El pseudocódigo del algoritmo que evalúa la condición.
   - Una breve conclusión: ¿en qué casos la condición es Verdadera?
4. **Reflexión final:** Un párrafo sobre qué aprendiste al construir tablas de verdad y por qué crees que son importantes para escribir condiciones en algoritmos.

---

## 📊 Rúbrica de Evaluación (Sugerida)

| Criterio                                    | Excelente (5)                                                                         | Bueno (4)                                               | Regular (3)                                             | Insuficiente (2)                              |
| :------------------------------------------ | :------------------------------------------------------------------------------------ | :------------------------------------------------------ | :------------------------------------------------------ | :-------------------------------------------- |
| **Comprensión de tablas de verdad**  | El resumen demuestra dominio del tema, cita al autor y explica los tres operadores.   | El resumen es correcto pero superficial.                | El resumen es confuso o incompleto.                     | No presenta resumen.                          |
| **Construcción de tablas de verdad** | Las 15 tablas están completas y correctas.                                           | La mayoría de las tablas están completas y correctas. | Algunas tablas están incompletas o tienen errores.     | No presenta tablas o son incorrectas.         |
| **Aplicación en pseudocódigo**      | Los 15 pseudocódigos usan correctamente los operadores lógicos.                     | La mayoría de los pseudocódigos son correctos.        | Algunos pseudocódigos son correctos, pero con errores. | No presenta pseudocódigos o son incorrectos. |
| **Conclusiones**                      | En cada ejercicio se concluye correctamente en qué casos la condición es Verdadera. | En la mayoría se concluye correctamente.               | En algunos se concluye correctamente.                   | No se concluye o se concluye mal.             |
| **Presentación y orden**             | Documento impecable, bien redactado, tablas claras.                                   | Documento ordenado con pequeños errores.               | Documento desordenado pero legible.                     | Documento desordenado e ilegible.             |

---

## 💡 Consejos del Autor (para tener en cuenta)

> *"Cuando utilizamos un operador AND, solamente genera Verdadero si ambas condiciones se cumplen... y en cualquier otro caso genera Falso."*

> *"Cuando el operador OR une dos condiciones, toda la expresión es verdadera si, al menos, una de las dos es verdadera."*

> *"El tercer operador booleano es el operador NOT. Este operador actúa sobre una sola expresión y lo que hace es que invierte el sentido de la condición."*

> *"Con estos tres operadores booleanos podemos construir una gran cantidad de decisiones y permitir que el computador las ejecute correctamente."*

---

**Nota:** Si tienes dudas sobre cómo construir tablas de verdad, revisa el Capítulo 4.4.3 del libro de Omar Iván Trejos Buriticá o consulta los ejemplos resueltos de este taller.

```

---

### 📌 Instrucciones para usar este archivo `.md`

1. Copia todo el contenido que está entre las tres comillas invertidas (````markdown` ... ````).
2. Abre un editor de texto plano (Bloc de notas, VS Code, Obsidian, Typora, etc.).
3. Pega el contenido.
4. Guarda el archivo con el nombre `Taller_Tablas_de_Verdad.md`.
5. ¡Listo! Ya tienes el taller en formato Markdown, con ejemplos resueltos, ejercicios propuestos, entregables y rúbrica de evaluación.

Si necesitas que ajuste algo (por ejemplo, agregar más ejemplos, cambiar los ejercicios propuestos o incluir diagramas de flujo), házmelo saber.
```
