# 📝 Taller 5: Pruebas de Escritorio en Lógica de Programación

**Asignatura:** Lógica de Programación
**Tema:** Metodología de la Prueba de Escritorio
**Basado en:** *Lógica de programación* de Omar Iván Trejos Buriticá (Capítulo 2.3 y 6.1.3)
**Modalidad:** Individual
**Fecha de entrega:** [Insertar fecha]

---

## 🎯 Objetivo del Taller

Comprender la importancia de la **prueba de escritorio** como herramienta fundamental para verificar la lógica de un algoritmo antes de codificarlo. El estudiante aprenderá a simular la ejecución de un algoritmo paso a paso, llevando el control de las variables en memoria y de los resultados en pantalla, tal como lo haría un computador.

---

## 📖 Parte 1: ¿Qué es una Prueba de Escritorio?

### 1.1. Definición

Según el autor del libro, la prueba de escritorio es:

> *"La simulación de la puesta en marcha de un algoritmo. Con la prueba de escritorio podemos determinar si el algoritmo que hemos diseñado logra el objetivo propuesto."*

En términos sencillos, es **actuar como si fuéramos el computador**: ejecutar las instrucciones una a una, sin saltarse ninguna, sin suponer nada, y anotar en papel qué va pasando en la memoria (variables) y en la pantalla (salidas).

### 1.2. ¿Por qué es importante?

El autor es enfático al afirmar que:

> *"Un algoritmo al que no se le ha hecho una rigurosa prueba de escritorio no es más que un conjunto de órdenes posiblemente incoherente."*

Las pruebas de escritorio permiten:

- **Verificar** si el algoritmo cumple con el objetivo.
- **Detectar errores lógicos** antes de codificar.
- **Ahorrar tiempo** y dinero, pues corregir un error en papel es mucho más fácil que en un lenguaje de programación.
- **Documentar** el comportamiento del algoritmo.

### 1.3. Elementos necesarios

Para realizar una prueba de escritorio necesitas:

1. **El algoritmo** escrito en pseudocódigo (con declaración de variables).
2. **Una tabla de memoria:** donde anotarás el valor de cada variable después de cada instrucción.
3. **Una "pantalla":** un espacio donde anotarás los mensajes que el algoritmo "imprime".
4. **Valores de entrada:** datos concretos para probar (ej: si el algoritmo lee un número, elige un valor como 5, 10, -3, etc.).
5. **Mucha disciplina:** no puedes suponer resultados; debes ejecutar cada línea como lo haría el computador.

---

## 📝 Parte 2: Paso a Paso para Realizar una Prueba de Escritorio

**Paso 1:** Lee el algoritmo completo y asegúrate de entenderlo.

**Paso 2:** Dibuja una tabla con las variables declaradas en memoria. Si el algoritmo tiene una pantalla, dibuja un rectángulo para anotar las salidas.

**Paso 3:** Asigna valores iniciales a las variables (si el algoritmo los pide) o comienza desde la primera instrucción.

**Paso 4:** Ejecuta cada instrucción **en orden**. Si hay una decisión (`Si...`), evalúa la condición con los valores actuales y sigue el camino correspondiente.

**Paso 5:** Si hay un ciclo (`Mientras...`), repite el cuerpo del ciclo hasta que la condición sea falsa.

**Paso 6:** Al terminar, revisa lo que quedó en pantalla. ¿Coincide con el objetivo del algoritmo? Si sí, el algoritmo está bien. Si no, hay un error que debes corregir.

---

## 🔍 Parte 3: Ejemplos Resueltos

### 📌 Ejemplo 1: Algoritmo que suma dos números

**Pseudocódigo:**

```text
Algoritmo Suma_Dos_Numeros
Variables
    Entero: a, b, resultado
Inicio
    Escriba "Digite el primer número:"
    Lea a
    Escriba "Digite el segundo número:"
    Lea b
    resultado = a + b
    Escriba "El resultado es: ", resultado
Fin
```

**Paso a paso de la prueba de escritorio:**

**Entrada de datos (supongamos):** `a = 5`, `b = 3`

| Paso | Instrucción                               | Memoria (a) | Memoria (b) | Memoria (resultado) | Pantalla                                                                    |
| :--- | :----------------------------------------- | :---------- | :---------- | :------------------ | :-------------------------------------------------------------------------- |
| 1    | Inicio                                     | -           | -           | -                   | (vacía)                                                                    |
| 2    | `Escriba "Digite el primer número:"`    | -           | -           | -                   | "Digite el primer número:"                                                 |
| 3    | `Lea a`                                  | **5** | -           | -                   | "Digite el primer número:"                                                 |
| 4    | `Escriba "Digite el segundo número:"`   | 5           | -           | -                   | "Digite el primer número:""Digite el segundo número:"                     |
| 5    | `Lea b`                                  | 5           | **3** | -                   | "Digite el primer número:""Digite el segundo número:"                     |
| 6    | `resultado = a + b`                      | 5           | 3           | **8**         | "Digite el primer número:""Digite el segundo número:"                     |
| 7    | `Escriba "El resultado es: ", resultado` | 5           | 3           | 8                   | "Digite el primer número:""Digite el segundo número:""El resultado es: 8" |
| 8    | Fin                                        | 5           | 3           | 8                   | "El resultado es: 8"                                                        |

