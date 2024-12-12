# Instrucciones Básicas del Intel 8086

## Introducción

El ensamblador del procesador Intel 8086 consta de instrucciones básicas que se clasifican de la siguiente manera:

- **Instrucciones de Transferencia de Datos**
- **Instrucciones Aritméticas** (Adición, Substracción, Multiplicación, etc.)
- **Instrucciones Lógicas** (Conjunción, Disyunción, etc.)
- **Instrucciones de Control de Programa** (Saltos, Bucles, Llamadas a procedimientos, etc.)

Estas no son todas las instrucciones que tiene el ensamblador 8086. Existen otras instrucciones (como las de desplazamiento y las de E/S) que no se mencionarán en este apartado.

Este apartado del repositorio se dedica a dar una introducción básica para que jóvenes desarrolladores puedan familiarizarse cómodamente con el entorno de desarrollo.

## Instrucciones de Transferencia de Datos

Los datos utilizados en un programa se almacenan en los registros del procesador. El 8086 dispone de 4 registros principales para datos: AX, BX, CX y DX. Estos registros se denominan **Registros de Datos** y tienen una capacidad de 16 bits cada uno.

Para cualquier programa en ensamblador, es necesario usar las instrucciones de transferencia de datos y trabajar con los registros de datos para operar o almacenar valores.

La instrucción **MOV** es la más importante y la más usada. Esta instrucción usa dos operandos separados por una coma. El primer operando se denomina *destino* y el segundo *fuente*. La instrucción transfiere al *destino* una copia del dato almacenado en el *fuente*.

    Ejemplo de uso:

```assembly
MOV AX, 5   ; AX <- 5
```

En este caso, el dato del operando fuente es el 5, que se almacenará en el registro AX. Ahora AX contiene el valor 5.

## Instrucciones Aritméticas

- **ADD**: Realiza la suma de dos operandos denominados respectivamente *destino* y *fuente*. El dato del operando *fuente* se suma con el dato del operando *destino* y el resultado de esa operación se guarda en el operando *destino* eliminandose el dato anterior y permaneciendo el nuevo dato.

Como el resultado del operación se almacena dentro de uno de los operandos, se concluye que el operando *destino* debe ser un registro de datos.

    Ejemplo de uso:

    MOV AX, 2           ; AX <- 2
    ADD AX, 2           ; AX <- AX + 2 = 2 + 2

    Se le transfiere al registro AX el valor de 2. Seguido se hace la suma del dato almacenado en AX (el cual se sabe que es 2) y el dato 2, es decir, la suma de 2+2 que da como resultado 4. El 4 se almacenará en el registro AX automaticamente.

- **SUB**: Realiza la resta de dos operandos denominados respectivamente *destino* y *fuente*. El dato del operando *fuente* corresponde al sustraendo de la resta mientras que el dato del operando *destino* corresponde al minuendo. El resultado de esa operación se guarda en el operando *destino* eliminandose el dato anterior y permaneciendo el nuevo dato.

Como el resultado del operación se almacena dentro de uno de los operandos, se concluye que el operando *destino* debe ser un registro de datos.

    Ejemplo de uso:

    MOV DX, 3           ; DX <- 3
    SUB DX, 2           ; DX <- DX - 2 = 3 - 2

    Se le transfiere al registro DX el valor de 3. Seguido se hace la resta del dato almacenado en DX (el cual se sabe que es 3) y el dato 2, es decir, la resta de 3-2 que da como resultado 1. El 1 se almacenará en el registro DX automaticamente.

- **MUL**: Realiza la multiplicación de dos operandos denominados respectivamente *destino* y *fuente*. El dato del operando *fuente* se multiplica con el dato del operando *destino* y el resultado de esa operación se guarda en el operando *destino* eliminandose el dato anterior y permaneciendo el nuevo dato.

Como el resultado del operación se almacena dentro de uno de los operandos, se concluye que el operando *destino* debe ser un registro de datos.