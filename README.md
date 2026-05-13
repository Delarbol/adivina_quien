# Juego: Adivina Quién

## Descripción general

En este proyecto vas a desarrollar una versión en consola del juego **Adivina Quién** usando Python.

El objetivo del juego es que el programa piense en un personaje secreto y que el usuario intente descubrirlo haciendo preguntas sobre sus características.

Este proyecto busca practicar la organización del código en **módulos**, separando el programa en varios archivos según su responsabilidad.

No se debe usar Programación Orientada a Objetos.  
El proyecto debe resolverse usando únicamente los temas vistos hasta el momento:

- Variables
- Condicionales
- Ciclos
- Listas
- Diccionarios
- Funciones
- Archivos
- Módulos propios

---

## Objetivo del proyecto

Construir un juego funcional de **Adivina Quién** en el que:

1. El programa cargue una lista de personajes desde un archivo.
2. Cada personaje tenga varias características.
3. El programa seleccione un personaje secreto.
4. El usuario haga preguntas para descartar personajes.
5. El programa responda según las características del personaje secreto.
6. El usuario pueda intentar adivinar el personaje.
7. El juego indique si el usuario ganó o perdió.

---

## Reglas generales del juego

El juego debe tener una lista de personajes. Cada personaje debe estar representado mediante un diccionario con información como:

- Nombre
- Género
- Color de cabello
- Usa gafas
- Tiene sombrero
- Tiene barba
- Color de ojos
- Otro rasgo que el grupo quiera agregar

El programa debe seleccionar aleatoriamente un personaje secreto.

El usuario podrá hacer preguntas como:

- ¿Tiene gafas?
- ¿Tiene barba?
- ¿Tiene el cabello negro?
- ¿Es mujer?
- ¿Tiene sombrero?

El programa debe responder con `sí` o `no`, dependiendo de las características del personaje secreto.

Después de varias preguntas, el usuario podrá intentar adivinar el personaje.

---

## Restricciones técnicas

Para este proyecto **no se permite usar**:

- Clases
- Objetos propios
- Herencia
- Librerías externas
- Interfaces gráficas
- Bases de datos
- Inteligencia artificial
- Código copiado de internet sin explicación

Sí se permite usar:

- `random`
- Lectura y escritura de archivos
- Funciones
- Listas
- Diccionarios
- Ciclos `for` y `while`
- Condicionales `if`, `elif`, `else`
- Módulos creados por ustedes

---

## Estructura esperada del repositorio

El proyecto debe organizarse de la siguiente manera:

```text
adivina-quien/
│
├── README.md
│
├── main.py
│
├── data/
│   └── personajes.txt
│
├── modules/
│   ├── cargar_datos.py
│   ├── juego.py
│   ├── preguntas.py
│   ├── personajes.py
│   └── archivos.py
│
└── docs/
    └── explicacion_proyecto.md
```

---

## Descripción de cada archivo y carpeta

### `README.md`

Este archivo contiene las instrucciones generales del proyecto.

Debe explicar:

* De qué trata el juego.
* Cómo está organizado el proyecto.
* Cómo ejecutar el programa.
* Qué archivos hacen parte de la solución.
* Qué funcionalidades fueron implementadas.

---

### `main.py`

Este será el archivo principal del proyecto.

Desde este archivo se debe iniciar el juego.

Debe encargarse de:

* Mostrar el mensaje de bienvenida.
* Llamar las funciones principales del juego.
* Controlar el flujo general del programa.
* Finalizar el juego correctamente.

Este archivo no debe tener toda la lógica del juego.
Debe apoyarse en los módulos ubicados dentro de la carpeta `modules`.

---

### Carpeta `data/`

Esta carpeta debe contener los archivos de datos usados por el programa.

---

### `data/personajes.txt`

Este archivo debe guardar la información de los personajes.

Cada línea del archivo debe representar un personaje.

Por ejemplo, cada personaje puede tener información como:

```text
nombre,genero,cabello,gafas,sombrero,barba,ojos
Ana,femenino,negro,no,no,no,cafes
Carlos,masculino,castano,si,no,si,verdes
Luisa,femenino,rubio,si,si,no,azules
```

El grupo puede agregar más personajes o más características, siempre que el programa pueda leerlas correctamente.

---

### Carpeta `modules/`

Esta carpeta debe contener los módulos del proyecto.

