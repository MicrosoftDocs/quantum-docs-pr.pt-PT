---
title: Operações e funções intrínsecas no QDK
description: Conheça as operações e funções intrínsecas no QDK, incluindo funções clássicas e operações unitárias, de rotação e medição.
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b1c26c632f36b6c254d940a89b13638f7592ab80
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907210"
---
# <a name="the-prelude"></a>O Prelúdio #

O compilador Q# e as máquinas-alvo incluídas no Kit de Desenvolvimento Quântico fornecem um conjunto de funções e operações intrínsecas que podem ser usadas ao escrever programas quânticos em Q#.

## <a name="intrinsic-operations-and-functions"></a>Operações e Funções Intrínsecas ##

As operações intrínsecas definidas na biblioteca padrão enquadram-se aproximadamente numa das várias categorias:

- Funções clássicas essenciais, recolhidas no espaço de nome <xref:microsoft.quantum.core>.
- Operações que representam unitários compostos por [Clifford e portões $T$.](xref:microsoft.quantum.concepts.qubit)
- Operações que representam rotações sobre vários operadores.
- Operações de implementação de medições.

Uma vez que o conjunto de portaClifford + $T$ é [universal](xref:microsoft.quantum.concepts.multiple-qubits) para a computação quântica, estas operações são suficientes para implementar aproximadamente qualquer algoritmo quântico dentro de um pequeno erro insignificante.
Ao fornecer rotações também, Q# permite que o programador trabalhe dentro da biblioteca de portão unitário e CNOT. Esta biblioteca é muito mais fácil de pensar porque não requer que o programador expresse diretamente a decomposição clifford + $T$ e porque existem métodos altamente eficientes para compilar unificações de qubit em Clifford e portões $T$ (ver [aqui](xref:microsoft.quantum.more-information) para mais informações).

Sempre que possível, as operações definidas no prelúdio que atuam sobre qubits permitem aplicar a variante `Controlled`, de modo a que a máquina-alvo efetue a decomposição adequada.

Muitas das funções e operações definidas nesta parte do prelúdio estão no espaço de nome @"microsoft.quantum.intrinsic", de tal forma que a maioria dos ficheiros de origem Q# terá uma diretiva `open Microsoft.Quantum.Intrinsic;` imediatamente após a declaração inicial do espaço de nome.
O espaço de nome <xref:microsoft.quantum.core> é automaticamente aberto, de modo que funções como <xref:microsoft.quantum.core.length> podem ser usadas sem uma declaração `open`.

### <a name="common-single-qubit-unitary-operations"></a>Operações Unitárias Moqubit Comuns ###

O prelúdio também define muitas operações comuns [de monobit.](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)
Todas estas operações permitem tanto os functores `Controlled` como `Adjoint`.

#### <a name="pauli-operators"></a>Operadores Pauli ####

A operação <xref:microsoft.quantum.intrinsic.x> implementa o operador Pauli $X$.
Isto às vezes também é conhecido como o portão `NOT`.
Tem assinatura `(Qubit => Unit is Adj + Ctl)`.
Corresponde ao único qubit unitário:

\begin{equation} \begin{bmatrix} 0 & 1 \\\\ % FIXME: isto usa atualmente o hack quadwhack.
1 & 0 \end{bmatrix} \end{equation}

A operação <xref:microsoft.quantum.intrinsic.y> implementa o operador Pauli $Y$.
Tem assinatura `(Qubit => Unit is Adj + Ctl)`.
Corresponde ao único qubit unitário:

\begin{equation} \begin{bmatrix} 0 & i \\\\ % FIXME: isto usa atualmente o hack quadwhack.
i & 0 \end{bmatrix} \end{equation}

A operação <xref:microsoft.quantum.intrinsic.z> implementa o operador Pauli $Z$.
Tem assinatura `(Qubit => Unit is Adj + Ctl)`.
Corresponde ao único qubit unitário:

\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: isto utiliza atualmente o hack quadwhack.
0 & -1 \end{bmatrix} \end{equation}

