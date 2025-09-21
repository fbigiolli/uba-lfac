## Ejercicio 1

### Enunciado

Ejercicio 1. Determinar si los siguientes lenguajes son regulares o no. Para los que sean
regulares, dar un autómata finito que los defina (o explicar cómo puede construirse dicho
autómata). Para los que no lo sean, demostrarlo

### Resolucion

a. {$𝑎^{2𝑛} | 𝑛 ≥ 1$}.

Es regular, se puede dar un automata.

---

b. {$𝑎^𝑛𝑏^𝑛 | 𝑛 ≥ 0$}

No es regular, demostrado en clase sale con $a^pb^p$ tomando $i=0$

--- 

c. {$𝑎^𝑚𝑏^𝑛𝑎^{𝑚+𝑛} | 𝑚, 𝑛 ≥ 1$}

Intuicion: si bien podriamos tener un automata que reconozca $a^mb^n$, para la parte de $a^{n+m}$ necesitariamos de alguna forma recordar cuantas a y b tuvimos para verificar la suma.

Demostremos usando el lema de pumping que el lenguaje no es regular. 

Sea $L=\{a^{m}b^{n}a^{m+n}\mid m,n\ge1\}$.
Supongamos, por contradicción, que $L$ es regular. Sea $p$ la constante del lema de pumping.

$$
s = a^{p} b^{p} a^{2p}\in L \quad(\text{tomando } m=p,n=p).
$$

Por el lema de pumping existe una descomposición $s=xyz$ con $|xy|\le p$ y $|y|\ge1$. Como $|xy|\le p$, el segmento $y$ está totalmente dentro del primer bloque de $a$’s, luego $y=a^{k}$ con $1\le k\le p$.

Tomemos $i=0$. Entonces

$$
s' = xz = a^{p-k} b^{p} a^{2p}.
$$

Si $s'\in L$ existirían $m',n'\ge1$ tales que