Cada módulo debe tener funciones relacionadas con una responsabilidad específica.

La idea es evitar que todo el código quede escrito en un solo archivo.

---

### `modules/cargar_datos.py`

Este módulo debe encargarse de cargar la información inicial del juego.

Debe incluir funciones para:

* Leer el archivo de personajes.
* Convertir cada línea del archivo en una estructura útil para Python.
* Crear una lista de diccionarios con los personajes.
* Validar que los datos estén completos.

Ejemplo conceptual de lo que debe producir este módulo:

```text
[
    {
        "nombre": "Ana",
        "genero": "femenino",
        "cabello": "negro",
        "gafas": "no",
        "sombrero": "no",
        "barba": "no",
        "ojos": "cafes"
    },
    {
        "nombre": "Carlos",
        "genero": "masculino",
        "cabello": "castano",
        "gafas": "si",
        "sombrero": "no",
        "barba": "si",
        "ojos": "verdes"
    }
]
```

---

### `modules/juego.py`

Este módulo debe contener la lógica principal del juego.

Debe incluir funciones para:

* Iniciar una partida.
* Seleccionar el personaje secreto.
* Controlar los turnos.
* Verificar si el usuario ganó o perdió.
* Mostrar mensajes importantes del juego.
* Controlar cuántas preguntas puede hacer el usuario.

Este módulo debe coordinar las funciones de otros módulos, pero no debe encargarse de leer archivos directamente.

---

### `modules/preguntas.py`

Este módulo debe manejar todo lo relacionado con las preguntas del usuario.

Debe incluir funciones para:

* Mostrar las preguntas disponibles.
* Recibir la pregunta del usuario.
* Validar que la pregunta sea válida.
* Comparar la pregunta con las características del personaje secreto.
* Responder `sí` o `no`.

Las preguntas pueden manejarse mediante opciones numeradas.

Ejemplo:

```text
1. ¿Tiene gafas?
2. ¿Tiene sombrero?
3. ¿Tiene barba?
4. ¿Tiene cabello negro?
5. ¿Tiene ojos azules?
6. Intentar adivinar el personaje
```

---

### `modules/personajes.py`

Este módulo debe manejar operaciones relacionadas con los personajes.

Debe incluir funciones para:

* Mostrar la lista de personajes disponibles.
* Buscar un personaje por nombre.
* Filtrar personajes según una característica.
* Mostrar las características de un personaje, si el juego lo permite.
* Verificar si el nombre ingresado por el usuario existe.

Este módulo debe trabajar principalmente con listas y diccionarios.

---

### `modules/archivos.py`

Este módulo debe encargarse de funciones adicionales relacionadas con archivos.

Puede incluir funciones para:

* Guardar el resultado de una partida.
* Registrar el historial de partidas.
* Guardar el nombre del jugador.
* Guardar si ganó o perdió.
* Guardar cuántos intentos utilizó.

Por ejemplo, el juego puede crear un archivo como:

```text
data/historial.txt
```

Ese archivo podría guardar información como:

```text
Jugador: Camilo | Resultado: ganó | Personaje: Ana | Preguntas usadas: 5
Jugador: Laura | Resultado: perdió | Personaje: Carlos | Preguntas usadas: 8
```

---

### Carpeta `docs/`

Esta carpeta debe contener documentación adicional del proyecto.

---

### `docs/explicacion_proyecto.md`

En este archivo el grupo debe explicar brevemente cómo desarrolló el proyecto.

Debe incluir:

* Cómo dividieron el código en módulos.
* Qué hace cada archivo.
* Qué estructuras de datos usaron.
* Cómo usaron listas.
* Cómo usaron diccionarios.
* Cómo usaron archivos.
* Qué dificultades encontraron.
* Qué aprendieron con el proyecto.

---

## Funcionalidades mínimas requeridas

El proyecto debe cumplir como mínimo con las siguientes funcionalidades:

1. Mostrar un mensaje de bienvenida.
2. Cargar personajes desde un archivo.
3. Guardar los personajes en una lista de diccionarios.
4. Seleccionar aleatoriamente un personaje secreto.
5. Mostrar los personajes disponibles al inicio del juego.
6. Permitir al usuario hacer preguntas.
7. Responder las preguntas con base en el personaje secreto.
8. Permitir al usuario intentar adivinar el personaje.
9. Indicar si el usuario ganó o perdió.
10. Guardar el resultado de la partida en un archivo.

