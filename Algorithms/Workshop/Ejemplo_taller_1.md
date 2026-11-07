
## 📝 Ejercicio 1: Adquirir una revista

### 1. Algoritmo Informal

**Objetivo:** Conseguir una revista específica para leerla o coleccionarla.

```text
Inicio
1. Definir cuál es la revista que se desea adquirir.
2. Salir de casa y dirigirse al quiosco, librería o punto de venta más cercano.
3. Llegar al mostrador y preguntar al vendedor si tiene la revista deseada.
4. Si la tiene:
    a. Pagar el precio de la revista.
    b. Recibir la revista y guardarla.
    c. Ir a casa a leerla.
5. Si no la tiene:
    a. Preguntar si puede encargarla o pedirla.
    b. Si acepta el encargo, pagar un anticipo (si es necesario) y esperar a que llegue.
    c. Si no acepta, ir a otro punto de venta.
6. Mientras no se tenga la revista y existan puntos de venta por visitar:
    a. Ir al siguiente punto de venta.
    b. Repetir el paso 3.
7. Fin
```

### 2. Pseudocódigo

```text
Algoritmo Adquirir_Revista
Variables
    Carácter: revista_deseada[50]
    Carácter: respuesta_vendedor[2] // 'S' o 'N'
    Lógico: revista_obtenida
    Entero: puntos_visitados, max_puntos
Inicio
    revista_obtenida = Falso
    puntos_visitados = 0
    max_puntos = 3 // Se asume un máximo de 3 puntos de venta
  
    Escriba "¿Qué revista desea adquirir?"
    Lea revista_deseada
  
    Mientras (revista_obtenida = Falso) Y (puntos_visitados < max_puntos) Hacer
        Escriba "Dirigiéndose al punto de venta número ", (puntos_visitados + 1)
        puntos_visitados = puntos_visitados + 1
      
        Escriba "¿Tiene la revista '", revista_deseada, "'? (S/N)"
        Lea respuesta_vendedor
      
        Si respuesta_vendedor = 'S' Entonces
            Escriba "Pagando la revista..."
            Escriba "Revista adquirida con éxito."
            revista_obtenida = Verdadero
        Sino
            Escriba "El vendedor no tiene la revista."
            Escriba "¿Acepta encargarla? (S/N)"
            Lea respuesta_vendedor
            Si respuesta_vendedor = 'S' Entonces
                Escriba "Dejando encargo y anticipo..."
                Escriba "Esperando a que llegue la revista..."
                revista_obtenida = Verdadero
            Sino
                Escriba "Buscando otro punto de venta..."
            Fin_Si
        Fin_Si
    Fin_Mientras
  
    Si revista_obtenida = Verdadero Entonces
        Escriba "¡Disfruta tu revista!"
    Sino
        Escriba "No fue posible adquirir la revista en los puntos visitados."
    Fin_Si
Fin
```

---

## 📝 Ejercicio 2: Entrar a una casa que está con llave

### 1. Algoritmo Informal

**Objetivo:** Ingresar al interior de una casa cuya puerta principal está cerrada con llave.

```text
Inicio
1. Llegar a la puerta de la casa.
2. Revisar si la puerta está abierta.
3. Si está abierta: entrar y fin.
4. Si está cerrada con llave:
    a. Revisar si se tiene la llave correcta en el bolsillo o llavero.
    b. Si se tiene: insertar la llave en la cerradura, girarla y abrir la puerta. Entrar.
    c. Si no se tiene:
        i. Buscar una llave de repuesto en un lugar seguro (ej: debajo del matero, con un vecino).
        ii. Si se encuentra la llave de repuesto: usarla para abrir.
        iii. Si no se encuentra:
            - Llamar a un cerrajero.
            - Esperar a que el cerrajero llegue.
            - Permitir que el cerrajero abra la puerta.
            - Pagar al cerrajero.
            - Entrar.
5. Fin
```

### 2. Pseudocódigo

