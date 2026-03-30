El [[Cálculo lambda]] es un modelo de cómputo equivalente a los formalismos de Turing, por tanto, es posible hacer lógica con sus funciones. 
$$
\begin{gathered}
T \equiv \lambda x.\lambda y.x\\\\
F \equiv \lambda x.\lambda y.y 
\end{gathered}
$$
Podemo definir $\lnot \lambda b.b\ F\ T$ como el operador lógico *not*.
$$
\begin{gathered}
\lnot T \rightarrow_{\beta} F \\\\
\lnot F \rightarrow_{\beta} T
\end{gathered}
$$
También podemos hacer *and*
$$
\begin{gathered}
\land \equiv \lambda a.\lambda b\ \ b\ F \\\\
\text{Y aplicamos a un ejemplo} \\\\
(\land T) F\\\\
(\lambda b.T \ b\ F)F\\\\
(\lambda x.\lambda y.)F F \\\\
(\lambda y.F)F \rightarrow_{\beta}F
\end{gathered}
$$


