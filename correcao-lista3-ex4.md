# Lista 3 Ex. 4 2015/2

#### Questão 4:

Construa gramáticas que gerem:

**a) `{ w a^n w | w ∈ {a,b}* e |w| = n }`**

> Resp:
>
> P → a A P A' | b A P B' | M Z  
> A a → a A  
> A b → b A  
> A M → M a  
> M → 𝜆  
>
> Z A → Z a  
> Z B → Z b  
> A' a → a A'  
> A' b → b A'  
> B' a → a B'  
> B' b → b B'  
> Z → 𝜆  

**b) `{ a^n b^m c^k | k = max(n,m) }`**

> Resp:
>
> P → A+ | B+ | 𝜆  
> A+ → a B A+ c | a A+ c  
> B+ → a B B+ c | B B+ c  
> B a → a B  
> B A+ → A+ b  
> B B+ → B+ b  
> A+ → 𝜆  
> B+ → 𝜆  
