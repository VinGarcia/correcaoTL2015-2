# Revisão exercício 11 lista 3

Olá Gente, como combinado em sala segue a resolução do exercício 11 da lista de exercícios 3 de Teoria de Linguagens 2015/2.

#### Questão 11:

Para cada PD abaixo, mostre que o mesmo é decidível ou que não é:

**a) Dadas duas GLCs `G1` e `G2`, determinar se `L(G1) ∩ L(G2)` é finita.**

> R: Esse problema é indecidível. O motivo é que o Problema da Correspondencia de Post (PCP) pode ser reduzido à ele.

A resposta acima **_deve_** bastar em uma prova, vou checar com o professor e envio outro e-mail com a confirmação.

Uma explicação detalhada da redução segue abaixo para vocês entenderem direitinho
(essa mesma redução pode ser usada na questão 10.d. e na questão 11.c,
por isso achei legal explicar ela em detalhes)

---

A redução é detalhada a seguir:

**Descrição PCP:**

O problema de post é o problema de dados duas listas de palavras A e B, onde:

- `A = a1,a2,a3,...,an`
- `B = b1,b2,b3,...,bn`

Determinar uma sequencia de indices do tipo:

- `I = di,dj,...,dk`

Tal que a concatenação das palavras de A com os respectivos indices é igual à concatenação das palavras de B também na mesma sequencia.

Ou seja:

- `ai aj ... ak = bi bj ... bk`

Um exemplo seria do tipo:

- `A = 11, 111, 100`
- `B = 111, 11, 001`

Onde a resposta seria:

- `I = 1, 3, 2`

Ou seja:

|      | (1) | (3) | (2) |
|------|-----|-----|-----|
| wa = | 11  | 100 | 111 |
| wb = | 111 | 001 | 11  |

Tal que wa = wb.

Note também que os indices em `I` podem ser omitidos ou aparecer varias vezes na solução.

Logo no caso acima `I2 = 1, 3, 2, 1, 3, 2` também é solução havendo dessa forma infinitas soluções:

- `I3 = 1, 3, 2, 1, 3, 2, 1, 3, 2`
- `I4 = 1, 3, 2, 1, 3, 2, 1, 3, 2, 1, 3, 2`
- `I5 = 1, 3, 2, 1, 3, 2, 1, 3, 2, 1, 3, 2, 1, 3, 2`
- `In = 1, 3, 2, 1, 3, 2, 1, 3, 2, 1, 3, 2, 1, 3, 2, 1, 3, 2, ...`

**Reduzindo o PCP ao problema da intercessão finita de gramáticas:**

Para reduzir o PCP ao problema da intercessão finita de gramáticas
basta utilizar uma formulação onde A e B vão se tornar Ga e Gb,
de forma que se a intercessão entre Ga e Gb for:

- Infinita é porque existe solução para o PCP.

- Finita ou vazia é porque não existe uma solução para o PCP.

**Gerando a gramática:**

Para gerar Ga e Gb vamos utilizar a lista A e a lista B como os terminais da gramática Ga e Gb respectivamente.
E para ambas as gramáticas vamos criar novos simbolos terminais t1,...,tn = T tal que |T| = |A| = |B|.

E agora vamos definir a gramática A e B como:

- `Ga: Pa -> ai P ti | ai ti`

- `Gb: Pb -> bi P ti | bi ti`

as palavras formadas serão na forma:

- `wa' = a1 a3 a2 t2 t3 t1 => 11 100 111 t2 t3 t1`

- `wb' = b1 b3 b2 t2 t3 t1 => 111 001 11 t2 t3 t1`

O exemplo acima é uma intercessão das duas gramáticas.

Note que os terminais t1,...,tn são necessários para garantir que intercessões
só irão ocorrer quando a ordem dos indices for a mesma nas duas gramáticas
como é exigido pelo problema do PCP.

**Mas o problema não é encontrar intercessão é descobrir se é finita...**

Agora observe que no PCP se existe uma solução existem infinitas soluções:

Logo se `wa = a1, a2, a3` é solução, então:

- `wa2 = a1, a2, a3, a1, a2, a3` também é solução.

O mesmo se aplica à gramática: Se há uma intercessão, por exemplo wa',
existem infinitas intercessões, basta repetir as substrings na mesma ordem.

Dessa forma o problema:

- L(Ga) intersec L(Gb) ser finito ou não

É reduzível a partir do Problema da Correspondencia de Post. E como o PCP
não é decidível o problema da intercessão finita de gramáticas também não é.

---

**b) Dada uma LLC L, determinar se o complemento de L é finita.**

> R: Esse não consegui fazer sozinho, vou checar com o professor e coloco aqui.

**c) Dadas uma GR `Gr` e uma GLC `GL`, determinar se `L(Gr) ∩ L(GL) = ∅`.**

> R: O PCP pode ser reduzido à este problema de forma quase identica a demonstrada no exercício 11a.

**d) Dadas uma linguagem regular `R` e uma LLC `L`, determinar se `R ⊆ L`.**

> R: O problema indecidível de se mostrar que `L = Σ∗`, pode ser
> reduzido a este produzindo-se uma expressão regular r que denote Σ∗
> e uma GLC G que gere L, pois: L = Σ∗ sse Σ∗ ⊆ L.

Solução retirada da questão 4b da prova 3 de TL
do semestre 2015/2 disponível [aqui][prova].

[prova]: http://homepages.dcc.ufmg.br/~nvieira/cursos/tl/a14s2/p3s.pdf

Att, Vinícius Garcia.



