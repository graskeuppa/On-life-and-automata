Se trata de una [[máquina de Turing]] que decide si $\forall n$, $n$ es la codificación de un una $\mathcal{M}$ sin círculos (como visto en [[circularidad]]).

El problema comienza suponiendo la existencia de una $\mathcal{M}_{D}$ universal que no tiene círculos y que puede decidir **CIRC?** $\forall n$.

Como toda máquina tiene una única *Standard Description (SD)* que corresponde a un único *Descriptor Number (DN)* y $\mathcal{M}_{D}$ puede simular a cualquier otra máquina (por ser universal), se plantea lo siguiente:

Se construye una nueva máquina $\mathcal{M}_{H}$ libre de círculos tal que usa a $\mathcal{M}_{D}$ como una subrutina:
- Se enumeran $\mathbb{N}=1,2,3,\dots$
- Cada $n$ se convierte en su respectivo *SD*
- Se usa $\mathcal{M}_{D}$ para ver si esa *SD* no tiene círculos
- Si no los tiene:
	- Será la $R-$ésima máquina satisfactoria
	- Simulará esa máquina usando la niversa
	- Imprimirá $0$ o $1$ como $R-$ésima salida para decir si cumple o no.
- Siguen infinitamente.

Como toda máquina tiene una *SD*, $\mathcal{M}_{H}$ eventualmente llegará al $n$ que corresponde a su misma *SD*. Cuando esto suceda, se simulará a sí misma y repetirá el proceso hasta encontrarse otra vez con su *SD*, así hasta el infinito.

Esto contradice que $\mathcal{M}_{H}$ sea no circular. Ni $\mathcal{M}_{H}$ ni $\mathcal{M}_{D}$ existen por lo expuesto arriba, resultando así en que **CIRC?** es incomputable.