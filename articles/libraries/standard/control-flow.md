---
title: Controlos de fluxo nos libarários padrão Q#
description: Conheça as operações e funções de controlo de fluxo na biblioteca padrão Microsoft Q#.
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b41b3edd7a3e3ac13dbda106a869f4cba8183600
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907176"
---
# <a name="higher-order-control-flow"></a>Fluxo de controlo de ordem superior #

Um dos principais papéis da biblioteca padrão é facilitar a expressão de ideias algorítmicas de alto nível como [programas quânticos.](https://en.wikipedia.org/wiki/Quantum_programming)
Assim, o cânone Q# fornece uma variedade de diferentes construções de controlo de fluxo, cada uma implementada usando aplicação parcial de funções e operações.
Saltando imediatamente para um exemplo, considere o caso em que se quer construir uma "escada CNOT" num registo:

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

Podemos expressar este padrão usando iteração e `for` loops:

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

Expresso em termos de <xref:microsoft.quantum.canon.applytoeachca> e de manipulação de matriz, tais como <xref:microsoft.quantum.arrays.zip>, no entanto, isto é muito mais curto e fácil de ler:

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

No resto desta secção, forneceremos uma série de exemplos de como usar as várias operações e funções de controlo de fluxo fornecidas pelo cânon para expressar compactamente programas quânticos.

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>Aplicação de operações e funções sobre matrizes e gamas ##

Uma das abstrações primárias fornecidas pelo cânone é a da iteração.
Por exemplo, considere um unitário do formulário $U \otimes U \otimes \cdots \otimes U$ para um único qubit unitary $U$.
Em Q#, podemos usar <xref:microsoft.quantum.arrays.indexrange> para representar isto como um ciclo `for` sobre um registo:

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

Podemos então usar esta nova operação como `HAll(register)` para aplicar $H \otimes H \otimes \cdots \otimes H$.

Isto é complicado de fazer, no entanto, especialmente num algoritmo maior.
Além disso, esta abordagem é especializada na operação específica que pretendemos aplicar a cada qubit.
Podemos usar o facto de que as operações são de primeira classe para expressar este conceito algorítmico de forma mais explícita:

```qsharp
ApplyToEachCA(H, register);
```

Aqui, o sufixo `CA` indica que a chamada para `ApplyToEach` é em si mesma adjointable e controlável.
Assim, se `U` apoia `Adjoint` e `Controlled`, as seguintes linhas são equivalentes:

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

Isto significa, em particular, que as chamadas para `ApplyToEachCA` podem aparecer em operações para as quais uma especialização adjoint é gerada automaticamente.
Da mesma forma, <xref:microsoft.quantum.canon.applytoeachindex> é útil para representar padrões do formulário `U(0, targets[0]); U(1, targets[1]); ...`, e oferece versões para cada combinação de functores suportados pela sua entrada.

> [!TIP]
> `ApplyToEach` é parâmetro de tipo de modo a que possa ser utilizado com operações que tomem inputs que não sejam `Qubit`.
> Por exemplo, suponha que `codeBlocks` é uma série de valores <xref:microsoft.quantum.errorcorrection.logicalregister> que precisam de ser recuperados.
> Em seguida, `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` aplicará o código de correção de erros `code` e função de recuperação `recoveryFn` a cada bloco de forma independente.
> Isto mantém-se mesmo para entradas clássicas: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` aplicará uma rotação de $\pi / 2$ cerca de $X$ seguido de uma rotação de $pi / 3$ cerca de $Y$.

O cânon Q# também fornece suporte para padrões de enumeração clássica familiares à programação funcional.
Por exemplo, <xref:microsoft.quantum.arrays.fold> implementa o padrão $f (f(f(s\_{\text{initial}}, x\_0), x\_1), \pontos)$ para reduzir uma função sobre uma lista.
Este padrão pode ser utilizado para implementar somas, produtos, minima, maxima e outras funções:

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

Da mesma forma, funções como <xref:microsoft.quantum.arrays.mapped> e <xref:microsoft.quantum.arrays.mappedbyindex> podem ser usadas para expressar conceitos de programação funcional em Q#.

## <a name="composing-operations-and-functions"></a>Compor operações e funções ##

As construções de fluxo de controlo oferecidas pelo cânon tomam as operações e funções como suas inputs, de modo a que seja útil ser capaz de compor várias operações ou funções numa única chamada.
Por exemplo, o padrão $UVU^{\dagger}$ é extremamente comum na programação quântica, de tal forma que o cânã fornece a operação <xref:microsoft.quantum.canon.applywith> como uma abstração para este padrão.
Esta abstração também permite uma complição mais eficiente em circuitos, uma vez que `Controlled` atuando na sequência `U(qubit); V(qubit); Adjoint U(qubit);` não precisa de agir em cada `U`.
Para ver isto, que $c(U)$ seja o unitário que representa `Controlled U([control], target)` e deixe que $c(V)$ seja definido da mesma forma.
Em seguida, para um estado arbitrário $\ket {\psi}$, \start{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & =(\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \otimes \otimes
\fim{alinhar} pela definição de `Controlled`.
Por outro lado, \begin{align} c(U) c(V) c(U)^dagger \ket{0} \otimes \ket {\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket {\psi}.
\end{align} Por linearidade, podemos concluir que podemos considerar $U$ desta forma para todos os estados de entrada.
Ou seja, $c (UVU^\dagger) = U c(V) U^\dagger$.
Uma vez que o controlo das operações pode ser dispendioso em geral, a utilização de variantes controladas como `WithC` e `WithCA` pode ajudar a reduzir o número de functores de controlo que precisam de ser aplicados.

> [!NOTE]
> Uma outra consequência de ter $U$ é que nem sequer precisamos de saber como aplicar o functor `Controlled` para `U`.
> `ApplyWithCA`, portanto, tem uma assinatura mais fraca do que seria de esperar:
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

Da mesma forma, <xref:microsoft.quantum.canon.bound> produz operações que aplicam uma sequência de outras operações por sua vez.
Por exemplo, os seguintes são equivalentes:

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

Combinar com padrões de iteração pode tornar isto especialmente útil:

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>Composição ordenada pelo tempo ###

Podemos ir ainda mais longe pensando no controlo de fluxos em termos de aplicação parcial e funções clássicas, e podemos modelar conceitos quânticos até bastante sofisticados em termos de controlo de fluxoclássico.
Esta analogia é feita precisamente pelo reconhecimento de que os operadores unitários correspondem exatamente aos efeitos secundários das operações de chamada, de modo a que qualquer decomposição dos operadores unitários em termos de outros operadores unitários corresponda à construção de um determinado a sequência de chamadas para subrotinas clássicas que emitem instruções para agir como operadores unitários específicos.
Nesta perspetiva, `Bound` é precisamente a representação do produto matricial, uma vez que `Bound([A, B])(target)` equivale a `A(target); B(target);`, que por sua vez é a sequência de chamadas correspondente a $BA$.

Um exemplo mais sofisticado é a [expansão Trotter-Suzuki.](https://arxiv.org/abs/math-ph/0506007v1)
Conforme discutido na secção dinâmica de representação do gerador das estruturas de [dados,](xref:microsoft.quantum.libraries.data-structures)a expansão Trotter-Suzuki fornece uma forma particularmente útil de expressar exponenciais matriciais.
Por exemplo, aplicar a expansão à sua ordem mais baixa rende que para quaisquer operadores $A$ e $B$ de tal forma que $A = A^\dagger$ e $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp (i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A/ n) \exp(i B t / n)\right^n.
\end{align} Colloquially, isto diz que podemos evoluir aproximadamente um estado sob $A + B$ evoluindo alternadamente sob $A$ e $B$ apenas.
Se representarmos a evolução sob $A$ por uma operação `A : (Double, Qubit[]) => Unit` que se aplica $e^{i a}$, então a representação da expansão Trotter-Suzuki em termos de reorganização de sequências de chamadas torna-se clara.
Concretamente, dada uma operação `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` tal que `A = U(0, _, _)` e `B = U(1, _, _)`, podemos definir uma nova operação que represente a integral da `U` no momento $t$ gerando sequências da forma

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

Neste momento, podemos agora raciocinar sobre a expansão Trotter-Suzuki *sem qualquer referência à mecânica quântica.*
A expansão é efetivamente um padrão de iteração muito particular motivado por $\eqref{eq:trotter-suzuki-0}$.
Este padrão de iteração é implementado por <xref:microsoft.quantum.canon.decomposeintotimestepsca>:

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

A assinatura de `DecomposeIntoTimeStepsCA` segue um padrão comum em Q#, onde coleções que podem ser apoiadas quer por matrizes, quer por algo que computa elementos na mosca são representados por tuples cujos primeiros elementos são `Int` valores indicando os seus comprimentos.

## <a name="putting-it-together-controlling-operations"></a>Reunindo-o: Operações de Controlo ##

Finalmente, o cânon baseia-se no functor `Controlled`, fornecendo formas adicionais de condicionar as operações quânticas.
É comum, especialmente na aritmética quântica, condicionar operações em estados computacionais que não $\ket{0\cdots 0}$.
Utilizando as operações de controlo e as funções acima introduzidas, podemos condições quânticas mais gerais numa única declaração.
Vamos saltar para a forma como <xref:microsoft.quantum.canon.controlledonbitstring> faz (parâmetros do tipo sans), então vamos quebrar as peças um a um.
A primeira coisa que temos de fazer é definir uma operação que realmente faz o pesado levantamento da implementação do controlo em estados computacionais arbitrários.
No entanto, não chamaremos esta operação diretamente, e por isso adicionamos `_` ao início do nome para indicar que é uma implementação de outra construção noutro lugar.

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

Note que tomamos uma série de bits, representados como uma matriz de `Bool`, que usamos para especificar o condicionamento que queremos aplicar à operação `oracle` que nos é dado.
Uma vez que esta operação efetivamente faz a aplicação diretamente, precisamos também de assumir os registos de controlo e de alvo, ambos aqui representados como `Qubit[]`.

Em seguida, notamos que o controlo na base computacional estado $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}} para um pouco de cadeia $\vec{s}$ pode ser realizado transformando $\ket{{{s}}$} em $\ket{0\cdots 0}$.
Em particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \otimes \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.
Desde $X^{\dagger} = X$, isto implica que $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}}.$.
Assim, podemos aplicar $P = X^{s\_0} \otimes X^{s\_1} \otimes \otimes X^{s\_{n - 1}}},apply `Controlled oracle`, e transformar-se novamente em $\vec{s}$.
Esta construção é precisamente `ApplyWith`, por isso escrevemos o corpo da nossa nova operação em conformidade:

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

Aqui, utilizámos <xref:microsoft.quantum.canon.applypaulifrombitstring> para aplicar $P$, aplicando-se parcialmente sobre o seu alvo para utilização com `ApplyWith`.
Note-se, no entanto, que precisamos de transformar o registo de *controlo* na nossa forma desejada, pelo que aplicamos parcialmente a operação interna `(Controlled oracle)` no *alvo.*
Isto deixa `ApplyWith` a agir para estoirar o registo de controlo com $P$, exatamente como desejávamos.

Neste momento, poderíamos ser feitos, mas é de alguma forma insatisfatório que a nossa nova operação não "sinta" como aplicar o `Controlled` functor.
Assim, terminamos a definição do nosso novo conceito de fluxo de controlo escrevendo uma função que leva o oráculo a ser controlado e que devolve uma nova operação.
Desta forma, a nossa nova função parece-se muito com `Controlled`, ilustrando que podemos facilmente definir novas e poderosas construções de fluxo de controlo usando Q# e o cânone juntos:

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
