Para cuando te encuentras con expresiones del tipo
$$
(\lambda x\lambda y.xy)(\lambda y.yx)
$$
Si lo $\beta-$reducimos, como se ve en [[Beta reducción]], 
$$
(\lambda y.xy)[x:=\lambda y.yx]
$$
$$
\lambda y.(\lambda y.yx)y
$$
Esta expresión es confusa, así que buscamos renombrar variables para eliminar ambigüedad.
$$
(\lambda x\lambda y.xy)(\lambda y.yx)  =_{\alpha}(\lambda w---)
$$
