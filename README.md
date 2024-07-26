[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/EID3BRwM)
# Unidad 1
## Conceptos generales de procesadores 


### 1. CPU (Central Processing Unit)
-  La CPU es el cerebro del ordenador donde se realizan la mayoría de los cálculos. Ejecuta instrucciones del programa mediante el proceso de búsqueda, decodificación y ejecución.

### 2. ALU (Arithmetic Logic Unit)
-  La ALU es una parte de la CPU que se encarga de realizar operaciones aritméticas (suma, resta, etc.) y lógicas (AND, OR, NOT).

## 3. Registros
### a. De propósito general
 Son registros utilizados para almacenar datos temporales durante la ejecución de programas.

### b. Específicos
  - **Program Counter (PC)**:
 Es un registro que contiene la dirección de la siguiente instrucción a ejecutar.
  - **Stack Pointer (SP)**:
 Es un registro que apunta a la parte superior de la pila, utilizada para el almacenamiento temporal de datos y direcciones.

### 4. Unidad de Control
 La unidad de control dirige el funcionamiento de la CPU, decodificando instrucciones del programa y generando señales de control para coordinar las operaciones internas.

### 5. Buses de Datos y de Dirección
 Los buses son canales de comunicación que transportan datos y direcciones entre la CPU, la memoria y otros dispositivos. El bus de datos transfiere datos, mientras que el bus de dirección transfiere direcciones de memoria.

### 6. Memoria
 La memoria es el componente del sistema que almacena datos e instrucciones que la CPU necesita para ejecutar programas. Puede ser de acceso rápido (RAM) o de almacenamiento permanente (ROM).

### 7. Opcode
 Un opcode (código de operación) es una parte de una instrucción de máquina que especifica la operación que debe realizarse. Es fundamental para la ejecución de instrucciones por parte de la CPU.

## Funcionamiento de la simulación 16 bits
El pc cuenta con una arquitectura Harvard, esto debido a que tiene dos memorias ubicadas en diferente sitio. Una destinada para las instrucciones y otra para los datos. En este caso específico la memoria ROM almacena el programa a ejecutarse, esta cuenta con dos registros, D y A. a través del registro D se transmiten las instrucciones. La CPU se encarga de los procesos de fetch, decode and execute. el bloque memory se encarga de almacenar los datos. 

![CPU 16 bits](https://www.google.com/url?sa=i&url=https%3A%2F%2Fhackaday.io%2Fproject%2F174192-simple-16-bit-computer&psig=AOvVaw1kVjXM_QaAREYIMGEThZPM&ust=1721939359297000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCPiXvJHCwIcDFQAAAAAdAAAAABAE)

## Fetch-decode-execute
Estas palabras resumen el funcionamiento básico de una CPU. Por ejemplo en la computadora de 16 bits la CPU primero tiene que buscar la dirección de la instrucción en el registro A dictada por el registro pc. Luego la CPU decodifica la instrucción, finalmente la envía para su ejecución a través del registro D. 

## Resumen de las instrucciones

En este ejemplo existen dos tipos de instrucciones: A y C. La instrucción tipo A viene dictada por el registro PC y se encarga de escribir en el registro A la dirección de la memoria en la cual se encuentra la instrucción para que luego el contenido sea mostrado en el registro D. Las instrucciones tipo A tienen su bit más significativo siempre en 0. Por ejemplo la instrucción 0x4000, la cual guarda en el registro A el número 0x4000. Por otro lado la instrucción tipo C está compuesto de tres partes, un encabezado conformado por los tres primeros bits, los cuales siempre estarán en 1. Luego vienen 7 bits que determinan la operación a realizar, siguiendo la forma *destino=operación*. Por ejemplo D=A, que almacena en D la información que se encuentra en el registro A. Finalmente los últimos tres bits se encargan de modificar el flujo del programa, también conocidos como saltos. Si no existiera la posibilidad de modificar el flujo del programa no tendría sentido el uso del registro PC, pues el programa se ejecutaría de manera secuencial. En resumen, el registro C sigue la forma:
*111destino=operación;salto*  