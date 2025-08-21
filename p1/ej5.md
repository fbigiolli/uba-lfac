## Ejercicio 5

### Enunciado
Dado un alfabeto Σ, sean 𝑥, 𝑦 ∈ Σ y 𝛼, 𝛽 ∈ Σ∗. Demostrar que:  
a. |𝑥.(𝑦.𝛼)| = 2 + |𝛼|  
b. |𝛼𝑟| = |𝛼|  
c. |𝛼𝑥𝛽| = |𝑥𝛼𝛽|  
d. |𝛼.𝛼| = 2|𝛼|  
e. (𝛼.𝛽)r = 𝛽r.𝛼r  
f. (𝛼r)r = 𝛼  
g. (𝛼𝑟)𝑛 = (𝛼𝑛)r  
(|𝛼| indica la longitud de la cadena 𝛼).  

### Resolucion
**a. |𝑥.(𝑦.𝛼)| = 2 + |𝛼|**

```
|𝑥.(𝑦.𝛼)| = 2 + |𝛼|
1 + |(𝑦.𝛼)| = 2 + |𝛼|
1 + 1 + |a| = 2 + |𝛼| 
2 + |a| = 2 + |𝛼| 
∴
```

**b. |𝛼𝑟| = |𝛼|**

Por induccion estructural.

#### Caso base
```
a = λ

Luego, por definicion el reverso de λ es λ. Entonces:

|λ| = |λ| ✓
```  
#### Caso recursivo

```
Sea x = ax'

Prop. a demostrar es |xr| = |x|

Como HI tenemos que |x'r| = |x'|

Desarrollando el primer lado de la igualdad tenemos que:
|xr| = |(ax')r| = |x'ra| = |x'r| + 1 =(HI) |x'| + 1

Del otro lado de la igualdad tenemos que:
|x| = |(ax')| = 1 + |x'|

Luego, la igualdad queda:
|x'| + 1 = |x'| + 1 
∴
```

**c. |𝛼𝑥𝛽| = |𝑥𝛼𝛽|**

```
|axb| = |xab|
|axb| = 1 + |ab|
```

Llegado a este punto, lo mas logico parece ser que si podemos demostrar que |ab| = |a| + |b| la demo sale de una... entonces:

Veamoslo por induccion estructural sobre a:

#### Caso base
```
a = λ

|λb| = |b| = 0 + |b| = |λ| + |b|✓
```

#### Caso recursivo

```
Sea a = xa'

Prop a demostrar es |ab| = |a| + |b|

Como HI tenemos que |a'b| = |a'| + |b|

|(xa')b|
= |x(a'b)|
= 1 + |a'b|
=(HI) 1 + |a'| + |b|
= |xa'| + |b|
= |a| + |b|      (que es lo que queriamos demostrar.)
∴
```

Entonces, ahora que sabemos que la propiedad vale podemos usarla para demostrar la prop. inicial:

```
|axb| = 1 + |ab|
|a| + |xb| = 1 + |ab|
|a| + |x| + |b| = 1 + |ab|
|a| + 1 + |b| = 1 + |ab|
1 + |ab| = 1 + |ab|
∴
```

**d. |𝛼.𝛼| = 2|𝛼|**

Usando la prop. demostrada anteriormente sale trivial:

```
|aa| = 2|a|
|a| + |a| = 2|a|
2|a| = 2|a|
∴
```

**e. (𝛼.𝛽)r = 𝛽r.𝛼**

TODO...