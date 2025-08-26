## Ejercicio 9

### Enunciado

Determinar el complemento de los siguientes lenguajes, considerando los alfabe-
tos indicados en cada caso.

a. ℒ = Λ para Σ = {𝑎, 𝑏}

b. ℒ = {𝜆, 𝑎} para Σ = {𝑎} y Σ = {𝑎, 𝑏}

c. ℒ = {𝑏𝛼 | 𝛼 ∈ {𝑎, 𝑏}∗} para Σ = {𝑎, 𝑏}

d. ℒ = {𝑎2𝑛 | 𝑛 ≥ 0} para Σ = {𝑎} y Σ = {𝑎, 𝑏}

e. ℒ = {𝛼1𝑏𝛼2 | 𝛼1, 𝛼2 ∈ {𝑎, 𝑏}∗ ∧ |𝛼1| > |𝛼2|} para Σ = {𝑎, 𝑏}

### Resolucion

a. {a,b,ab,ba,...}

b. para {a} es {a}* \ {λ,a}, para {a,b} es {a,b}* \ {λ, a}

c. {w ∈ {a,b}* | w = λ ∨ w = a.α con α ∈ {a,b}*} (o sea, las cadenas que NO empiezan con una b)

d. para {a} es {a^2n+1 | n ≥ 0 } (o sea, long impar), para {a,b} es { w ∈ {a,b}* | w contiene al menos una b ∨ w = a^2k+1, k ≥ 0}

e. todo