
# 📝 Taller: Manejo de Arrays en Lógica de Programación

**Asignatura:** Lógica de Programación
**Tema:** Arreglos (Vectores y Matrices)
**Basado en:** *Lógica de programación* de Omar Iván Trejos Buriticá (Capítulos 9 y 10)
**Modalidad:** Individual
**Fecha de entrega:** [Insertar fecha]

---

## 🎯 Objetivo del Taller

Comprender el concepto de arreglo (array) como una estructura de datos que permite almacenar múltiples valores del mismo tipo bajo un mismo nombre. El estudiante aprenderá a declarar, inicializar, recorrer y manipular **vectores** (arreglos unidimensionales) y **matrices** (arreglos bidimensionales), utilizando ciclos para automatizar las operaciones.

---

## 📖 Parte 1: Contextualización Teórica

### 1.1. ¿Qué es un arreglo?

Según el autor del libro, un arreglo es:

> *"Un conjunto de variables en donde cada una de ellas puede ser referenciada utilizando su posición relativa, es decir, su ubicación en relación con el primer elemento de dicho conjunto."*

En términos sencillos, un arreglo es como una **fila de casillas** (o una **tabla**, si es bidimensional) donde cada casilla puede almacenar un dato. Todas las casillas son del **mismo tipo** (homogéneas) y se accede a ellas mediante un **índice** (un número entero que indica la posición).

**Analogía del libro:** Es como una cola de personas en un banco. Si el cajero dice "venga la quinta persona", todos saben que se refiere a la persona que ocupa la posición 5, contando desde el inicio de la fila.

### 1.2. Tipos de arreglos

| Tipo             | Definición                                       | Ejemplo                               | ¿Cuántos índices necesita? |
| :--------------- | :------------------------------------------------ | :------------------------------------ | :---------------------------- |
| **Vector** | Arreglo unidimensional (una sola fila o columna). | `notas[5]` (5 notas)                | 1 índice                     |
| **Matriz** | Arreglo bidimensional (filas y columnas).         | `tabla[3][4]` (3 filas, 4 columnas) | 2 índices (fila, columna)    |

### 1.3. Características de un arreglo

| Característica      | Descripción                                                                                                    |
| :------------------- | :-------------------------------------------------------------------------------------------------------------- |
| **Tipo**       | Todos los datos del arreglo son del mismo tipo (entero, real, carácter, etc.).                                 |
| **Nombre**     | Identificador único (ej: `notas`, `edades`, `matriz`).                                                   |
| **Dimensión** | Cantidad de elementos que puede almacenar. Se define al declarar el arreglo.                                    |
| **Índice**    | Variable entera que indica la posición de un elemento. Generalmente empieza en 1 (o en 0, según el lenguaje). |
| **Tamaño**    | En vectores, es igual a la dimensión. En matrices, es filas × columnas.                                       |

### 1.4. Declaración de arreglos en pseudocódigo

**Vector:**

```text
Variables
    Entero: notas[5]          // Vector de 5 enteros
    Real: precios[10]         // Vector de 10 reales
    Carácter: nombres[20][50] // Vector de 20 cadenas de hasta 50 caracteres
```

**Matriz:**

```text
Variables
    Entero: tabla[3][4]       // Matriz de 3 filas y 4 columnas (12 enteros)
    Real: matriz[5][5]        // Matriz de 5x5 (25 reales)
```

### 1.5. Acceso a los elementos de un arreglo

- **Vector:** `nombre_arreglo[indice]`
  - Ejemplo: `notas[1]` (primer elemento), `notas[5]` (quinto elemento).
- **Matriz:** `nombre_arreglo[fila][columna]`
  - Ejemplo: `tabla[2][3]` (elemento en la fila 2, columna 3).

**Importante:** El índice debe ser un número entero. No se puede usar `notas[1.5]` (eso sería un error).

---

## 🔍 Parte 2: Ejemplos Resueltos

### 📌 Ejemplo 1: Declarar, llenar y mostrar un vector

**Pseudocódigo:**

