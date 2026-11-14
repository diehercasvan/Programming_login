
# 📝 Taller 4 : Tipos de Datos en Lógica de Programación

**Asignatura:** Lógica de Programación
**Tema:** Variables y Tipos de Datos
**Basado en:** *Lógica de programación* de Omar Iván Trejos Buriticá (Capítulo 3)
**Modalidad:** Individual
**Fecha de entrega:** [Insertar fecha]

---

## 🎯 Objetivo del Taller

Comprender la importancia de los tipos de datos en la lógica de programación, identificando cuándo usar cada uno (Entero, Real, Carácter, Lógico y Cadena) y cómo afectan el comportamiento de un algoritmo. El estudiante aprenderá a declarar variables con el tipo adecuado y a realizar operaciones básicas respetando las reglas de cada tipo.

---

## 📖 Parte 1: Contextualización Teórica

### 1.1. ¿Qué es un tipo de dato?

En lógica de programación, un **tipo de dato** define la naturaleza de la información que se puede almacenar en una variable. Determina:

- **Qué valores** puede contener (números, letras, valores lógicos, etc.).
- **Qué operaciones** se pueden realizar con esos valores.
- **Cómo se almacena** en la memoria del computador.

El autor del libro afirma que las variables son *"como unas cajitas de diferentes tamaños"*, y el tipo de dato es lo que define el tamaño y la forma de esa cajita.

### 1.2. Tipos de datos básicos

| Tipo de Dato        | Definición                                                                           | Ejemplos             | ¿Genera decimales en operaciones? | Operadores permitidos        |
| :------------------ | :------------------------------------------------------------------------------------ | :------------------- | :--------------------------------- | :--------------------------- |
| **Entero**    | Números sin punto decimal. Se rige por la aritmética entera.                        | 25, -96, 0, 1000     | No                                 | +, -, *, /, mod, ^           |
| **Real**      | Números con punto decimal. Se rige por la aritmética real.                          | 12.3, -78.56, 45.0   | Sí                                | +, -, *, /, ^                |
| **Carácter** | Un solo símbolo (letra, dígito, signo de puntuación). Se basa en el código ASCII. | 'A', 'b', '5', '@'   | No aplica                          | Comparación (=, <>, <, >)   |
| **Lógico**   | Valores de verdad: Verdadero o Falso.                                                 | Verdadero, Falso     | No aplica                          | Y, O, NO                     |
| **Cadena**    | Conjunto de caracteres. Se acota entre comillas dobles.                               | "Hola", "12345", "A" | No aplica                          | Comparación, concatenación |

### 1.3. El código ASCII

El tipo de dato **Carácter** se basa en el código ASCII (American Standard Code for Information Interchange), que asigna un número entero a cada símbolo. Por ejemplo:

- La letra 'A' tiene el código ASCII 65.
- La letra 'a' tiene el código ASCII 97.
- El dígito '0' tiene el código ASCII 48.
- El dígito '1' tiene el código ASCII 49.

Esto significa que, internamente, el computador almacena números, pero los interpreta como caracteres.

### 1.4. Aritmética entera vs. aritmética real

- **Aritmética entera:** Las operaciones con números enteros **nunca generan decimales**. Por ejemplo, `7 / 2` da como resultado `3` (no 3.5), porque los decimales se descartan.
- **Aritmética real:** Las operaciones con números reales **sí generan decimales**. Por ejemplo, `7.0 / 2.0` da como resultado `3.5`.

Esta diferencia es crucial al momento de elegir el tipo de dato para una variable.

---

## 🔍 Parte 2: Ejemplos Resueltos

### 📌 Ejemplo 1: Declaración y uso de variables enteras

**Pseudocódigo:**

```text
Algoritmo Ejemplo_Enteros
Variables
    Entero: edad, año_nacimiento, año_actual, edad_calculada
Inicio
    año_actual = 2024
    Escriba "Digite su año de nacimiento:"
    Lea año_nacimiento
    edad_calculada = año_actual - año_nacimiento
    Escriba "Su edad aproximada es: ", edad_calculada
Fin
```

**Explicación:**

- Se declaran cuatro variables de tipo **Entero**.
- La operación `año_actual - año_nacimiento` genera un resultado entero.
- Si el usuario ingresa `1990`, el resultado será `34` (2024 - 1990). No hay decimales.

