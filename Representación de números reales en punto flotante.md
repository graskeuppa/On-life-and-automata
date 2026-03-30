¿Cómo es que, una computadora, que pueda únicamente trabajar con números finitos y numerables, usa "números reales"?

Hoy día hacemos uso de la *representación de punto flotante*, que es análoga a la notación científica.
Todo número se escribe de la forma $\pm a \times b^k$ donde $b$ es la base, $a$ es la *mantisa* y $k$ el exponente.

### Formato de presición simple
Los números reales se representan en 4 *bytes* (32 bits).
El primer bit indica el signo de la mantisa siguiendo un esquema similar a lo que se vio en [[Representación binaria de números negativos]].
Los siguientes 8 bits especifican la magnitud de la mantisa normalizada, puesto que hay muchas maneras de representar un número científico, se prefiere que la cifra más significativa esté inmediatamente a la izquierda del punto

**PENDIENTE**