---

## Funcionalidades opcionales

Si el grupo termina las funcionalidades mínimas, puede agregar algunas de las siguientes mejoras:

* Limitar el número de preguntas.
* Mostrar un historial de partidas anteriores.
* Permitir jugar varias rondas.
* Permitir que el usuario seleccione la dificultad.
* Agregar más personajes.
* Agregar más características.
* Permitir que el usuario cree nuevos personajes desde el programa.
* Mostrar los personajes descartados.
* Mostrar los personajes que todavía podrían ser el personaje secreto.

---

## Recomendación de flujo del programa

El programa puede seguir este flujo general:

```text
1. Mostrar bienvenida.
2. Pedir el nombre del jugador.
3. Cargar personajes desde el archivo.
4. Mostrar personajes disponibles.
5. Seleccionar personaje secreto.
6. Iniciar ciclo principal del juego.
7. Mostrar menú de preguntas.
8. Recibir opción del usuario.
9. Responder pregunta o permitir adivinar.
10. Verificar si el usuario ganó o perdió.
11. Guardar resultado en historial.
12. Preguntar si desea jugar otra vez.
13. Finalizar el programa.
```

---

## Organización recomendada del trabajo

Cada integrante del grupo puede encargarse de una parte del proyecto.

Una posible división es:

* Integrante 1: lectura de archivos y carga de personajes.
* Integrante 2: lógica principal del juego.
* Integrante 3: preguntas y validaciones.
* Integrante 4: historial de partidas y documentación.

Aunque se dividan el trabajo, todos los integrantes deben entender cómo funciona el proyecto completo.

---

## Buenas prácticas esperadas

El proyecto debe cumplir con las siguientes buenas prácticas:

* Usar nombres claros para variables y funciones.
* Separar el código en módulos.
* Evitar repetir código innecesariamente.
* Escribir funciones pequeñas y claras.
* Validar las entradas del usuario.
* Usar comentarios cuando sea necesario.
* Mantener una estructura ordenada de carpetas.
* Probar el programa varias veces antes de entregarlo.
* No dejar código que no se use.
* No dejar mensajes de prueba innecesarios.

---

## Ejemplo de nombres adecuados

Usen nombres claros como:

```text
personajes
personaje_secreto
pregunta_usuario
opcion_menu
historial_partidas
numero_preguntas
resultado_partida
```

Eviten nombres poco claros como:

```text
x
y
a
b
cosa
dato
lista1
dicc
```

---

## Entrega del proyecto

El repositorio debe contener:

```text
README.md
main.py
data/personajes.txt
modules/cargar_datos.py
modules/juego.py
modules/preguntas.py
modules/personajes.py
modules/archivos.py
docs/explicacion_proyecto.md
```

Todos los archivos deben estar organizados correctamente.

El programa debe poder ejecutarse desde `main.py`.

---

## Criterios de evaluación

| Criterio                      | Descripción                                                      | Puntaje sugerido |
| ----------------------------- | ---------------------------------------------------------------- | ---------------: |
| Funcionamiento general        | El juego funciona correctamente de principio a fin               |              1.0 |
| Uso de listas y diccionarios  | Los personajes se manejan mediante estructuras adecuadas         |              0.8 |
| Uso de archivos               | El programa lee personajes y guarda resultados                   |              0.8 |
| Uso de condicionales y ciclos | El flujo del juego usa decisiones y repetición correctamente     |              0.7 |
| Organización en módulos       | El código está separado en archivos con responsabilidades claras |              1.0 |
| Claridad y estilo             | Variables claras, funciones ordenadas y código legible           |              0.5 |
| Documentación                 | README y explicación del proyecto completos                      |              0.2 |
| **Total**                     |                                                                  |          **5.0** |

---

## Recomendación final

Antes de entregar, el grupo debe verificar que:

* El programa inicia correctamente desde `main.py`.
* Los personajes se cargan desde el archivo.
* El juego no se rompe si el usuario escribe una opción inválida.
* El usuario puede hacer preguntas.
* El usuario puede intentar adivinar.
* El programa muestra si ganó o perdió.
* El resultado queda guardado en un archivo.
* El código está separado en módulos.
* El repositorio está ordenado.

El objetivo principal no es solo que el juego funcione, sino que el código esté bien organizado y sea fácil de entender.

```
```
