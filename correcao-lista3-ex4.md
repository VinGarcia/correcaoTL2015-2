# Lista 3 Ex. 4 2015/2

#### Questão 4:

Construa gramáticas que gerem:

**a) `{ w a^n w | w ∈ {a,b}* e |w| = n }`**

**b) `{ a^n b^m c^k | k = max(n,m) }`**

> Resp:
>
> P -> A+ | B+ | 𝜆
> A+ -> a B A+ c | a A+ c
> B+ -> a B B+ c | B B+ c
> B a -> a B
> B A+ -> A+ b
> B B+ -> B+ b
> A+ -> 𝜆
> B+ -> 𝜆