Abaixo vemos estas transformações mapeadas para a [esfera bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (o eixo de rotação em cada caso é destacado vermelho):

![Operações de Pauli mapeadas na esfera bloch](~/media/prelude_pauliBloch.png)

É importante notar que aplicar o mesmo portão Pauli duas vezes ao mesmo qubit cancela a operação (porque já realizou uma rotação completa de 2π (360°) sobre a superfície para a Esfera bloch, chegando assim ao ponto de partida). Isto leva-nos à seguinte identidade:

$$ X^2=Y^2=Z^2=\boldone $$

Isto pode ser visualizado na esfera bloch:

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>Outros Cliffords Single-Qubit ####

A operação <xref:microsoft.quantum.intrinsic.h> implementa o portão hadamard.
Isto troca os eixos Pauli $X$ e $Z$ do qubit alvo, de tal forma que $H\ket{0} = \ket{+} \mathrel{:=} (\ket{0} + \ket{1}) / \sqrt{2}$ e $H\ket{+} = \ket{0}$.
Tem assinatura `(Qubit => Unit is Adj + Ctl)`, e corresponde ao único qubit unitário:

\begin{equation} \frac{1}{\sqrt{2}} \start{bmatrix} 1 e 1 \\\\ % FIXME: isto utiliza atualmente o hack quadwhack.
1 & -1 \end{bmatrix} \end{equation}

O portão Hadamard é particularmente importante, pois pode ser usado para criar uma superposição dos $\ket{0}$ e $ket{1}estados de $. Na representação da esfera bloch, é mais fácil pensar nisto como uma rotação de $\ket{\psi}$ em torno do eixo x por $\pi$ radians ($180^\circ$) seguido de uma rotação (no sentido horário) em torno do eixo y por $\pi/2$ radians ($90^\circ$):

![Operação Hadamard mapeada na esfera bloch](~/media/prelude_hadamardBloch.png)

A operação <xref:microsoft.quantum.intrinsic.s> implementa o portão de fase $S$.
Esta é a raiz quadrada da operação Pauli $Z$.
Isto é, $S^2 = Z$.
Tem assinatura `(Qubit => Unit is Adj + Ctl)`, e corresponde ao único qubit unitário:

\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: isto utiliza atualmente o hack quadwhack.
0 & i \end{bmatrix} \end{equation}

#### <a name="rotations"></a>Rotações ####

Além das operações de Pauli e Clifford acima, o prelúdio Q# fornece uma variedade de formas de expressar rotações.
Como descrito em [operações de qubit único,](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)a capacidade de rotação é crítica para algoritmos quânticos.

Começamos por recordar que podemos expressar qualquer operação de um único qubit utilizando os portões $H$ e $T$, onde $H$ é a operação Hadamard, e onde \start{equation} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ % FIXME: isto usa atualmente o quad back whack hack.
0 & e^{i \pi / 4} \end{bmatrix} \end{equation} Esta é a raiz quadrada da operação <xref:microsoft.quantum.intrinsic.s>, de tal forma que $T^2 = S$.
O portão $T$ é, por sua vez, implementado pela operação <xref:microsoft.quantum.intrinsic.t>, e tem assinatura `(Qubit => Unit is Adj + Ctl)`, indicando que se trata de uma operação unitária num único qubit.

Embora isso seja, em princípio, suficiente para descrever qualquer operação arbitrária de um único qubit, diferentes máquinas-alvo podem ter representações mais eficientes para rotações sobre os operadores pauli, de modo que o prelúdio inclui uma variedade de maneiras de convientamente expressar tais rotações.
O mais básico destes é a operação <xref:microsoft.quantum.intrinsic.r>, que implementa uma rotação em torno de um eixo Pauli especificado, \begin{equation} R (\sigma, \phi) \mathrel{:=} \exp(-i \phi \sigma / 2), \end{equation} onde $\sigma$ é um operador Pauli, $\phi$ é um ângulo, e onde $\exp$ representa a matriz exponencial.
Tem assinatura `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`, onde as duas primeiras partes da entrada representam os argumentos clássicos $\sigma$ e $\phi$ necessários para especificar o operador unitário $R (\sigma, \phi)$.
Podemos aplicar parcialmente $\sigma$ e $\phi$ para obter uma operação cujo tipo é o de um único qubit unitário.
Por exemplo, `R(PauliZ, PI() / 4, _)` tem tipo `(Qubit => Unit is Adj + Ctl)`.

> [!NOTE]
> A operação <xref:microsoft.quantum.intrinsic.r> divide o ângulo de entrada em 2 e multiplica-o por -1.
> Para $Z rotações de$, isto significa que o $\ket{0}$ eigenstate é rodado por $\phi / 2$ e o $\ket{1}$ eigenstate é rodado por $\phi / 2$, de modo que o $\ket{1}$  eigenstate $ é rodado por $\phi$ em relação ao $\ket{0}$ eigenstate.
>
> Isto significa, em especial, que `T` e `R(PauliZ, PI() / 8, _)` diferem apenas por uma [fase global](xref:microsoft.quantum.glossary#global-phase)irrelevante.
> Por esta razão, $T$ é por vezes conhecido como o $\frac{\pi}{8}$-gate.
>
> Note também que rodar em torno `PauliI` simplesmente aplica uma fase global de $\phi / 2$. Embora tais fases sejam irrelevantes, como argumentam [os documentos conceptuais,](xref:microsoft.quantum.concepts.qubit)são relevantes para rotações controladas `PauliI`.

Dentro de algoritmos quânticos, é muitas vezes útil expressar rotações como frações disadicas, de tal forma que $\phi = \pi k / 2^n$ para alguns $k \in \mathbb{Z}e $n \in \mathbb{N}$.
A operação <xref:microsoft.quantum.intrinsic.rfrac> implementa uma rotação em torno de um eixo Pauli especificado usando esta convenção.
Difere de <xref:microsoft.quantum.intrinsic.r> na medida em que o ângulo de rotação é especificado como duas inputs de tipo `Int`, interpretados como uma fração disadica.
Assim, `RFrac` tem assinatura `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.
Implementa a matriz unitária de um único qubit $\exp (i \pi k \sigma / 2^n)$, onde $\sigma$ é a matriz Pauli correspondente ao primeiro argumento, $k$ é o segundo argumento, e $n$ é o terceiro argumento.
`RFrac(_,k,n,_)` é o mesmo que `R(_,-πk/2^n,_)`; nota que o ângulo é o *negativo* da fração.

A operação <xref:microsoft.quantum.intrinsic.rx> implementa uma rotação em torno do eixo Pauli $X$.
Tem assinatura `((Double, Qubit) => Unit is Adj + Ctl)`.
`Rx(_, _)` é o mesmo que `R(PauliX, _, _)`.

A operação <xref:microsoft.quantum.intrinsic.ry> implementa uma rotação em torno do eixo Pauli $Y$.
Tem assinatura `((Double, Qubit) => Unit is Adj + Ctl)`.
`Ry(_, _)` é o mesmo que `R(PauliY,_ , _)`.

A operação <xref:microsoft.quantum.intrinsic.rz> implementa uma rotação em torno do eixo Pauli $Z$.
Tem assinatura `((Double, Qubit) => Unit is Adj + Ctl)`.
`Rz(_, _)` é o mesmo que `R(PauliZ, _, _)`.

A operação <xref:microsoft.quantum.intrinsic.r1> implementa uma rotação pelo valor dado em torno de $\ket{1}$, o eigenstate de $1$1$ de $Z$.
Tem assinatura `((Double, Qubit) => Unit is Adj + Ctl)`.
`R1(phi,_)` é o mesmo que `R(PauliZ,phi,_)` seguido de `R(PauliI,-phi,_)`.

A operação <xref:microsoft.quantum.intrinsic.r1frac> implementa uma rotação fracionada pelo montante dado em torno do z=1 eigenstate.
Tem assinatura `((Int,Int, Qubit) => Unit is Adj + Ctl)`.
`R1Frac(k,n,_)` é o mesmo que `RFrac(PauliZ,-k.n+1,_)` seguido de `RFrac(PauliI,k,n+1,_)`.

Um exemplo de uma operação de rotação (em torno do eixo Pauli $Z$, neste caso) mapeado na esfera bloch é mostrado abaixo:

![Operação de rotação mapeada na esfera bloch](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>Operações Multiqubit ####

Para além das operações de qubit único acima, o prelúdio também define várias operações multiqubit.

Primeiro, a operação <xref:microsoft.quantum.intrinsic.cnot> executa um portão de`NOT` controlado padrão, \start{equation} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 e 0 \\\\ 0 & 0 &amp \\; 0 & 0 & 0 \\ 0 & 0 & 0 & 0 & 0 & 0 {bmatrix.
\end{equation} Tem assinatura `((Qubit, Qubit) => Unit is Adj + Ctl)`, representando que $\operatorname{CNOT}$ atua unitamente em dois qubits individuais.
`CNOT(q1, q2)` é o mesmo que `(Controlled X)([q1], q2)`.
Uma vez que o functor `Controlled` permite controlar um registo, usamos a matriz literal `[q1]` para indicar que queremos apenas um controlo.

A operação <xref:microsoft.quantum.intrinsic.ccnot> executa o portão NOT controlado duplamente, por vezes também conhecido como portão Toffoli.
Tem assinatura `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.
`CCNOT(q1, q2, q3)` é o mesmo que `(Controlled X)([q1, q2], q3)`.

A operação <xref:microsoft.quantum.intrinsic.swap> troca os estados quânticos de dois qubits.
Ou seja, implementa a matriz unitária \begin {equation} \operatorname {SWAP} \mathrel{:=} \start{bmatrix} 1 & 0 & \\0 & 0 e 0 \\ 0 & 0 & 0 e 0 \\\\ 0 & 1 & \\0 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix}.
\end{equation} Tem assinatura `((Qubit, Qubit) => Unit is Adj + Ctl)`.
`SWAP(q1,q2)` equivale a `CNOT(q1, q2)` seguido de `CNOT(q2, q1)` e depois `CNOT(q1, q2)`.

> [!NOTE]
> O portão SWAP *não* é o mesmo que reorganizar os elementos de uma variável com tipo `Qubit[]`.
> A aplicação `SWAP(q1, q2)` provoca uma alteração ao estado dos qubits referidos pelos `q1` e `q2`, enquanto `let swappedRegister = [q2, q1];` apenas afeta a forma como nos referimos a esses qubits.
> Além disso, `(Controlled SWAP)([q0], (q1, q2))` permite que `SWAP` seja condicionado no estado de um terceiro qubit, que não podemos representar reorganizando elementos.
> O portão controlado swap, também conhecido como o portão Fredkin, é poderoso o suficiente para incluir toda a computação clássica.

Finalmente, o prelúdio fornece duas operações para representar exponencialmente os operadores de Pauli multiqubit.
A operação <xref:microsoft.quantum.intrinsic.exp> realiza uma rotação baseada num produto tensor de matrizes Pauli, representada pelo multiqubit unitary \begin{equation} \operatorname{Exp}(\vec{\sigma}, \phi) \mathrel{:=} \exp\left(i \phi \sigma_0 \otimes \sigma_1 \otimes \otimes \sigma_n \right), \end{equation} where $\vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n)$ é uma sequência de operadores de Pauli de um único qubit, e onde $\phi$ é um ângulo.
A rotação `Exp` representa $\vec{\sigma}$ como uma variedade de elementos `Pauli`, de tal forma que tem assinatura `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.

A operação <xref:microsoft.quantum.intrinsic.expfrac> realiza a mesma rotação, utilizando a notação da fração disadica acima discutida.
Tem assinatura `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.