```text
Algoritmo Ejemplo_Vector
Variables
    Entero: numeros[5], i
Inicio
    // Llenar el vector
    Para i = 1 Hasta 5 Hacer
        Escriba "Digite el número ", i, ":"
        Lea numeros[i]
    Fin_Para
  
    // Mostrar el vector
    Escriba "Los números ingresados son:"
    Para i = 1 Hasta 5 Hacer
        Escriba numeros[i]
    Fin_Para
Fin
```

**Explicación:**

- Se declara un vector `numeros` de 5 posiciones y una variable `i` como índice.
- El primer ciclo `Para` recorre las posiciones 1 a 5 y lee un número en cada una.
- El segundo ciclo `Para` recorre el vector y muestra cada elemento.

**Prueba de escritorio (supongamos que el usuario ingresa 10, 20, 30, 40, 50):**

| i | numeros[i] | Pantalla                       |
| :- | :--------- | :----------------------------- |
| 1 | 10         | "Digite el número 1:"         |
| 2 | 20         | "Digite el número 2:"         |
| 3 | 30         | "Digite el número 3:"         |
| 4 | 40         | "Digite el número 4:"         |
| 5 | 50         | "Digite el número 5:"         |
| - | -          | "Los números ingresados son:" |
| 1 | 10         | "10"                           |
| 2 | 20         | "20"                           |
| 3 | 30         | "30"                           |
| 4 | 40         | "40"                           |
| 5 | 50         | "50"                           |

---

### 📌 Ejemplo 2: Calcular el promedio de un vector

**Pseudocódigo:**

```text
Algoritmo Promedio_Vector
Variables
    Real: notas[5], suma, promedio
    Entero: i
Inicio
    suma = 0
  
    // Llenar el vector
    Para i = 1 Hasta 5 Hacer
        Escriba "Digite la nota ", i, ":"
        Lea notas[i]
        suma = suma + notas[i]
    Fin_Para
  
    // Calcular promedio
    promedio = suma / 5
  
    // Mostrar resultados
    Escriba "La suma de las notas es: ", suma
    Escriba "El promedio es: ", promedio
Fin
```

**Explicación:**

- Se declara un vector `notas` de 5 reales, y variables `suma` y `promedio`.
- En el mismo ciclo en que se leen las notas, se van acumulando en `suma`.
- Al final, se divide `suma` entre 5 para obtener el promedio.

---

### 📌 Ejemplo 3: Buscar el mayor en un vector

**Pseudocódigo:**

```text
Algoritmo Mayor_Vector
Variables
    Entero: numeros[5], i, mayor
Inicio
    // Llenar el vector
    Para i = 1 Hasta 5 Hacer
        Escriba "Digite el número ", i, ":"
        Lea numeros[i]
    Fin_Para
  
    // Buscar el mayor
    mayor = numeros[1]  // Se asume que el primero es el mayor
    Para i = 2 Hasta 5 Hacer
        Si numeros[i] > mayor Entonces
            mayor = numeros[i]
        Fin_Si
    Fin_Para
  
    Escriba "El número mayor es: ", mayor
Fin
```

**Explicación:**

- Se inicializa `mayor` con el primer elemento del vector (`numeros[1]`).
- Luego se recorre el vector desde la posición 2 hasta la 5, comparando cada elemento con `mayor`. Si se encuentra uno más grande, se actualiza `mayor`.
- Al final, `mayor` contiene el número más grande del vector.

---

### 📌 Ejemplo 4: Declarar, llenar y mostrar una matriz

**Pseudocódigo:**

```text
Algoritmo Ejemplo_Matriz
Variables
    Entero: tabla[3][3], i, j
Inicio
    // Llenar la matriz
    Para i = 1 Hasta 3 Hacer
        Para j = 1 Hasta 3 Hacer
            Escriba "Digite el valor para [", i, "][", j, "]:"
            Lea tabla[i][j]
        Fin_Para
    Fin_Para
  
    // Mostrar la matriz
    Escriba "La matriz ingresada es:"
    Para i = 1 Hasta 3 Hacer
        Para j = 1 Hasta 3 Hacer
            Escriba tabla[i][j]
        Fin_Para
        Escriba ""  // Salto de línea para cada fila
    Fin_Para
Fin
```

**Explicación:**