$$
s' = a^{m'} b^{n'} a^{m'+n'}.
$$

Comparando bloques obligatoriamente $m'=p-k$ y $n'=p$. Entonces el bloque final debería tener longitud

$$
m'+n'=(p-k)+p=2p-k.
$$

Pero en $s'$ el bloque final tiene longitud $2p$. Como $k\ge1$, $2p\ne 2p-k$. Por tanto no existe tal par $(m',n')$ y concluimos $s'\notin L$. Esto contradice la condición del lema de pumping, de modo que $L$ no puede ser regular.
 
---

d. {$𝜔 ∈ ${$𝑎, 𝑏$}$∗$ | 𝜔 no contiene tres 𝑎es consecutivas}.

Es regular, con 3 estados que cuenten la cant de a consecutivas y un estado trampa alcanza

---

e. {𝜔 ∈ {𝑎, 𝑏}∗ | |𝜔|𝑎 = |𝜔|𝑏}.

Intuicion: no es regular porque para contar la cantidad de ambas necesitamos infinitos estados. Veamoslo por lema de pumping.

Consideramos la palabra $s = a^pb^p$. La demo de aca en adelante es igual a la de la clase.

--- 

f. {𝜔 ∈ {𝑎, 𝑏}∗ | |𝜔|𝑎 ≠ |𝜔|𝑏}.

Este lenguaje es el complemento del item anterior. Como los lenguajes estan cerrados bajo complemento, si un lenguaje es regular su complemento tambien lo es. Pero ya vimos que su complemento no es regular. 

--- 

g. {𝜔 ∈ {𝑎, 𝑏}∗ | |𝜔|𝑎 < |𝜔|𝑏}

No es regular, sale tomando 

$$
a^pb^{p+1}
$$

y haciendo el pumping sobre la cantidad de $a's$ tomando por ejemplo $i = 2$, ya que luego no valdra la desigualdad sobre las cantidades de $a's$ y $b's$

---

h. {𝜔 ∈ {𝑎, 𝑏}∗ | 𝜔 = $𝜔^r$}.

Para que una cadena sea igual a su reverso, se debe leer igual de principio a fin que de fin a principio.

Tomemos la palabra: 

$$
a^pba^p
$$

La palabra pertenece claramente al lenguaje, y cumple con las hipotesis del lema de pumping. 

Luego, como $|xy| < p$ y $y = a^k, k≥1$, necesariamente en y tendremos solamente $a's$. Tomando tanto $i=0$ como $i ≥ 1$ la palabra deja de pertenecer al lenguaje ya que nos queda:

$$
a^{p-k}ba^p
$$

Y como $k ≥1$ el lenguaje no es regular. 

---

i. {𝜔 ∈ {𝑎, 𝑏}∗ | $|𝜔|_𝑎$ es par}

Es un lenguaje regular, podemos dar un AFD con dos estados: cant a's par y cant a's impar. Entramos en el estado cant a's par que es final, por b nos quedamos en el mismo estado y por a cambiamos a cant a's impar, en el cual por a volvemos al estado anterior y por b nos quedamos en el mismo.

---
j. {𝜔 ∈ {𝑎, 𝑏}∗ | ||𝜔|𝑎 − |𝜔|𝑏| ≤ 1}

No es regular, sale muy similar al de cant de $a's$ menor a cant de $b's$, ya que es la misma desigualdad practicamente pero sumando 2. Si planteamos la palabra

$$
a^pb^p
$$

pertenece al lenguaje, y es facil demostrar que no es regular despues eligiendo $i > 2$.

---
k. {𝜔 ∈ {𝑎, 𝑏}∗ | para todo prefijo 𝛾 de 𝜔, ||𝛾|𝑎 − |𝛾|𝑏| ≤ 1}.

Es regular... la idea del automata es ir leyendo de izquierda a derecha la palabra, donde vamos a mantener 4 estados: 1 $a$ de mas, mismas $a's$ que $b's$, 1 $b$ de mas, o palabra no valida (si en algun momento detectamos que tenemos mas de una letra de diferencia, la palabra ya deja de ser aceptada por el automata del lenguaje ya que no cumple para todo prefijo aunque si podria cumplir para alguno.) 

Las transiciones son las que dice el sentido comun, no las voy a escribir

---

l. {𝜔 ∈ {𝑎, 𝑏}∗ | para todo prefijo 𝛾 de 𝜔, ||𝛾|𝑎 − |𝛾|𝑏| ≤ 1, y |𝜔|𝑎 = |𝜔|𝑏}.

Es finito, mismo automata de antes pero aceptando solo cuando tienen la misma cant de $a's$ que de $b's$.

Esto se puede hacer porque la condicion del prefijo nos permite acotar la diferencia que toleramos en la cantidad de letras, cosa que no pasa cuando queremos ver si dos palabras tienen la misma cantidad de letras solamente. Para ese automata deberiamos modelar infinitos estados para captar todas las posibles diferencias, ya que no tenemos forma de saber de antemano a cuanto puede ascender ese numero. En cambio, la condicion del prefijo nos permite rechazar cualquier palabra que difieran sus prefijos en mas de 1.

--- 
m. {𝜔 ∈ {𝑎, 𝑏}∗ | para todo prefijo 𝛾 de 𝜔, |𝛾|𝑎 ≥ |𝛾|𝑏}.

No es regular ya que tendriamos que tener infinitos estados para modelar esa desigualdad, tomando

$$
a^pb^p
$$

Es posible romperlo usando $i = 0$ ya que tendremos una cantidad menor de $a's$ que de $b's$.

---
n. Sea 𝑘 un natural fijo. ℒ𝑘 = {𝜔 ∈ {𝑎, 𝑏}∗ | |𝜔|𝑎 es divisible por 𝑘}

Al estar $k$ fijo es regular. Tenemos $k$ estados donde c/u representa el mod de la division de la cant de $a's$, por $a$ transicionamos $+1$ ese mod y volvemos al $0$ cuando nos pasamos, y por b no hacemos nada en ninguno.