---

### 📌 Ejemplo 2: Declaración y uso de variables reales

**Pseudocódigo:**

```text
Algoritmo Ejemplo_Reales
Variables
    Real: precio, descuento, precio_final
Inicio
    Escriba "Digite el precio del producto:"
    Lea precio
    Escriba "Digite el porcentaje de descuento (ej: 0.15 para 15%):"
    Lea descuento
    precio_final = precio - (precio * descuento)
    Escriba "El precio final es: ", precio_final
Fin
```

**Explicación:**

- Se declaran tres variables de tipo **Real**.
- Si el precio es `100.50` y el descuento es `0.15`, el precio final será `85.425`. Aquí sí se generan decimales.
- Es importante usar tipo Real para precios y porcentajes, ya que los resultados pueden tener decimales.

---

### 📌 Ejemplo 3: Declaración y uso de variables de tipo carácter

**Pseudocódigo:**

```text
Algoritmo Ejemplo_Caracter
Variables
    Carácter: letra, letra_mayuscula
Inicio
    Escriba "Digite una letra minúscula:"
    Lea letra
    // Convertir a mayúscula usando el código ASCII
    letra_mayuscula = letra - 32
    Escriba "La letra en mayúscula es: ", letra_mayuscula
Fin
```

**Explicación:**

- Se declaran dos variables de tipo **Carácter**.
- La operación `letra - 32` aprovecha el código ASCII: la 'a' es 97, y la 'A' es 65 (97 - 32 = 65).
- Si el usuario ingresa 'a', el resultado será 'A'.
- Nota: No todos los lenguajes permiten operar caracteres como números, pero en pseudocódigo es útil para entender el concepto.

---

### 📌 Ejemplo 4: Declaración y uso de variables lógicas

**Pseudocódigo:**

```text
Algoritmo Ejemplo_Logicos
Variables
    Lógico: es_mayor_de_edad, tiene_permiso
    Entero: edad
Inicio
    Escriba "Digite su edad:"
    Lea edad
    es_mayor_de_edad = (edad >= 18)
    Escriba "¿Tiene permiso de sus padres? (Verdadero/Falso):"
    Lea tiene_permiso
  
    Si es_mayor_de_edad O tiene_permiso Entonces
        Escriba "Puede ingresar al evento."
    Sino
        Escriba "No puede ingresar al evento."
    Fin_Si
Fin
```

**Explicación:**

- Se declaran dos variables de tipo **Lógico**.
- `es_mayor_de_edad` se asigna con el resultado de una comparación (`edad >= 18`), que es Verdadero o Falso.
- La condición `es_mayor_de_edad O tiene_permiso` usa el operador lógico **O** (OR).
- Si la edad es 20, `es_mayor_de_edad` será Verdadero, y el mensaje será "Puede ingresar".

---

### 📌 Ejemplo 5: Declaración y uso de cadenas

**Pseudocódigo:**

```text
Algoritmo Ejemplo_Cadenas
Variables
    Carácter: nombre[50], apellido[50], nombre_completo[100]
Inicio
    Escriba "Digite su nombre:"
    Lea nombre
    Escriba "Digite su apellido:"
    Lea apellido
    nombre_completo = nombre + " " + apellido
    Escriba "Su nombre completo es: ", nombre_completo
Fin
```

**Explicación:**

- Se declaran tres variables de tipo **Cadena** (arreglos de caracteres).
- La operación `nombre + " " + apellido` concatena las cadenas.
- Si el nombre es "Juan" y el apellido es "Pérez", el resultado será "Juan Pérez".

---

### 📌 Ejemplo 6: Diferencia entre aritmética entera y real

**Pseudocódigo:**

```text
Algoritmo Diferencia_Aritmetica
Variables
    Entero: resultado_entero
    Real: resultado_real
Inicio
    resultado_entero = 7 / 2
    resultado_real = 7.0 / 2.0
    Escriba "Resultado entero: ", resultado_entero
    Escriba "Resultado real: ", resultado_real
Fin
```

**Explicación:**

