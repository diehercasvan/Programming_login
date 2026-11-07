# 📝 Taller de Lógica de Programación: Algoritmos, Pseudocódigo y Diagramas de Flujo

**Asignatura:** Lógica de Programación
**Tema:** Estructuras básicas, ciclos, arreglos y funciones.
**Modalidad:** Individual (o en parejas, según indicación del docente).
**Fecha de entrega:** 07/11/2026

---

## 🎯 Objetivo del Taller

Aplicar los conceptos fundamentales de la lógica de programación (secuencias, decisiones, ciclos, vectores, matrices y funciones) mediante el análisis, diseño y representación de soluciones algorítmicas. El estudiante deberá demostrar su capacidad para transformar un enunciado en un pseudocódigo estructurado y su correspondiente diagrama de flujo, además de gestionar su código bajo un sistema de control de versiones.

---

## 📋 Condiciones Generales

1. **Lenguaje de representación:** Se debe utilizar **pseudocódigo** (puede basarse en el estándar visto en clase o en el que utiliza la herramienta PSeInt) y **diagramas de flujo** (dibujados a mano con buena letra o realizados en herramientas digitales como Draw.io, Lucidchart o PSeInt).
2. **Indentación:** El pseudocódigo debe estar correctamente indentado para reflejar los bloques de control (Si, Mientras, Para, etc.).
3. **Declaración de variables:** Todos los algoritmos deben iniciar con la declaración explícita de las variables que se van a utilizar, indicando su tipo de dato (Entero, Real, Carácter, Lógico).
4. **Prueba de escritorio:** Aunque no se entrega como documento aparte, se recomienda realizarla en papel antes de escribir el pseudocódigo para garantizar la lógica.
5. **Originalidad:** Los ejercicios son de diseño propio. Se permite consultar fuentes, pero el pseudocódigo y el diagrama deben ser de autoría del estudiante. Cualquier indicio de copia será sancionado según el reglamento de la institución.
6. **Uso de GitHub:** El taller debe ser entregado a través de un repositorio público en GitHub. El repositorio debe tener una estructura organizada y un archivo `README.md` que sirva como portada.

---

## 📚 Lista de Ejercicios

A continuación, se presentan 15 ejercicios clasificados por nivel de dificultad. Para cada uno, el estudiante deberá:

- **Analizar** el enunciado y definir el objetivo.
- **Escribir** el pseudocódigo completo (con declaración de variables, inicio y fin).
- **Dibujar** el diagrama de flujo correspondiente.

### 🟢 Nivel Básico (5 Ejercicios)

*Enfoque: Variables, operadores aritméticos, secuencias y condicionales simples.*

1. **Cálculo de Promedio:** Leer tres notas de un estudiante y calcular su promedio. Mostrar el resultado en pantalla.
2. **Área de un Rectángulo:** Leer la base y la altura de un rectángulo, calcular y mostrar su área y su perímetro.
3. **Positivo, Negativo o Cero:** Leer un número entero y determinar si es positivo, negativo o cero. Mostrar un mensaje por cada caso.
4. **Calculadora Básica:** Leer dos números enteros y una opción (1: Suma, 2: Resta, 3: Multiplicación, 4: División). Realizar la operación correspondiente y mostrar el resultado. Validar que no se divida por cero.
5. **Conversión de Temperatura:** Leer una temperatura en grados Celsius y convertirla a grados Fahrenheit. Mostrar el resultado.

### 🟡 Nivel Intermedio (5 Ejercicios)

*Enfoque: Ciclos, acumuladores, contadores y condicionales anidados.*

6. **Suma de Números Pares:** Leer un número entero N y calcular la suma de todos los números pares comprendidos entre 1 y N. Mostrar el resultado.
7. **Factorial de un Número:** Leer un número entero positivo y calcular su factorial (ej: 5! = 5*4*3*2*1 = 120). Mostrar el resultado.
8. **Contar Vocales en una Cadena:** Leer una cadena de texto (palabra o frase corta) y contar cuántas vocales contiene. Mostrar el total.
9. **Serie de Fibonacci:** Leer un número N y mostrar los primeros N términos de la serie de Fibonacci (0, 1, 1, 2, 3, 5, 8...).
10. **Validar Contraseña:** Simular un sistema de login. El usuario tiene 3 intentos para ingresar la contraseña correcta ("12345"). Si acierta, mostrar "Bienvenido". Si falla los 3 intentos, mostrar "Cuenta bloqueada".

### 🔴 Nivel Avanzado (5 Ejercicios)

*Enfoque: Vectores, matrices, ciclos anidados, funciones y lógica compleja.*

11. **Mayor y Menor en un Vector:** Leer 10 números enteros en un vector. Determinar cuál es el número mayor, cuál es el menor y en qué posiciones se encuentran.
12. **Suma de Matriz:** Leer una matriz de 3x3 (9 números enteros). Calcular la suma de todos sus elementos y la suma de su diagonal principal.
13. **Números Primos en un Rango:** Leer dos números enteros (inicio y fin). Mostrar todos los números primos que existen en ese rango. Se debe crear una función `EsPrimo(n)` que retorne verdadero o falso.
14. **Ordenamiento Burbuja:** Leer un vector de 8 números enteros y ordenarlo de menor a mayor utilizando el método de burbuja. Mostrar el vector ordenado.
15. **Sistema de Inventario (Menú):** Crear un programa con un menú que permita gestionar un inventario simple (solo nombres de productos en un vector de 10 posiciones). Opciones: 1. Agregar producto, 2. Listar productos, 3. Buscar producto, 4. Salir. Usar un ciclo `Mientras` para mantener el menú activo.