**Verificación:** El resultado es 8, que es la suma de 5 + 3. ✅ El algoritmo cumple el objetivo.

---

### 📌 Ejemplo 2: Algoritmo que determina si un número es par (del libro, Cap. 6.4)

**Pseudocódigo:**

```text
Algoritmo Numero_Par
Variables
    Entero: num
Inicio
    Lea num
    Si num < 0 Entonces
        Escriba "El número debe ser positivo"
    Sino
        Si num / 2 * 2 = num Entonces
            Escriba "El número leído es par"
        Sino
            Escriba "El número leído no es par"
        Fin_Si
    Fin_Si
Fin
```

**Paso a paso (supongamos `num = 18`):**

| Paso | Instrucción                                       | Memoria (num) | Pantalla                   |
| :--- | :------------------------------------------------- | :------------ | :------------------------- |
| 1    | Inicio                                             | -             | (vacía)                   |
| 2    | `Lea num`                                        | **18**  | (vacía)                   |
| 3    | `Si num < 0` → ¿18 < 0?                        | 18            | (vacía)                   |
| 4    | **Falso**, entonces ejecuta el Sino          | 18            | (vacía)                   |
| 5    | `Si num / 2 * 2 = num` → ¿18/2*2 = 18?         | 18            | (vacía)                   |
| 6    | 18/2 = 9, 9*2 = 18. ¿18 = 18? **Verdadero** | 18            | (vacía)                   |
| 7    | `Escriba "El número leído es par"`             | 18            | "El número leído es par" |
| 8    | Fin                                                | 18            | "El número leído es par" |

**Verificación:** 18 es par. ✅ El algoritmo cumple el objetivo.

**Prueba con otro valor (supongamos `num = 25`):**

| Paso | Instrucción                                                          | Memoria (num) | Pantalla                      |
| :--- | :-------------------------------------------------------------------- | :------------ | :---------------------------- |
| 1    | Inicio                                                                | -             | (vacía)                      |
| 2    | `Lea num`                                                           | **25**  | (vacía)                      |
| 3    | `Si num < 0` → ¿25 < 0?                                           | 25            | (vacía)                      |
| 4    | **Falso**                                                       | 25            | (vacía)                      |
| 5    | `Si num / 2 * 2 = num` → ¿25/2*2 = 25?                            | 25            | (vacía)                      |
| 6    | 25/2 = 12 (aritmética entera), 12*2 = 24. ¿24 = 25? **Falso** | 25            | (vacía)                      |
| 7    | `Escriba "El número leído no es par"`                             | 25            | "El número leído no es par" |
| 8    | Fin                                                                   | 25            | "El número leído no es par" |

**Verificación:** 25 no es par. ✅ El algoritmo cumple el objetivo.

---

### 📌 Ejemplo 3: Algoritmo con ciclo (contar dígitos de un número)

**Pseudocódigo:**

```text
Algoritmo Cuenta_Digitos
Variables
    Entero: num, cd
Inicio
    Escriba "Digite un número entero:"
    Lea num
    cd = 0
    Mientras num <> 0 Hacer
        num = num / 10
        cd = cd + 1
    Fin_Mientras
    Escriba "El número tiene ", cd, " dígitos"
Fin
```

**Paso a paso (supongamos `num = 523`):**