- `resultado_entero = 7 / 2` da como resultado `3` (aritmética entera, se descartan los decimales).
- `resultado_real = 7.0 / 2.0` da como resultado `3.5` (aritmética real, se conservan los decimales).
- Esto demuestra por qué es importante elegir el tipo de dato adecuado.

---

## ✏️ Parte 3: Ejercicios Propuestos

**Instrucción:** Para cada ejercicio, escribe el pseudocódigo declarando las variables con el tipo de dato adecuado. Justifica tu elección.

### Ejercicio 1: Calcular el área de un triángulo

**Enunciado:** Leer la base y la altura de un triángulo, y calcular su área (fórmula: base × altura / 2).

**Preguntas:**

- ¿Qué tipo de dato usarías para la base y la altura? ¿Entero o Real? ¿Por qué?
- ¿Qué tipo de dato usarías para el área?
- Escribe el pseudocódigo.

---

### Ejercicio 2: Determinar si un número es positivo

**Enunciado:** Leer un número y determinar si es positivo. Mostrar un mensaje.

**Preguntas:**

- ¿Qué tipo de dato usarías para el número? ¿Entero o Real? ¿Por qué?
- ¿Necesitas una variable lógica? ¿Para qué?
- Escribe el pseudocódigo.

---

### Ejercicio 3: Convertir una letra a mayúscula

**Enunciado:** Leer una letra minúscula y convertirla a mayúscula usando el código ASCII (restar 32).

**Preguntas:**

- ¿Qué tipo de dato usarías para la letra?
- ¿Qué pasa si el usuario ingresa un número en lugar de una letra?
- Escribe el pseudocódigo.

---

### Ejercicio 4: Calcular el promedio de tres notas

**Enunciado:** Leer tres notas (pueden tener decimales) y calcular su promedio.

**Preguntas:**

- ¿Qué tipo de dato usarías para las notas? ¿Entero o Real? ¿Por qué?
- ¿Qué tipo de dato usarías para el promedio?
- Escribe el pseudocódigo.

---

### Ejercicio 5: Validar si un usuario puede votar

**Enunciado:** Leer la edad de una persona y determinar si puede votar (mayor o igual a 18 años). Mostrar un mensaje.

**Preguntas:**

- ¿Qué tipo de dato usarías para la edad? ¿Entero o Real? ¿Por qué?
- ¿Necesitas una variable lógica? ¿Para qué?
- Escribe el pseudocódigo.

---

### Ejercicio 6: Concatenar nombre y apellido

**Enunciado:** Leer el nombre y el apellido de una persona, y mostrar el nombre completo.

**Preguntas:**

- ¿Qué tipo de dato usarías para el nombre y el apellido? ¿Carácter o Cadena? ¿Por qué?
- ¿Cómo se concatenan las cadenas en pseudocódigo?
- Escribe el pseudocódigo.

---

### Ejercicio 7: Diferencia entre aritmética entera y real

**Enunciado:** Realizar las siguientes operaciones y mostrar los resultados:

- `a = 10 / 3` (con variables enteras)
- `b = 10.0 / 3.0` (con variables reales)

**Preguntas:**

- ¿Qué diferencia hay entre los resultados?
- ¿Por qué ocurre esta diferencia?
- Escribe el pseudocódigo.

---

### Ejercicio 8: Calcular el salario neto

**Enunciado:** Leer el salario bruto de un empleado y el porcentaje de descuento (ej: 0.10 para 10%). Calcular y mostrar el salario neto.

**Preguntas:**

- ¿Qué tipo de dato usarías para el salario y el descuento? ¿Entero o Real? ¿Por qué?
- ¿Qué pasa si el descuento se ingresa como entero (ej: 10 en lugar de 0.10)? ¿Cómo lo corregirías?
- Escribe el pseudocódigo.

---

### Ejercicio 9: Determinar si un carácter es una vocal

**Enunciado:** Leer un carácter y determinar si es una vocal (a, e, i, o, u). Mostrar un mensaje.

**Preguntas:**

- ¿Qué tipo de dato usarías para el carácter?
- ¿Cómo compararías el carácter con las vocales?
- Escribe el pseudocódigo.

---

### Ejercicio 10: Calcular el factorial de un número

**Enunciado:** Leer un número entero positivo y calcular su factorial (ej: 5! = 120). Mostrar el resultado.