> [!WARNING]
> Os exponenciais do produto tensor dos operadores Pauli não são os mesmos que os produtos tensores dos exponenciais dos operadores pauli.
> Ou seja, $e^{i (Z \otimes Z) \phi} \ne e^{i Z \phi} \otimes e^{i Z \phi}$.

### <a name="measurements"></a>Medições ###

Ao medir, o valor +1 do operador a ser medido corresponde a um resultado `Zero`, e o valor de -1 eigenvalue a um resultado `One`.

> [!NOTE]
> Embora esta convenção possa parecer estranha, tem duas vantagens muito agradáveis.
> Em primeiro lugar, observar o resultado $\ket{0}$ é representado pelo valor `Result` `Zero`, enquanto observar $\ket{1}$ corresponde a `One`.
> Em segundo lugar, podemos escrever que o eigenvalue $\lambda$ correspondente a um resultado $r$ é $\lambda = (-1)^r$.

As operações de medição não suportam nem o `Adjoint` nem o `Controlled` functor.

A operação <xref:microsoft.quantum.intrinsic.measure> efetua uma medição conjunta de um ou mais qubits no produto especificado dos operadores pauli.
Se a matriz Pauli e a matriz qubit tiverem comprimentos diferentes, então a operação falha.
`Measure` tem `((Pauli[], Qubit[]) => Result)`de assinatura.

