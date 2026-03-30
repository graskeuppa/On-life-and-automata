*Microprocessor without Interlocked Pipeline Stages* es una arquitectura de instrucciones. 
Es simple de entender y de optimizar.

---

# Tipos de datos

- word: 32 bits
- doubleword: 64 bits
- float: número de punto flotante
- ascizz: cadenas en ASCII

Los datos se guardan en registros o en memoria, de cualquier modo, MIPS tiene instrucciones para mover datos entre las dos y para realizar operaciones aritméticas y lógicas.

# Operaciones básicas

- add: añade dos valores y guarda el resultado en un registro

```armasm
add $s1, $s0, $zero
# Suma $s0 y $zero y lo guarda en $s1
```

- sub: el dual del anterior

```armasm
sub $s1, $s0, $zero
# Resta $s0 y $zero y lo guarda en $s1
```

- lw (load word): carga una palabra de 4 bytes de memoria a un registro
```armasm
lw $t1, count
# Guarda la palabra *count* en $t1
```

- sw (save word): guarda una palabra de registro en la memoria

```armasm
sw $t1, count
# Guarda el contenido de $t1 en *count*
```


# Control de flujo

- beq (break if equal): Salta a una *etiqueta* si dos registros son iguales; si no lo son, continúa su ejecución
- bne (break if not equal): El dual del anterior

- j (jump): salta a una etiqueta

```armasm
# Compara el registro $t0 y $t1
beq $t0, $t1, etiqueta_igual
add $t2, $t0, $t1 # (Corre si no son ig.)
j end             # Salta al final si no son ig.

etiqueta_igual:
	~~~           # Instrucciones
	
end:
```

- jal (jump and load): salta a una etiqueta y guarda la dirección de retorno en el registro dado
- jr (jump to register): tal como su nombre lo indica
Con estas operaciones se implementan ciclos, condicionales y llamadas a funciones.

---
# Recomendaciones
- Código limpio y legible
- Comentarios explicatorios
- Pruebas profundas
- Sigue buenas prácticas