| Paso | Instrucción                                                     | Memoria (num) | Memoria (cd) | Pantalla                                                 |
| :--- | :--------------------------------------------------------------- | :------------ | :----------- | :------------------------------------------------------- |
| 1    | Inicio                                                           | -             | -            | (vacía)                                                 |
| 2    | `Escriba "Digite un número entero:"`                          | -             | -            | "Digite un número entero:"                              |
| 3    | `Lea num`                                                      | **523** | -            | "Digite un número entero:"                              |
| 4    | `cd = 0`                                                       | 523           | **0**  | "Digite un número entero:"                              |
| 5    | `Mientras num <> 0` → ¿523 ≠ 0? **Verdadero**         | 523           | 0            | "Digite un número entero:"                              |
| 6    | `num = num / 10` → 523/10 = 52 (entero)                       | **52**  | 0            | "Digite un número entero:"                              |
| 7    | `cd = cd + 1` → 0 + 1 = 1                                     | 52            | **1**  | "Digite un número entero:"                              |
| 8    | Volver al Mientras → ¿52 ≠ 0? **Verdadero**             | 52            | 1            | "Digite un número entero:"                              |
| 9    | `num = num / 10` → 52/10 = 5                                  | **5**   | 1            | "Digite un número entero:"                              |
| 10   | `cd = cd + 1` → 1 + 1 = 2                                     | 5             | **2**  | "Digite un número entero:"                              |
| 11   | Volver al Mientras → ¿5 ≠ 0? **Verdadero**              | 5             | 2            | "Digite un número entero:"                              |
| 12   | `num = num / 10` → 5/10 = 0                                   | **0**   | 2            | "Digite un número entero:"                              |
| 13   | `cd = cd + 1` → 2 + 1 = 3                                     | 0             | **3**  | "Digite un número entero:"                              |
| 14   | Volver al Mientras → ¿0 ≠ 0? **Falso** (sale del ciclo) | 0             | 3            | "Digite un número entero:"                              |
| 15   | `Escriba "El número tiene ", cd, " dígitos"`                 | 0             | 3            | "Digite un número entero:""El número tiene 3 dígitos" |
| 16   | Fin                                                              | 0             | 3            | "El número tiene 3 dígitos"                            |

**Verificación:** 523 tiene 3 dígitos. ✅ El algoritmo cumple el objetivo.

---

## ✏️ Parte 4: Ejercicios Propuestos

**Instrucción:** Realiza la prueba de escritorio de los siguientes algoritmos. Para cada uno, dibuja la tabla de memoria y pantalla, y verifica si cumple con el objetivo.

### Ejercicio 1: Área de un círculo

**Pseudocódigo:**

```text
Algoritmo Area_Circulo
Variables
    Real: radio, area
    Real: pi = 3.1416
Inicio
    Escriba "Digite el radio del círculo:"
    Lea radio
    area = pi * radio * radio
    Escriba "El área es: ", area
Fin
```

**Prueba de escritorio:** Supón que `radio = 5`. Llena la tabla y verifica si el área es correcta (fórmula: π × r²).

| Paso | Instrucción | Memoria (radio) | Memoria (area) | Pantalla |
| :--- | :----------- | :-------------- | :------------- | :------- |
| 1    |              |                 |                |          |
| 2    |              |                 |                |          |
| ...  |              |                 |                |          |

**Pregunta:** ¿El resultado coincide con el cálculo manual? (π × 5² = 3.1416 × 25 = 78.54).

---

### Ejercicio 2: Determinar el mayor de dos números

**Pseudocódigo:**

```text
Algoritmo Mayor_Dos_Numeros
Variables
    Entero: a, b
Inicio
    Escriba "Digite el primer número:"
    Lea a
    Escriba "Digite el segundo número:"
    Lea b
    Si a > b Entonces
        Escriba "El mayor es: ", a
    Sino
        Escriba "El mayor es: ", b
    Fin_Si
Fin
```

**Prueba de escritorio:** Realiza dos pruebas:

- Caso 1: `a = 10`, `b = 7`.
- Caso 2: `a = 3`, `b = 12`.

**Pregunta:** ¿En ambos casos el algoritmo muestra el número correcto? ¿Qué pasa si `a = b`?

---

### Ejercicio 3: Suma de los primeros N números

**Pseudocódigo:**

```text
Algoritmo Suma_N_Numeros
Variables
    Entero: n, i, suma
Inicio
    Escriba "Digite un número entero positivo:"
    Lea n
    suma = 0
    Para i = 1 Hasta n Hacer
        suma = suma + i
    Fin_Para
    Escriba "La suma de 1 a ", n, " es: ", suma
Fin
```

**Prueba de escritorio:** Supón `n = 5`. La suma debe ser 1 + 2 + 3 + 4 + 5 = 15.

**Pregunta:** ¿El resultado es 15? ¿Qué pasa si `n = 1`?

---

### Ejercicio 4: Contar números pares e impares en un vector

**Pseudocódigo:**

```text
Algoritmo Contar_Pares_Impares
Variables
    Entero: v[5], i, pares, impares
Inicio
    Para i = 1 Hasta 5 Hacer
        Escriba "Digite el número ", i, ":"
        Lea v[i]
    Fin_Para
    pares = 0
    impares = 0
    Para i = 1 Hasta 5 Hacer
        Si v[i] mod 2 = 0 Entonces
            pares = pares + 1
        Sino
            impares = impares + 1
        Fin_Si
    Fin_Para
    Escriba "Cantidad de pares: ", pares
    Escriba "Cantidad de impares: ", impares
Fin
```

**Prueba de escritorio:** Supón que el usuario ingresa los valores: `v = [8, 3, 10, 7, 2]`.

**Pregunta:** ¿Cuántos pares e impares hay? (Pista: 8, 10, 2 son pares; 3, 7 son impares).

---

