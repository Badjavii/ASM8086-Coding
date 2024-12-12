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
MOV AX, 7   ; AX <- 7
```

En este caso, el dato del operando fuente es el 5, que se almacenará en el registro AX. Ahora AX contiene el valor 5.

## Instrucciones Aritméticas

- **ADD**: Suma el dato del operando fuente al dato del operando destino y almacena el resultado en el destino.

Ejemplo de uso:

```assembly
MOV AX, 2       ; AX <- 2 
ADD AX, 2       ; AX <- AX + 2 = 4
```

En este ejemplo, se transfiere al registro AX el valor 2. Luego, se suma el valor de AX (2) con 2, dando como resultado 4, que se almacena en AX.

- **SUB**: Resta el dato del fuente al dato del destino y almacena el resultado en el destino.

Ejemplo de uso:

```assembly
MOV DX, 3       ; DX <- 3 
SUB DX, 2       ; DX <- DX - 2 = 1
```

Se transfiere al registro DX el valor 3. Luego, se resta 2 al valor de DX (3), dando como resultado 1, que se almacena en DX.

- **MUL**: Multiplica el dato del fuente con el dato del destino y almacena el resultado en el destino.

Ejemplo de uso:

```assembly
MOV BX, 3       ; BX <- 3
MOV AX, 4       ; AX <- 4 
MUL BX          ; AX <- AX * BX
```

Se transfiere al registro BX el valor 3. El resultado de la multiplicación (4 * 3) se almacenará en AX.

- **MUL**: Divide el dato del destino entre el dato del fuente y almacena el cociente en el destino.

Ejemplo de uso:

```assembly
MOV BX, 2       ; BX <- 2
MOV AX, 8       ; AX <- 8
DIV BX          ; AX <- AX / BX
```

Se transfiere al registro BX el valor 3. El resultado de la multiplicación (8 / 2) se almacenará en AX.

- **INC**: Incrementa en 1 el valor del destino.

```assembly
MOV AX, 5       ; AX <- 5
INC AX          ; AX <- AX + 1
```

Se transfiere al registro AX el valor 5. Después de la instrucción INC, AX contendrá 6.

- **DEC**: Decrementa en 1 el valor del destino.

```assembly
MOV DX, 7       ; DX <- 7
INC DX          ; DX <- DX - 1
```

Se transfiere al registro DX el valor 7. Después de la instrucción INC, DX contendrá 6.