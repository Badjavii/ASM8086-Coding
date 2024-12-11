# Instrucciones Basicas del Intel 8086

El ensamblador del procesador Intel 8086 consta de intrucciones basicas que son clasificadas de la siguiente forma:

- Instrucciones de **Transferencia de datos**.
- Instrucciones **Aritmeticas** (Adición, Substracción, Multiplicación, etc).
- Instrucciones **Logicas** ("Y", "O", etc).
- Instrucciones de **Control de Programa** (Saltos, Bucles, Llamadas a procedimientos, etc).

![This is a comment]Estas **no** son todas las instrucciones que tiene el ensamblador 8086. Existen otras instrucciones (como las de desplazamiento y las de E/S) que no se mencionaran en este apartado.

Este apartado del repositorio se dedicará a dar una introducción basica para que jovenes desarrolladores puedan familiarizarse comodamente al entorno de desarrollo.

## Instrucciones de Transferencia de Datos (IMPORTANTE)

Los datos usados en un programa se almacenan en los registros del procesador. Recordemos que el 8086 dispone 4 registros que son usados para datos que son el AX, BX, CX, DX. Esos registros se denominan `Registros de Datos` y tienen una capacidad de 16 bits cada uno.

Para cualquier programa en ensamblador será necesario hacer uso de las instrucciones de transferencia de datos y a la vez trabajar con los registros de datos para situaciones en las que tengamos que operar un valor o guardar un valor. 

## Instrucciones Aritméticas

- **ADD**: Realiza la suma 