---
title: Operações e funções intrínsecas no QDK
description: Conheça as operações e funções intrínsecas no QDK, incluindo funções clássicas e operações unitárias, de rotação e medição.
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 283504a5f5635a4996c804e514a6f52eb4966d22
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868445"
---
# <a name="the-prelude"></a>O Prelúdio #

O Q# compilador e as máquinas-alvo incluídas no Kit de Desenvolvimento Quântico fornecem um conjunto de funções e operações intrínsecas que podem ser usadas ao escrever programas quânticos em Q# .

## <a name="intrinsic-operations-and-functions"></a>Operações e Funções Intrínsecas ##

As operações intrínsecas definidas na biblioteca padrão enquadram-se aproximadamente numa das várias categorias:

- Funções clássicas essenciais, recolhidas no espaço de <xref:microsoft.quantum.core> nomes.
- Operações que representam unitários compostos por [clifford e portões $T$](xref:microsoft.quantum.concepts.qubit).
- Operações que representam rotações sobre vários operadores.
- Operações implementando medições.

Uma vez que o conjunto de portas Clifford + $T$ é [universal](xref:microsoft.quantum.concepts.multiple-qubits) para computação quântica, estas operações são suficientes para implementar aproximadamente qualquer algoritmo quântico dentro de um erro insignificantemente pequeno.
Ao fornecer rotações também, Q# permite que o programador trabalhe dentro da única biblioteca unitária de qubit e cnot gate. Esta biblioteca é muito mais fácil de pensar porque não requer que o programador expresse diretamente a decomposição Clifford + $T$ e porque existem métodos altamente eficientes para compilar unidades de qubit únicas em clifford e portões de $T$ (ver [aqui](xref:microsoft.quantum.more-information) para mais informações).

Sempre que possível, as operações definidas no prelúdio que atuam sobre os qubits permitem a aplicação da `Controlled` variante, de modo a que a máquina-alvo efetue a decomposição adequada.

Muitas das funções e operações definidas nesta parte do prelúdio estão no espaço de nomes, de tal forma que a maioria dos @"microsoft.quantum.intrinsic" Q# ficheiros de origem terá uma `open Microsoft.Quantum.Intrinsic;` diretiva imediatamente após a declaração inicial do espaço de nome.
O <xref:microsoft.quantum.core> espaço de nome é aberto automaticamente, de modo que as funções como podem ser <xref:microsoft.quantum.core.length> usadas sem qualquer `open` declaração.

### <a name="common-single-qubit-unitary-operations"></a>Operações unitárias comuns de um só qubit ###

O prelúdio também define muitas operações comuns [de um único qubit.](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)
Todas estas operações permitem tanto os `Controlled` `Adjoint` functores como os funtores.

#### <a name="pauli-operators"></a>Operadores Pauli ####

A <xref:microsoft.quantum.intrinsic.x> operação implementa o operador pauli $X$.
Isto às vezes também é conhecido como o `NOT` portão.
Tem `(Qubit => Unit is Adj + Ctl)` assinatura.
Corresponde ao monobit unitário:

\start{equation} \start{bmatrix} 0 & 1 \\ \\ % FIXME: isto utiliza atualmente o hack quadwhack.
1 & 0 \end{bmatrix} \end{equação}

A <xref:microsoft.quantum.intrinsic.y> operação implementa o operador pauli $Y$.
Tem `(Qubit => Unit is Adj + Ctl)` assinatura.
Corresponde ao monobit unitário:

\start{equation} \start{bmatrix} 0 & -i \\ \\ % FIXME: isto utiliza atualmente o hack quadwhack.
i & 0 \end{bmatrix} \end{equação}

A <xref:microsoft.quantum.intrinsic.z> operação implementa o operador pauli $Z$.
Tem `(Qubit => Unit is Adj + Ctl)` assinatura.
Corresponde ao monobit unitário:

\start{equation} \start{bmatrix} 1 & 0 \\ \\ % FIXME: isto utiliza atualmente o hack quadwhack.
0 & -1 \end{bmatrix} \end{equação}