```text
Algoritmo Entrar_Casa_Con_Llave
Variables
    Lógico: puerta_abierta, tengo_llave, hay_repuesto, cerrajero_disponible
Inicio
    Escriba "Llegando a la puerta de la casa..."
  
    Escriba "¿La puerta está abierta? (Verdadero/Falso)"
    Lea puerta_abierta
  
    Si puerta_abierta = Verdadero Entonces
        Escriba "Entrando a la casa..."
    Sino
        Escriba "La puerta está cerrada. ¿Tienes la llave? (Verdadero/Falso)"
        Lea tengo_llave
      
        Si tengo_llave = Verdadero Entonces
            Escriba "Insertando llave, girando y abriendo puerta..."
            Escriba "Entrando a la casa..."
        Sino
            Escriba "Buscando llave de repuesto..."
            Escriba "¿Se encontró llave de repuesto? (Verdadero/Falso)"
            Lea hay_repuesto
          
            Si hay_repuesto = Verdadero Entonces
                Escriba "Usando llave de repuesto para abrir..."
                Escriba "Entrando a la casa..."
            Sino
                Escriba "Llamando a un cerrajero..."
                Escriba "¿El cerrajero está disponible? (Verdadero/Falso)"
                Lea cerrajero_disponible
              
                Si cerrajero_disponible = Verdadero Entonces
                    Escriba "Esperando al cerrajero..."
                    Escriba "El cerrajero abre la puerta."
                    Escriba "Pagando al cerrajero..."
                    Escriba "Entrando a la casa..."
                Sino
                    Escriba "No se pudo entrar a la casa. Intente más tarde."
                Fin_Si
            Fin_Si
        Fin_Si
    Fin_Si
Fin
```

---

## 📝 Ejercicio 3: Dar un beso

### 1. Algoritmo Informal

**Objetivo:** Dar un beso a otra persona de manera consentida y afectuosa.

```text
Inicio
1. Acercarse a la persona a quien se desea besar.
2. Verificar si la otra persona está de acuerdo (consentimiento).
3. Si no está de acuerdo: detenerse y no dar el beso.
4. Si está de acuerdo:
    a. Inclinarse ligeramente hacia la persona.
    b. Cerrar los ojos (opcional).
    c. Fruncir ligeramente los labios.
    d. Acercar los labios a la mejilla, frente o labios de la otra persona (según el tipo de beso).
    e. Hacer contacto suave con los labios.
    f. Mantener el contacto por un instante breve (1-2 segundos).
    g. Separarse lentamente.
    h. Sonreír y expresar afecto.
5. Fin
```

### 2. Pseudocódigo

```text
Algoritmo Dar_Un_Beso
Variables
    Lógico: consentimiento
    Carácter: tipo_beso[20] // "mejilla", "frente", "labios"
    Entero: duracion_segundos
Inicio
    Escriba "Acercándose a la persona..."
  
    Escriba "¿La persona da su consentimiento para el beso? (Verdadero/Falso)"
    Lea consentimiento
  
    Si consentimiento = Verdadero Entonces
        Escriba "¿Qué tipo de beso será? (mejilla/frente/labios)"
        Lea tipo_beso
      
        Escriba "Inclinándose ligeramente hacia la persona..."
        Escriba "Cerrando los ojos (opcional)..."
        Escriba "Frunciendo ligeramente los labios..."
        Escriba "Acercando los labios a la ", tipo_beso, " de la persona..."
        Escriba "Haciendo contacto suave..."
      
        duracion_segundos = 2
        Escriba "Manteniendo el contacto por ", duracion_segundos, " segundos..."
      
        Escriba "Separándose lentamente..."
        Escriba "Sonriendo y expresando afecto..."
        Escriba "¡Beso dado con éxito!"
    Sino
        Escriba "No se dará el beso. Se respeta la decisión de la otra persona."
    Fin_Si
Fin
```

---

### 📌 Notas sobre los pseudocódigos

1. **Variables lógicas:** Se utilizan variables de tipo `Lógico` (Verdadero/Falso) para representar condiciones de decisión.
2. **Estructuras de control:** Se emplean `Si-Entonces-Sino` para las decisiones y `Mientras` para el ciclo en el ejercicio de la revista.
3. **Consentimiento:** En el ejercicio del beso, se incluye explícitamente la verificación del consentimiento, lo cual es fundamental en cualquier interacción afectiva.
4. **Simplicidad:** Estos algoritmos son informales, pero su traducción a pseudocódigo sigue las normas técnicas del libro (declaración de variables, Inicio, Fin, indentación).
