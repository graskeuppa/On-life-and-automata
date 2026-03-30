# Práctica 2 - Preguntas
García Bollás Emiliano
Reyes Ríos Julián Humberto

---
1. En el contexto de las ALUs, explica qué son los: SIMD, MIMD, La Execution Units (EUs) y los Address Generation Units (AGUs)

- SIMD (Single Instruction Multiple Data): Arquitectura en la que únicamente una instrucción controla varios elementos de procesamiento en paralelo sobre datos.
- MIMD (Multiple Instruction Multiple Data): Procesadores diferentes realización instrucciones distintas sobre conjuntos de datos distintos de modo simultáneo.
- Execution Units: Elementos del procesador que efectúan las operaciones. En particular, una ALU es una EU.
- Address Generation Units: Circuitos dedicados a computar direcciones de memoria.

1. ¿Qué es el *Carry-Look-Ahead Adder*? Muestra su diagrama.
- Es un sumador que calcula el acarreo anticipadamente por medio de **lógica combinacional**. Genera los bits de acarreo cuando sus operandos son ambos 1 y los propaga cuando al menos uno de ellos es 1.
![[Pasted image 20260308211945.png]]
Es particularmente útil pues reduce enormemente el tiempo de cálculo

1. Las ALU modernas suelen estar conectadas en *Pipelines*. ¿Qué significa conectar una ALU en *Pipelines*? ¿Cuál es la ventaja y cuál es el riesgo o desafío potencial de hacerlo?
- Conectar a una ALU en *Pipelines* implica dividir una operación compleja en trozos más cortos y sencillos. Es análogo a cómo operan las *líneas de ensamblaje*.
- Como ventajas, permite procesar varias instrucciones a la vez en diferentes etapas, aumentando su velocidad de procesamiento.
- Sin embargo, puede llegar a suceder que se suscite una **condición de carrera** cuando una instrucción requiera del resultado de una instrucción anterior que aún no la completa.