Note que uma medição articular não é a mesma que medir cada qubit individualmente.
Por exemplo, considere o estado $\ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.
Medindo $Z_0$ e $Z_1$ cada um individualmente, obtemos os resultados $r_0 = 1$ e $r_1 = 1$1$.
Medindo $Z_0 Z_1$, no entanto, obtemos o resultado único $r_{\textrm{joint}} = 0$, representando que a paridade de $\ket{11}$ é positiva.
Coloque de forma diferente, $(-1)^{r_0 + r_1} = (-1)^r_{\textrm{joint}}}.$.
Criticamente, uma vez que *só* aprendemos a paridade com esta medida, qualquer informação quântica representada na superposição entre os dois estados de paridade positiva, $\ket{00}$ e $\ket{11}$ket, é preservada.
Esta propriedade será essencial mais tarde, enquanto discutimos a correção de erros.

Por conveniência, o prelúdio também fornece duas outras operações para medir qubits.
Em primeiro lugar, uma vez que a realização de medições de qubit único é bastante comum, o prelúdio define uma abreviatura para este caso.
A operação <xref:microsoft.quantum.intrinsic.m> mede o operador Pauli $Z$ num único qubit, e tem assinatura `(Qubit => Result)`.
`M(q)` equivale a `Measure([PauliZ], [q])`.

