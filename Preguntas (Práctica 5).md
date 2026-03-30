# Preguntas (P5)
- Emiliano Bollás
---
> [!example|noicon] 1. ¿Qué hacen las instrucciones de tipo FR y de tipo FI? Da algunos ejemplos de instrucciones de este tipo y menciona porqué están separadas de las otras tres principales.


Las instrucciones FR (*Floating-point Register*) y FI (*Floating-point Immediate*) están dedicadas a operaciones de aritmética de punto flotante. Ejemplos de ambas incluyen:
- FR: `add.s`, que es la **suma de precisión simple**; o `mul.d`, la **multiplicación de precisión doble**.
- FI: `lwc1`, que **carga una palabra al coprocesador 1** y su dual `swc1`.

No se agrupan con las instrucciones de tipo R, I y J porque los procesadores *MIPS* tienen un procesador principal que se encarga únicamente de tratar números enteros y un *Coprocesador 1* que hace lo mismo, pero para decimales; como hay una separación en hardware, sus instrucciones siguen la misma organización.

> [!example|noicon] 2. ¿Qué es la *Portabilidad de Arquitecturas (Cross-Architecture Porting)*?

Se trata en el proceso de adaptación de un programa que se escribió pensando en un tipo de procesador a uno para otra arquitectura, ya sea por medio de *adaptaciones* o *recompilaciones* para que pueda ejecutarse nativamente en la nueva arquitectura. 

Pensando en ensamblador, la reescritura es funcionalmente completa por diferencias en el conjunto de instrucciones, manejo de registros y demás reglas de la arquitectura. 

> [!example|noicon] 3. ¿Qué son las arquitecturas x86 y x64?, ¿tienen un único lenguaje ensamblador?

Son las familias de procesadores más comunes del siglo. x86 es una arquitectura de 32 bits y x64 de 64 bits.

No tienen un único lenguaje ensamblador, pese a que el código máquina es idéntico, los separamos en dos grandes *corpus* de sintáxis:
- Sintaxis Intel: Que se usa en Windows
- Sintaxis AT&T: Usada en sistemas tipo UNIX


> [!example|noicon] 4. En el contexto de los lenguajes de ensamblador, ¿qué es *NASM*?, ¿qué es *MASM*?

Colgándonos un poco de la pregunta anterior, son ensambladores para las arquitecturas x86 y x64 respectivamente.
- MASM (*Microsoft Macro Assembler*): como su nombre indica, es de Microsoft y está orientado a hacer programas profundamente integrados con Windows.
- NASM (*Netwide Assembler*): Ensamblador *open-source* multiplataforma.

---