**Preguntas:**

- ¿Qué tipo de dato usarías para el número y el factorial? ¿Entero o Real? ¿Por qué?
- ¿Qué pasa si el número es muy grande? ¿Qué tipo de dato usarías para evitar desbordamiento?
- Escribe el pseudocódigo.

---

## 📦 Entregables

El estudiante debe entregar un documento (Word, PDF o Markdown) con:

1. **Portada** (nombre, fecha, título del taller).
2. **Parte 1:** Un resumen de media página sobre la importancia de los tipos de datos en la lógica de programación (basado en el libro y en tu investigación).
3. **Parte 2:** Los **10 ejercicios propuestos** resueltos, cada uno con:
   - La justificación del tipo de dato elegido para cada variable.
   - El pseudocódigo completo (con declaración de variables, inicio y fin).
   - Una breve prueba de escritorio (opcional, pero suma puntos).
4. **Reflexión final:** Un párrafo sobre qué aprendiste al elegir tipos de datos y por qué crees que es importante hacerlo correctamente antes de programar.

---

## 📊 Rúbrica de Evaluación (Sugerida)

| Criterio                                     | Excelente (5)                                                                             | Bueno (4)                                                            | Regular (3)                                                             | Insuficiente (2)                               |
| :------------------------------------------- | :---------------------------------------------------------------------------------------- | :------------------------------------------------------------------- | :---------------------------------------------------------------------- | :--------------------------------------------- |
| **Comprensión de los tipos de datos** | El resumen demuestra dominio del tema, cita al autor y explica la diferencia entre tipos. | El resumen es correcto pero superficial.                             | El resumen es confuso o incompleto.                                     | No presenta resumen.                           |
| **Elección del tipo de dato**         | En los 10 ejercicios se elige el tipo correcto y se justifica adecuadamente.              | En la mayoría se elige el tipo correcto con justificación básica. | En algunos se elige el tipo correcto, pero la justificación es débil. | No se justifica o se elige el tipo incorrecto. |
| **Pseudocódigo**                      | Los 10 pseudocódigos son correctos, con declaración de variables, inicio y fin.         | La mayoría son correctos con pequeños errores.                     | Algunos son correctos, pero con errores notorios.                       | No presenta pseudocódigos o son incorrectos.  |
| **Presentación y orden**              | Documento impecable, bien redactado, tablas claras.                                       | Documento ordenado con pequeños errores.                            | Documento desordenado pero legible.                                     | Documento desordenado e ilegible.              |
| **Reflexión final**                   | Reflexión profunda y personal sobre la utilidad de los tipos de datos.                   | Reflexión correcta pero superficial.                                | Reflexión muy breve.                                                   | No presenta reflexión.                        |

---

## 💡 Consejos del Autor (para tener en cuenta)

> *"Las variables son como unas cajitas de diferentes tamaños y, por tal motivo, se deben declarar previamente para que el computador las dimensione de acuerdo a las necesidades."*

> *"El hecho de que los datos de tipo entero no generen decimales significa que operan con un juego de reglas llamado aritmética entera."*

> *"Un dato tipo carácter es un equivalente del código ASCII. Cuando usted presiona en su teclado la letra A, realmente se genera por dentro de su computador el número 65."*

---

**Nota:** Si tienes dudas sobre cómo elegir el tipo de dato adecuado, revisa el Capítulo 3 del libro de Omar Iván Trejos Buriticá o consulta los ejemplos resueltos de este taller.

```

---

### 📌 Instrucciones para usar este archivo `.md`

1. Copia todo el contenido que está entre las tres comillas invertidas (````markdown` ... ````).
2. Abre un editor de texto plano (Bloc de notas, VS Code, Obsidian, Typora, etc.).
3. Pega el contenido.
4. Guarda el archivo con el nombre `Taller_Tipos_de_Datos.md`.
5. ¡Listo! Ya tienes el taller en formato Markdown, con ejemplos resueltos, ejercicios propuestos, entregables y rúbrica de evaluación.

Si necesitas que ajuste algo (por ejemplo, agregar más ejemplos, cambiar los ejercicios propuestos o incluir diagramas de flujo), házmelo saber.
```