O <xref:microsoft.quantum.measurement.multim> mede o operador Pauli $Z$ *separadamente* em cada um de um conjunto de qubits, devolvendo o *conjunto* de valores `Result` obtidos para cada qubit.
Em alguns casos, isto pode ser otimizado. Tem assinatura (`Qubit[] => Result[])`.
`MultiM(qs)` equivale a:

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a>Funções e Operações de Extensão ##

Além disso, o prelúdio define um conjunto rico de funções matemáticas e de conversão de tipos no nível .NET para utilização dentro do código Q#.
Por exemplo, o espaço de nome <xref:microsoft.quantum.extensions.math> define operações úteis como <xref:microsoft.quantum.extensions.math.sin> e <xref:microsoft.quantum.extensions.math.log>.
A implementação fornecida pelo Quantum Development Kit utiliza a clássica biblioteca de classes base .NET, podendo assim envolver uma viagem de ida e volta de comunicações adicional entre os programas quânticos e os seus condutores clássicos.
Embora isto não apresente um problema para um simulador local, este pode ser um problema de desempenho ao usar um simulador remoto ou hardware real como uma máquina-alvo.
Dito isto, uma máquina-alvo individual pode atenuar este impacto de desempenho, ultrapassando estas operações com versões mais eficientes para esse sistema específico.

### <a name="math"></a>Matemática ###

O espaço de nome <xref:microsoft.quantum.extensions.math> fornece muitas funções úteis da classe base da biblioteca base .NET [`System.Math` classe](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1).
Estas funções podem ser utilizadas da mesma forma que quaisquer outras funções Q#:

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

Quando um método estático .NET tenha sido sobrecarregado com base no tipo dos seus argumentos, a função Q# correspondente é anotada com um sufixo indicando o tipo da sua entrada:

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>Operações Bitwise ###

Finalmente, o espaço de nome <xref:microsoft.quantum.extensions.bitwise> fornece várias funções úteis para manipular os inteiros através de operadores bitwise.
Por exemplo, <xref:microsoft.quantum.extensions.bitwise.parity> devolve a paridade bitwise de um inteiro como outro inteiro.
