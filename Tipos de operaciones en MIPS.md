[[MIPS]] cuenta con tres tipos de 
operaciones:
## R-Type
Se usan cuando *todos los valores que se usan en la instrucción están en registros*.
Siguen el formato `Op rd, rs, rt`, donde `rs` y `rt` son los registros de donde se sacan los datos y `rd` es donde se guardará el resultado. 

Un ejemplo es `add`.
```armasm
add $s0, $s1, $s2
```
## J-Type
Usadas para *realizar saltos*, permiten manejar valores inmediatos (aquellos con un máximo de 16 bits, son funcionalmente *números constantes* que se escriben directo al código), puesto que las direcciones de memoria ocupan números grandes.
Siguen el formato `Op label`, donde `Op` es la operación y `label` la etiqueta a la que se saltará.

```armasm
j loop
```
## I-Type
Se usan cuando se tiene que *operar con un valor inmediato y un valor en el registro*. 
Siguen el formato `Op rt, IMM(rs)`, donde `rs` es el inmediato y `rt` el registro.

```armasm
addi $t2, $s3, 4
```