### Ejercicio 5: Validar contraseña con 3 intentos

**Pseudocódigo:**

```text
Algoritmo Login
Variables
    Carácter: password[10]
    Entero: intentos
    Lógico: acceso
Inicio
    intentos = 0
    acceso = Falso
    Mientras intentos < 3 Y NO acceso Hacer
        Escriba "Digite la contraseña:"
        Lea password
        Si password = "12345" Entonces
            acceso = Verdadero
        Sino
            intentos = intentos + 1
            Escriba "Contraseña incorrecta. Intento ", intentos, " de 3"
        Fin_Si
    Fin_Mientras
    Si acceso Entonces
        Escriba "Bienvenido"
    Sino
        Escriba "Cuenta bloqueada"
    Fin_Si
Fin
```

**Prueba de escritorio:** Realiza dos pruebas:

- Caso 1: El usuario ingresa "12345" en el primer intento.
- Caso 2: El usuario ingresa "111", "222", "333" (falla 3 veces).

**Pregunta:** ¿Qué mensaje aparece en cada caso?

---

## 📦 Entregables

El estudiante debe entregar un documento (Word, PDF o Markdown) con:

1. **Portada** (nombre, fecha, título del taller).
2. **Parte 1:** Un resumen de media página sobre qué es una prueba de escritorio y por qué es importante (basado en el libro).
3. **Parte 2:** Los **5 ejercicios propuestos** resueltos, cada uno con:
   - La tabla de memoria y pantalla completa (paso a paso).
   - Una conclusión: ¿el algoritmo cumple el objetivo? ¿Sí o no? ¿Por qué?
4. **Reflexión final:** Un párrafo sobre qué aprendiste al realizar las pruebas de escritorio y por qué crees que son importantes antes de programar.

---

## 📊 Rúbrica de Evaluación (Sugerida)

| Criterio                             | Excelente (5)                                                                             | Bueno (4)                                                          | Regular (3)                                         | Insuficiente (2)                      |
| :----------------------------------- | :---------------------------------------------------------------------------------------- | :----------------------------------------------------------------- | :-------------------------------------------------- | :------------------------------------ |
| **Comprensión del concepto**  | El resumen demuestra dominio del tema, cita al autor y explica la importancia.            | El resumen es correcto pero superficial.                           | El resumen es confuso o incompleto.                 | No presenta resumen.                  |
| **Ejecución paso a paso**     | Las tablas están completas, los valores son correctos y se sigue el orden del algoritmo. | La mayoría de las tablas están completas, con pequeños errores. | Algunas tablas están incompletas o tienen errores. | No presenta tablas o son incorrectas. |
| **Verificación del objetivo** | En cada ejercicio se concluye correctamente si el algoritmo cumple o no el objetivo.      | En la mayoría se concluye correctamente.                          | En algunos se concluye correctamente.               | No se concluye o se concluye mal.     |
| **Presentación y orden**      | Documento impecable, bien redactado, tablas claras.                                       | Documento ordenado con pequeños errores.                          | Documento desordenado pero legible.                 | Documento desordenado e ilegible.     |
| **Reflexión final**           | Reflexión profunda y personal sobre la utilidad de la prueba de escritorio.              | Reflexión correcta pero superficial.                              | Reflexión muy breve.                               | No presenta reflexión.               |

---

## 💡 Consejos del Autor (para tener en cuenta)

> *"No se olvide que lo único que necesita para realizar una buena prueba de escritorio es que usted, mientras la esté realizando, no 'razone', o sea, que actúe como si usted fuera un computador (que no piensa) y de manera autómata realice y obedezca una a una las órdenes establecidas en el algoritmo."*

> *"Si al realizar la prueba de escritorio ve que los resultados finales no coinciden con el objetivo inicial, entonces su algoritmo estará mal y deberá corregirlo. La prueba de escritorio es la que le dice a usted en dónde está el error."*

---

**Nota:** Si tienes dudas sobre cómo hacer una prueba de escritorio, revisa los ejemplos resueltos de este taller o consulta el Capítulo 2.3 y 6.1.3 del libro de Omar Iván Trejos Buriticá.

```

---

### 📌 Instrucciones para usar este archivo `.md`

1. Copia todo el contenido que está entre las tres comillas invertidas (````markdown` ... ````).
2. Abre un editor de texto plano (Bloc de notas, VS Code, Obsidian, Typora, etc.).
3. Pega el contenido.
4. Guarda el archivo con el nombre `Taller_Pruebas_Escritorio.md`.
5. ¡Listo! Ya tienes el taller en formato Markdown, con ejemplos resueltos, ejercicios propuestos, entregables y rúbrica de evaluación.

Si necesitas que ajuste algo (por ejemplo, agregar más ejemplos, cambiar los ejercicios propuestos o incluir diagramas de flujo), házmelo saber.
```
