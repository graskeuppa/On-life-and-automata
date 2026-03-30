[[MIPS]] puede interactura directamente con el sistema operativo usando *llamadas al sistema*: funciones especiales que provee el OS para dejar a un programa tomar entradas y salidas, locaciones de memoria y creación de procesos. Las más comunes incluyen:
- `syscall`: dado el valor en el registro `\$v0`, realiza la llamada al sistema guardada en el registro; es bastante versátil, puesto que el resultado obtenido será diferente si lo que está guardado en `\$v0`
- `li`: carga un valor inmediato un registro
- `la`: carga la dirección de una etiqueta al registro
Son clave!