- Se declara una matriz `tabla` de 3x3 y dos índices `i` (filas) y `j` (columnas).
- El ciclo externo recorre las filas (1 a 3) y el ciclo interno recorre las columnas (1 a 3).
- Al mostrar, se recorre de la misma forma, pero se agrega un salto de línea al final de cada fila para que se vea como una tabla.

---

### 📌 Ejemplo 5: Sumar los elementos de la diagonal de una matriz

**Pseudocódigo:**

```text
Algoritmo Suma_Diagonal
Variables
    Entero: matriz[3][3], i, j, suma_diagonal
Inicio
    // Llenar la matriz
    Para i = 1 Hasta 3 Hacer
        Para j = 1 Hasta 3 Hacer
            Escriba "Digite el valor para [", i, "][", j, "]:"
            Lea matriz[i][j]
        Fin_Para
    Fin_Para
  
    // Sumar la diagonal (donde i = j)
    suma_diagonal = 0
    Para i = 1 Hasta 3 Hacer
        suma_diagonal = suma_diagonal + matriz[i][i]
    Fin_Para
  
    Escriba "La suma de la diagonal es: ", suma_diagonal
Fin
```

**Explicación:**

- La diagonal de una matriz está formada por los elementos donde el índice de fila es igual al índice de columna (`i = j`).
- Por eso, solo se necesita un ciclo `Para i = 1 Hasta 3` y se accede a `matriz[i][i]`.

---

## ✏️ Parte 3: Ejercicios Propuestos

**Instrucción:** Para cada ejercicio, escribe el pseudocódigo completo (declaración de variables, inicio, fin) y realiza una prueba de escritorio con valores concretos.

### 🟢 Nivel Básico (Vectores)

**Ejercicio 1: Llenar y mostrar un vector**

- Leer 8 números enteros en un vector y mostrarlos en pantalla en el mismo orden en que fueron ingresados.

**Ejercicio 2: Suma de un vector**

- Leer 6 números reales en un vector y calcular la suma de todos sus elementos. Mostrar el resultado.

**Ejercicio 3: Contar números pares**

- Leer 10 números enteros en un vector y contar cuántos son pares y cuántos son impares. Mostrar ambos resultados.

**Ejercicio 4: Promedio de un vector**

- Leer 5 notas (reales) en un vector y calcular su promedio. Mostrar el promedio.

**Ejercicio 5: Mostrar en orden inverso**

- Leer 7 números enteros en un vector y mostrarlos en pantalla en orden inverso (del último al primero).

---

### 🟡 Nivel Intermedio (Vectores con lógica)

**Ejercicio 6: Buscar el menor**

- Leer 8 números enteros en un vector y determinar cuál es el menor y en qué posición se encuentra.

**Ejercicio 7: Contar un valor específico**

- Leer 10 números enteros en un vector, luego leer un número adicional y determinar cuántas veces aparece ese número en el vector.

**Ejercicio 8: Vector de factoriales**

- Leer 5 números enteros en un vector y calcular el factorial de cada uno, almacenándolos en otro vector. Mostrar ambos vectores.

**Ejercicio 9: Invertir un vector**

- Leer 6 números enteros en un vector y crear un nuevo vector con los elementos en orden inverso. Mostrar ambos vectores.

**Ejercicio 10: Suma de vectores**

- Leer dos vectores de 5 elementos cada uno y crear un tercer vector que contenga la suma de los elementos correspondientes. Mostrar el vector resultante.

---

### 🔴 Nivel Avanzado (Matrices)

**Ejercicio 11: Llenar y mostrar una matriz**

- Leer una matriz de 3x3 (9 números enteros) y mostrarla en pantalla en forma de tabla.

**Ejercicio 12: Suma de filas y columnas**

- Leer una matriz de 4x4 y calcular la suma de cada fila y la suma de cada columna. Mostrar los resultados.

**Ejercicio 13: Buscar un valor en una matriz**

- Leer una matriz de 3x3, luego leer un número adicional y determinar si ese número se encuentra en la matriz y en qué posición (fila, columna).

**Ejercicio 14: Transponer una matriz**

- Leer una matriz de 3x3 y crear su matriz transpuesta (intercambiar filas por columnas). Mostrar ambas matrices.