Abaixo vemos estas transformações mapeadas para a [esfera bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (o eixo de rotação em cada caso é realçado vermelho):

![Operações de Pauli mapeadas na esfera bloch](~/media/prelude_pauliBloch.png)

É importante notar que a aplicação do mesmo portão Pauli duas vezes ao mesmo qubit cancela a operação (porque já realizou uma rotação completa de 2π (360°) sobre a superfície para a Esfera bloch, chegando assim ao ponto de partida). Isto leva-nos à seguinte identidade:

$$ X^2=Y^2=Z^2=\\boldone $$

Isto pode ser visualizado na esfera bloch:

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>Outros Cliffords Single-Qubit ####

A <xref:microsoft.quantum.intrinsic.h> operação implementa o portão Hadamard.
Isto intermuta os eixos Pauli $X$ e $Z$ do qubit alvo, de tal forma que $H\ket {0} = \ket{+} \mathrel{:=} (\ket {0} + \ket) {1} / \sqrt {2} $ e $H\ket{+} = \ket {0} $.
Tem assinatura `(Qubit => Unit is Adj + Ctl)` , e corresponde ao único qubit unitário:

\start{equation} \frac {1} {\sqrt {2} } \start{bmatrix} 1 & 1 \\ \\ % FIXME: isto utiliza atualmente o hack quadwhack.
1 & -1 \end{bmatrix} \end{equação}

O portão Hadamard é particularmente importante, pois pode ser usado para criar uma superposição dos estados $\ket {0} $ e $\ket$ {1} . Na representação da esfera bloch, é mais fácil pensar nisto como uma rotação de $\ket{\psi}$ em torno do eixo x por $\pi$ radians ($180^\circ$) seguido por uma rotação (no sentido horário) em torno do eixo y por $\pi/2$ radians ($90^\circ$):

![Operação Hadamard mapeada na esfera bloch](~/media/prelude_hadamardBloch.png)

A <xref:microsoft.quantum.intrinsic.s> operação implementa o portão de fase $S$.
Esta é a raiz quadrada da operação Pauli $Z$.
Ou seja, $S^2 = Z$.
Tem assinatura `(Qubit => Unit is Adj + Ctl)` , e corresponde ao único qubit unitário:

\start{equation} \start{bmatrix} 1 & 0 \\ \\ % FIXME: isto utiliza atualmente o hack quadwhack.
0 & i \end{bmatrix} \end{equação}

#### <a name="rotations"></a>Rotações ####

Além das operações de Pauli e Clifford acima, o Q# prelúdio fornece uma variedade de formas de expressar rotações.
Como descrito em [operações de um único qubit,](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)a capacidade de rotação é fundamental para algoritmos quânticos.

Começamos por recordar que podemos expressar qualquer operação de um único qubit utilizando os portões $H$ e $T$, onde $H$ é a operação Hadamard, e onde \start{equação} T \mathrel{:=} \start{bmatrix} 1 & 0 \\ \\ % FIXME: isto atualmente utiliza o quad back whack hack.
0 & e^{i \pi / 4} \end{bmatrix} \end{equação} Esta é a raiz quadrada da <xref:microsoft.quantum.intrinsic.s> operação, de tal forma que $T^2 = S$.
O portão $T$ é, por sua vez, implementado pela <xref:microsoft.quantum.intrinsic.t> operação, e tem `(Qubit => Unit is Adj + Ctl)` assinatura, indicando que se trata de uma operação unitária num único qubit.

Embora isto seja, em princípio, suficiente para descrever qualquer operação arbitrária de um único qubit, as diferentes máquinas-alvo podem ter representações mais eficientes para rotações sobre os operadores de Pauli, de modo a que o prelúdio inclua uma variedade de formas de expressar convienentemente tais rotações.
O mais básico destes é a <xref:microsoft.quantum.intrinsic.r> operação, que implementa uma rotação em torno de um eixo Pauli especificado, \start{equação} R(\sigma, \phi) \mathrel{:=} \exp(i\phi \sigma / 2), \end{equação} onde $\sigma$ é um operador Pauli, $\phi$ é um ângulo, e onde $\exp$ representa a matriz expoente.
Tem assinatura `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` , onde as duas primeiras partes da entrada representam os argumentos clássicos $\sigma$ e $\phi$ necessários para especificar o operador unitário $R(\sigma, \phi)$.
Podemos aplicar parcialmente $\sigma$ e $\phi$ para obter uma operação cujo tipo é o de um único qubit unitário.
Por exemplo, `R(PauliZ, PI() / 4, _)` tem tipo `(Qubit => Unit is Adj + Ctl)` .

> [!NOTE]
> A <xref:microsoft.quantum.intrinsic.r> operação divide o ângulo de entrada por 2 e multiplica-o por -1.
> Para $Z dólares rotações, isto significa que o $\ket {0} $ eigenstate é rodado por $-\phi / 2$ e o $\ket {1} $ eigenstate é rodado por $\phi / 2$, de modo que o $\ket {1} $ eigenstate é rodado por $\phi$ em relação ao $\ket {0} $ eigenstate.
>
> Isto significa, em particular, que `T` e `R(PauliZ, PI() / 8, _)` diferem apenas por uma [fase global](xref:microsoft.quantum.glossary#global-phase)irrelevante.
> Por esta razão, $T$ é por vezes conhecido como o $\frac{\pi} {8} $-gate.
>
> Note também que rodar em torno `PauliI` simplesmente aplica uma fase global de $\phi / 2$. Embora tais fases sejam irrelevantes, como [argumentam os documentos conceptuais,](xref:microsoft.quantum.concepts.qubit)são relevantes para `PauliI` rotações controladas.

Dentro de algoritmos quânticos, é frequentemente útil expressar rotações como frações dyadic, de modo que $\phi = \pi k / 2^n$ para alguns $k \in \mathbb{Z}$ e $n \in \mathbb{N}$.
A <xref:microsoft.quantum.intrinsic.rfrac> operação implementa uma rotação em torno de um eixo Pauli especificado usando esta convenção.
Difere da medida em que o ângulo de <xref:microsoft.quantum.intrinsic.r> rotação é especificado como duas entradas do `Int` tipo, interpretadas como uma fração diádica.
Assim, `RFrac` tem `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` assinatura.
Implementa o monobit unitário $\exp(i\pi k \sigma / 2^n)$, onde $\sigma$ é a matriz Pauli correspondente ao primeiro argumento, $k$ é o segundo argumento, e $n$ é o terceiro argumento.
`RFrac(_,k,n,_)`é o mesmo `R(_,-πk/2^n,_)` que; note que o ângulo é *o negativo* da fração.

A <xref:microsoft.quantum.intrinsic.rx> operação implementa uma rotação em torno do eixo Pauli $X$.
Tem `((Double, Qubit) => Unit is Adj + Ctl)` assinatura.
`Rx(_, _)`é o mesmo `R(PauliX, _, _)` que.

A <xref:microsoft.quantum.intrinsic.ry> operação implementa uma rotação em torno do eixo Pauli $Y$.
Tem `((Double, Qubit) => Unit is Adj + Ctl)` assinatura.
`Ry(_, _)`é o mesmo `R(PauliY,_ , _)` que.

A <xref:microsoft.quantum.intrinsic.rz> operação implementa uma rotação em torno do eixo Pauli $Z$.
Tem `((Double, Qubit) => Unit is Adj + Ctl)` assinatura.
`Rz(_, _)`é o mesmo `R(PauliZ, _, _)` que.

A <xref:microsoft.quantum.intrinsic.r1> operação implementa uma rotação pelo valor dado em torno de $\ket {1} $, o $-1$ eigenstate de $Z$.
Tem `((Double, Qubit) => Unit is Adj + Ctl)` assinatura.
`R1(phi,_)`é o mesmo `R(PauliZ,phi,_)` que seguido `R(PauliI,-phi,_)` por.

A <xref:microsoft.quantum.intrinsic.r1frac> operação implementa uma rotação fracionária pela quantidade dada em torno do estado de Z=1.
Tem `((Int,Int, Qubit) => Unit is Adj + Ctl)` assinatura.
`R1Frac(k,n,_)`é o mesmo `RFrac(PauliZ,-k.n+1,_)` que seguido `RFrac(PauliI,k,n+1,_)` por.

Um exemplo de uma operação de rotação (em torno do eixo Pauli $Z$, neste caso) mapeada na esfera bloch é mostrado abaixo:

![Operação de rotação mapeada na esfera bloch](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>Operações Multi-Qubit ####

Além das operações de um único qubit acima, o prelúdio também define várias operações multi-qubit.

Primeiro, a <xref:microsoft.quantum.intrinsic.cnot> operação executa um portão controlado padrão, `NOT` \start{equation} \operatorname{CNOT} \mathrel{:=} \start{bmatrix} 1 & 0 & 0 & \\ \\ 0 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & \\ \\ 10 & 0 & 1 & 0 \end{bmatrix}.
\end{equation} Tem `((Qubit, Qubit) => Unit is Adj + Ctl)` assinatura, representando que $\operatorname{CNOT}$ age unitariamente em dois qubits individuais.
`CNOT(q1, q2)`é o mesmo `(Controlled X)([q1], q2)` que.
Uma vez que o `Controlled` functor permite controlar um registo, usamos a matriz literal `[q1]` para indicar que queremos apenas um controlo.

A <xref:microsoft.quantum.intrinsic.ccnot> operação executa o portão NÃO duplamente controlado, por vezes também conhecido como portão Toffoli.
Tem `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` assinatura.
`CCNOT(q1, q2, q3)`é o mesmo `(Controlled X)([q1, q2], q3)` que.

A <xref:microsoft.quantum.intrinsic.swap> operação troca os estados quânticos de dois qubits.
Ou seja, implementa a matriz unitária \start{equação} \operatorname{SWAP} \mathrel{:=} \start{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}.
\end{equação} Tem assinatura `((Qubit, Qubit) => Unit is Adj + Ctl)` .
`SWAP(q1,q2)`é equivalente a `CNOT(q1, q2)` seguido por `CNOT(q2, q1)` e, em `CNOT(q1, q2)` seguida, .

> [!NOTE]
> O portão SWAP *não* é o mesmo que reorganizar os elementos de uma variável com o tipo `Qubit[]` .
> A aplicação `SWAP(q1, q2)` provoca uma alteração ao estado dos qubits referidos `q1` `q2` e, embora `let swappedRegister = [q2, q1];` apenas afete a forma como nos referimos a esses qubits.
> Além disso, `(Controlled SWAP)([q0], (q1, q2))` permite estar condicionado ao estado de um terceiro `SWAP` qubit, que não podemos representar através da reorganização de elementos.
> O portão swap controlado, também conhecido como o portão Fredkin, é poderoso o suficiente para incluir toda a computação clássica.

Por último, o prelúdio prevê duas operações para representar exponencial dos operadores de Pauli multi-qubit.
A <xref:microsoft.quantum.intrinsic.exp> operação executa uma rotação baseada num produto tensor de matrizes Pauli, representada pelo multi-qubit unitário \begin{equação} \operatorname{Exp}(\vec{\sigma}, \phi) \mathrel{:=} \exp\left(i\phi \sigma_0 \otimes \sigma_1 \otimes \otimes \otimes \sigma_n \right), \end{equation} where $\vec{\sigma} = (\sigma_0, \sigma_1, \pontos, \sigma_n)$ é uma sequência de operadores pauli de um único qubit, e onde $\phi$ é um ângulo.
A `Exp` rotação representa $\vec{\sigma}$ como uma variedade de `Pauli` elementos, de modo a que tenha assinatura `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` .

A <xref:microsoft.quantum.intrinsic.expfrac> operação executa a mesma rotação, utilizando a notação de fração dyad discutida acima.
Tem `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` assinatura.

> [!WARNING]
> As exponenciais do produto tensor dos operadores Pauli não são os mesmos que os produtos tensores dos exponencial dos operadores da Pauli.
> Ou seja, $e^{i (Z \otimes Z) \phi} \ne e^{i Z \phi} \otimes e^{i Z \phi}$.

### <a name="measurements"></a>Medições ###

Ao medir, o valor de +1 do operador a ser medido corresponde a um `Zero` resultado e o -1 égénico para `One` um resultado.

> [!NOTE]
> Embora esta convenção possa parecer estranha, tem duas vantagens muito boas.
> Em primeiro lugar, observar o resultado $\ket {0} $ é representado pelo `Result` `Zero` valor, enquanto observa $\ket {1} $ corresponde a `One` .
> Em segundo lugar, podemos escrever que o eigenvalue $\lambda$ correspondente a um resultado $r$ é $\lambda = (-1)^r$.

As operações de medição não suportam nem o `Adjoint` functor nem o `Controlled` functor.

A <xref:microsoft.quantum.intrinsic.measure> operação efetua uma medição conjunta de um ou mais qubits no produto especificado dos operadores da Pauli.
Se a matriz de Pauli e a matriz de qubits forem diferentes comprimentos, então a operação falha.
`Measure`tem assinatura `((Pauli[], Qubit[]) => Result)` .

Note que uma medição articular não é a mesma que medir cada qubit individualmente.
Por exemplo, considere o estado $\ket {11} = \ket {1} \otimes \ket {1} = X\otimes X \ket {00} $.
Medindo $Z_0$ e $Z_1$ cada um individualmente, obtemos os resultados $r_0 = 1$ e $r_1 = 1$.
Medindo $Z_0 Z_1$, no entanto, obtemos o único resultado $r_{\textrm{joint}} = 0$, representando que a paridade de $\ket {11} $ é positiva.
Dito de forma diferente, $(-1)^{r_0 + r_1} = (-1)^r_{\textrm{joint}})$.
Criticamente, uma vez que *só* aprendemos a paridade com esta medida, qualquer informação quântica representada na superposição entre os dois estados de dois qubits de paridade positiva, $\ket {00} $ e $\ket {11} $, é preservada.
Esta propriedade será essencial mais tarde, enquanto discutimos a correção de erros.

Por conveniência, o prelúdio também fornece duas outras operações para medir qubits.
Em primeiro lugar, uma vez que a realização de medições de um único qubit é bastante comum, o prelúdio define uma abreviatura para este caso.
A <xref:microsoft.quantum.intrinsic.m> operação mede o operador pauli $Z$ num único qubit, e tem assinatura `(Qubit => Result)` .
`M(q)`é equivalente a `Measure([PauliZ], [q])` .

As <xref:microsoft.quantum.measurement.multim> medidas que o Operador Pauli $Z$ *separadamente* em cada uma de uma matriz de qubits, devolvendo a *matriz* de `Result` valores obtidos para cada qubit.
Em alguns casos, isto pode ser otimizado. Tem assinatura ( `Qubit[] => Result[])` .
`MultiM(qs)`equivale a:

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a>Funções e Operações de Extensão ##

Além disso, o prelúdio define um conjunto rico de funções de conversão matemática e tipo ao nível .NET para utilização dentro do Q# código.
Por exemplo, o <xref:microsoft.quantum.math> espaço de nome define operações úteis tais como e <xref:microsoft.quantum.math.sin> <xref:microsoft.quantum.math.log> .
A implementação fornecida pelo Kit de Desenvolvimento Quântico utiliza a clássica biblioteca de classe base .NET, podendo assim envolver uma viagem de ida e volta de comunicações adicional entre programas quânticos e seus condutores clássicos.
Embora isto não apresente um problema para um simulador local, este pode ser um problema de desempenho ao usar um simulador remoto ou hardware real como uma máquina alvo.
Dito isto, uma máquina-alvo individual pode mitigar este impacto de desempenho, sobrepôs-se a estas operações com versões mais eficientes para esse sistema específico.

### <a name="math"></a>Matemática ###

O <xref:microsoft.quantum.math> espaço de nomes fornece muitas funções úteis da classe base da [ `System.Math` biblioteca](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1).NET.
Estas funções podem ser utilizadas da mesma forma que quaisquer Q# outras funções:

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

Quando um método estático .NET tiver sido sobrecarregado com base no tipo dos seus argumentos, a função correspondente Q# é anotada com um sufixo que indique o tipo da sua entrada:

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>Operações Bitwise ###

Finalmente, o <xref:microsoft.quantum.bitwise> espaço de nomes fornece várias funções úteis para manipular inteiros através de operadores bitwise.
Por exemplo, <xref:microsoft.quantum.bitwise.parity> devolve a paridade de um inteiro como outro inteiro.
