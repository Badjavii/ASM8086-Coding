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

## Instrucciones Lógicas

- **AND**: Realiza una conjunción lógica bit a bit entre el operando fuente y el operando destino, almacenando el resultado en el destino.

```assembly
MOV AX, 5       ; AX <- 0101b 
AND AX, 3       ; AX <- AX & 0011b = 0001b
```

En este ejemplo, 0101b (5 en decimal) se conjuga lógicamente con 0011b (3 en decimal), dando como resultado 0001b (1 en decimal), que se almacena en AX.

- **OR**: Realiza una disyunción lógica bit a bit entre el operando fuente y el operando destino, almacenando el resultado en el destino.

```assembly
MOV AX, 5       ; AX <- 0101b 
OR AX, 3        ; AX <- AX | 0011b = 0111b
```

En este ejemplo, 0101b (5 en decimal) se disyunta lógicamente con 0011b (3 en decimal), dando como resultado 0111b (7 en decimal), que se almacena en AX.

- **CMP**: Compara el operando fuente con el operando destino restando el valor del fuente al del destino. Los resultados de la comparación afectan las banderas de la CPU, pero no almacenan el resultado de la resta.

```assembly
MOV AX, 5       ; AX <- 5 
CMP AX, 3       ; AX - 3 -> afecta las banderas
```

En este ejemplo, se compara el valor de AX (5) con 3. Esto afectará las banderas de la CPU como ZF (Zero Flag), CF (Carry Flag), SF (Sign Flag) y OF (Overflow Flag), pero el valor de AX permanecerá sin cambios.

## Instrucciones de Control de Programas

- **JMP**: Realiza un salto incondicional a una dirección específica.

Ejemplo de uso:

```assembly
JMP etiqueta   ; Salta a la instrucción en "etiqueta"
```

- **JE/JZ**: Salta a una dirección específica si el resultado de la comparación anterior es igual a cero (Zero Flag = 1).

Ejemplo de uso:

```assembly
CMP AX, 0
JE etiqueta   ; Salta a la instrucción en "etiqueta" si AX es igual a 0
```

- **JNE/JNZ**: Salta a una dirección específica si el resultado de la comparación anterior no es igual a cero (Zero Flag = 0).

Ejemplo de uso:

```assembly
CMP AX, 1
JNE etiqueta   ; Salta a la instrucción en "etiqueta" si AX no es igual a 1
```

- **JG/JNLE**: Salta a una dirección específica si el resultado de la comparación anterior es mayor (SF = OF y ZF = 0).

Ejemplo de uso:

```assembly
CMP AX, BX
JG etiqueta   ; Salta a la instrucción en "etiqueta" si AX es mayor que BX
```

- **JL/JNGE**: Salta a una dirección específica si el resultado de la comparación anterior es menor (SF ≠ OF).

Ejemplo de uso:

```assembly
CMP AX, BX
JL etiqueta   ; Salta a la instrucción en "etiqueta" si AX es menor que BX
```

- **JGE/JNL**: Salta a una dirección específica si el resultado de la comparación anterior es mayor o igual (SF = OF).

Ejemplo de uso:

```assembly
CMP AX, BX
JGE etiqueta   ; Salta a la instrucción en "etiqueta" si AX es mayor o igual a BX
```

- **JLE/JNG**: Salta a una dirección específica si el resultado de la comparación anterior es menor o igual (SF ≠ OF o ZF = 1).

Ejemplo de uso:

```assembly
CMP AX, BX
JLE etiqueta   ; Salta a la instrucción en "etiqueta" si AX es menor o igual a BX
```

- **LOOP**: Este bucle se ejecuta mientras el registro CX sea distinto de 0. Decrementa CX en 1 cada vez y salta a la dirección especificada si CX no es igual a 0. Útil para repetir un bloque de código un número determinado de veces.

Ejemplo de uso:

```assembly
MOV CX, 100
COMIENZO: 
; código del bucle 
LOOP COMIENZO           ; Este bucle se repite 100 veces
```

- **LOOPNE/LOOPNZ**: Este bucle se ejecuta mientras el registro CX sea distinto de 0 y la bandera de cero (ZF) sea igual a 0. Útil para bucles que requieren una condición adicional para romperse.

Ejemplo de uso:

```assembly
MOV CX, 100 
COMIENZO: 
; código del bucle 
LOOPNZ COMIENZO         ; Este bucle se repite mientras CX ≠ 0 y ZF = 0
```

- **LOOPE/LOOPZ**: Este bucle se ejecuta mientras el registro CX sea distinto de 0 y la bandera de cero (ZF) sea igual a 1. Similar al anterior, pero con una condición diferente.

Ejemplo de uso:

```assembly
MOV CX, 100 
COMIENZO: 
; código del bucle 
LOOPZ COMIENZO          ; Este bucle se repite mientras CX ≠ 0 y ZF = 1
```

- **JCXZ**: Realiza un salto incondicional si el registro CX es igual a 0. Útil para verificar la terminación de un bucle antes de ejecutarlo.

Ejemplo de uso:

```assembly
JCXZ etiqueta           ; Salta a "etiqueta" si CX = 0
```