**Ejercicio 15: Contar números primos en una matriz**

- Leer una matriz de 4x4 y contar cuántos de sus elementos son números primos. Mostrar el total.

---

## 📦 Entregables

El estudiante debe entregar un documento (Word, PDF o Markdown) con:

1. **Portada** (nombre, fecha, título del taller).
2. **Parte 1:** Un resumen de media página sobre qué es un arreglo, sus características y la diferencia entre vector y matriz (basado en el libro y en tu investigación).
3. **Parte 2:** Los **15 ejercicios propuestos** resueltos, cada uno con:
   - El pseudocódigo completo (con declaración de variables, inicio y fin).
   - Una breve prueba de escritorio con valores concretos (opcional, pero suma puntos).
4. **Reflexión final:** Un párrafo sobre qué aprendiste al manejar arreglos y por qué crees que son importantes en la programación.

---

## 📊 Rúbrica de Evaluación (Sugerida)

| Criterio                            | Excelente (5)                                                                                       | Bueno (4)                                       | Regular (3)                                               | Insuficiente (2)                     |
| :---------------------------------- | :-------------------------------------------------------------------------------------------------- | :---------------------------------------------- | :-------------------------------------------------------- | :----------------------------------- |
| **Comprensión de arreglos**  | El resumen demuestra dominio del tema, cita al autor y explica la diferencia entre vector y matriz. | El resumen es correcto pero superficial.        | El resumen es confuso o incompleto.                       | No presenta resumen.                 |
| **Declaración de arreglos**  | En los 15 ejercicios se declaran correctamente los vectores y matrices, con sus dimensiones.        | En la mayoría se declaran correctamente.       | En algunos se declaran correctamente, pero con errores.   | No se declaran o se declaran mal.    |
| **Recorrido con ciclos**      | Los ciclos se usan correctamente para recorrer los arreglos (Para, Mientras).                       | La mayoría de los ciclos son correctos.        | Algunos ciclos son correctos, pero con errores.           | No se usan ciclos o son incorrectos. |
| **Lógica de los ejercicios** | Los 15 ejercicios resuelven el problema correctamente.                                              | La mayoría resuelve el problema correctamente. | Algunos resuelven el problema, pero con errores lógicos. | No resuelven el problema.            |
| **Presentación y orden**     | Documento impecable, bien redactado, tablas claras.                                                 | Documento ordenado con pequeños errores.       | Documento desordenado pero legible.                       | Documento desordenado e ilegible.    |

---

## 💡 Consejos del Autor (para tener en cuenta)

> *"Un vector es un arreglo en donde la ubicación exacta de cada uno de sus elementos necesita solamente la utilización de un subíndice."*

> *"Una matriz es un conjunto de datos organizados en forma de filas y columnas en donde para referenciar cada dato necesitaremos establecer claramente en qué fila y en qué columna se encuentra."*

> *"Siempre que vaya a desarrollar un algoritmo, primero debe clarificar el objetivo para que sepa hacia dónde va y hasta dónde debe llegar."*

> *"No sobredimensione los vectores, esto quiere decir que no utilice vectores con una dimensión exagerada para no correr el riesgo de quedarse corto de memoria."*

---

**Nota:** Si tienes dudas sobre cómo manejar arreglos, revisa los Capítulos 9 y 10 del libro de Omar Iván Trejos Buriticá o consulta los ejemplos resueltos de este taller.

```

---

### 📌 Instrucciones para usar este archivo `.md`

1. Copia todo el contenido que está entre las tres comillas invertidas (````markdown` ... ````).
2. Abre un editor de texto plano (Bloc de notas, VS Code, Obsidian, Typora, etc.).
3. Pega el contenido.
4. Guarda el archivo con el nombre `Taller_Manejo_Arrays.md`.
5. ¡Listo! Ya tienes el taller en formato Markdown, con ejemplos resueltos, ejercicios propuestos, entregables y rúbrica de evaluación.

Si necesitas que ajuste algo (por ejemplo, agregar más ejemplos, cambiar los ejercicios propuestos o incluir diagramas de flujo), házmelo saber.
```