---

## 📦 Entregables

El estudiante debe entregar **un enlace al repositorio de GitHub** con la siguiente estructura obligatoria:

### Estructura del Repositorio

taller-logica-programacion/
│
├── README.md               <-- Portada del taller
├── /ejercicios/
│   ├── basico/
│   │   ├── ej01_promedio.md
│   │   ├── ej02_rectangulo.md
│   │   ├── ej03_positivo_negativo.md
│   │   ├── ej04_calculadora.md
│   │   └── ej05_temperatura.md
│   ├── intermedio/
│   │   ├── ej06_suma_pares.md
│   │   ├── ej07_factorial.md
│   │   ├── ej08_vocales.md
│   │   ├── ej09_fibonacci.md
│   │   └── ej10_login.md
│   └── avanzado/
│       ├── ej11_mayor_menor_vector.md
│       ├── ej12_suma_matriz.md
│       ├── ej13_primos_rango.md
│       ├── ej14_ordenamiento.md
│       └── ej15_inventario.md
│
└── /diagramas/
    ├── ej01_promedio.png
    ├── ej02_rectangulo.png
    ├── ... (una imagen por cada ejercicio)
    └── ej15_inventario.png

### Descripción de los Entregables

1. **Archivo `README.md` (Portada):**

   - Título del taller.
   - Nombre completo del estudiante.
   - Fecha de entrega.
   - Breve descripción del contenido del repositorio.
   - Una tabla de contenido con enlaces a cada uno de los ejercicios (usando enlaces relativos de Markdown).
2. **Archivos de los Ejercicios (`.md`):**

   - Cada archivo debe contener:
     - **Enunciado:** Copiado del taller.
     - **Análisis:** Breve explicación de cómo se resolvió el problema (opcional, pero suma puntos).
     - **Pseudocódigo:** Escrito en un bloque de código Markdown (``text ... ``).
     - **Diagrama de Flujo:** Una imagen embebida que muestre el diagrama de flujo del ejercicio. Se puede usar la sintaxis `![Descripción](ruta/a/la/imagen.png)`.
   - *Nota:* Se recomienda que los diagramas se guarden en la carpeta `/diagramas/` y se enlacen desde los archivos `.md`.
3. **Carpeta `/diagramas/`:**

   - Contendrá las imágenes (PNG, JPG o SVG) de los 15 diagramas de flujo. Los nombres deben ser descriptivos y coincidir con los archivos de los ejercicios.
4. **Commits y Buenas Prácticas:**

   - Se valorará el uso de **commits descriptivos** (ej: "Agrega ejercicio 1: cálculo de promedio").
   - El repositorio debe ser **público** para que el docente pueda revisarlo.
   - Se debe incluir un archivo `.gitignore` si se utilizan herramientas que generan archivos temporales (opcional).

---

## 📊 Rúbrica de Evaluación

| Criterio                                | Excelente (5)                                                                | Bueno (4)                                                | Regular (3)                                      | Insuficiente (2)                                    |
| :-------------------------------------- | :--------------------------------------------------------------------------- | :------------------------------------------------------- | :----------------------------------------------- | :-------------------------------------------------- |
| **Lógica del pseudocódigo**     | Resuelve correctamente los 15 ejercicios, con sintaxis clara e indentación. | Resuelve la mayoría, con pequeños errores de sintaxis. | Resuelve algunos, con errores lógicos notorios. | No resuelve o el pseudocódigo es incomprensible.   |
| **Diagramas de flujo**            | Símbolos correctos, flujo coherente con el pseudocódigo.                   | Símbolos correctos, pequeños errores en el flujo.      | Símbolos incorrectos o flujo confuso.           | No presenta diagramas o son ilegibles.              |
| **Estructura del repositorio**    | Cumple con la estructura solicitada, README completo y commits descriptivos. | Cumple con la estructura, README básico.                | Estructura incompleta o desordenada.             | No utiliza GitHub o el repositorio no es accesible. |
| **Presentación de los archivos** | Archivos `.md` bien formateados, imágenes embebidas correctamente.        | Archivos `.md` con pequeños errores de formato.       | Archivos desordenados o sin formato Markdown.    | Archivos ilegibles o no se entregan.                |
| **Originalidad y análisis**      | Se evidencia análisis propio y originalidad en las soluciones.              | Soluciones propias con poca originalidad.                | Soluciones copiadas o sin análisis.             | Copia evidente.                                     |

---

## ⏰ Fecha de Entrega y Envío

- **Fecha límite:** 14-11-2026
- **Medio de envío:** Subir el enlace del repositorio a la plataforma virtual de la asignatura (Moodle, Google Classroom, etc.) en el espacio destinado para este taller.
- **Formato del enlace:** `https://github.com/tu-usuario/taller-logica-programacion`
- **Enviar por correo electrónico el link**

---

**Nota:** Si tienes dudas sobre cómo crear un repositorio en GitHub, subir archivos o usar Markdown, consulta la documentación oficial de GitHub o pregunta al docente con anticipación. No dejes la entrega para última hora.

### 📌 Instrucciones para usar este archivo `.md`

1. Copia todo el contenido que está entre las tres comillas invertidas (``markdown` ... ``).
2. Abre un editor de texto plano (Bloc de notas, VS Code, Obsidian, Typora, etc.).
3. Pega el contenido.
4. Guarda el archivo con el nombre `Taller_Logica_Programacion.md`.
5. ¡Listo! Ya tienes el taller en formato Markdown, listo para entregar a tus estudiantes o subir a una plataforma.
