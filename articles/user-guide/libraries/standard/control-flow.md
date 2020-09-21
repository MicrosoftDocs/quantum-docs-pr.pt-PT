---
title: Controlos de fluxo nos Q# libarries padrão
description: Saiba mais sobre as operações e funções de controlo de fluxo na biblioteca padrão da Q# Microsoft.
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1cfef50cf2bbecd2043972a662edd8120c5570ec
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835626"
---
# <a name="higher-order-control-flow"></a>Fluxo de controlo de ordem superior #

Um dos principais papéis da biblioteca padrão é facilitar a expressão de ideias algorítmicas de alto nível como [programas quânticos.](https://en.wikipedia.org/wiki/Quantum_programming)
Assim, o Q# cânone fornece uma variedade de diferentes construções de controlo de fluxo, cada uma implementada usando a aplicação parcial de funções e operações.
Saltando imediatamente para um exemplo, considere o caso em que se quer construir uma "escada CNOT" num registo:

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

Podemos expressar este padrão usando iteração e `for` laços:

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

Expressa em termos de funções de <xref:microsoft.quantum.canon.applytoeachca> manipulação de matrizes, tais <xref:microsoft.quantum.arrays.zip> como, no entanto, isto é muito mais curto e fácil de ler:

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

No resto desta secção, forneceremos uma série de exemplos de como usar as várias operações e funções de controlo de fluxos fornecidas pelo cânone para expressar compactamente programas quânticos.

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>Aplicação de Operações e Funções sobre Matrizes e Gamas ##

Uma das abstrações primárias fornecidas pelo cânone é a da iteração.
Por exemplo, considere um unitário do formulário $U \otimes U \otimes \cdots \otimes U$ para um único qubit unitário $U$.
Em Q# , podemos usar <xref:microsoft.quantum.arrays.indexrange> para representar isto como um loop sobre um `for` registo:

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

Em seguida, podemos utilizar esta nova operação `HAll(register)` para aplicar $H \otimes H \otimes \cdots \otimes H$.

Isto é complicado de fazer, no entanto, especialmente num algoritmo maior.
Além disso, esta abordagem é especializada na operação específica que pretendemos aplicar a cada qubit.
Podemos usar o facto de que as operações são de primeira classe para expressar este conceito algorítmico de forma mais explícita:

```qsharp
ApplyToEachCA(H, register);
```

Aqui, o `CA` sufixo indica que a chamada é em si adjacente e `ApplyToEach` controlável.
Assim, se `U` os suportes `Adjoint` `Controlled` e, as seguintes linhas forem equivalentes:

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

Isto significa, nomeadamente, que as chamadas `ApplyToEachCA` podem aparecer em operações para as quais é gerada uma especialização adjacente.
Da mesma forma, <xref:microsoft.quantum.canon.applytoeachindex> é útil para representar padrões do formulário , e oferece `U(0, targets[0]); U(1, targets[1]); ...` versões para cada combinação de funtores suportados pela sua entrada.

> [!TIP]
> `ApplyToEach` é de tipo parametrizado de modo a que possa ser utilizado com operações que tomem entradas diferentes `Qubit` de .
> Por exemplo, suponha que `codeBlocks` esta é uma variedade de <xref:microsoft.quantum.errorcorrection.logicalregister> valores que precisam de ser recuperados.
> Em seguida, `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` aplicará o código de correção de `code` erros e a função de recuperação `recoveryFn` a cada bloco de forma independente.
> Isto mantém-se mesmo para entradas clássicas: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` aplicará uma rotação de $\pi / 2$ cerca de $X$ seguido de uma rotação de $pi / 3$ cerca de $Y$.

O Q# cânone também fornece suporte para padrões clássicos de enumeração familiares à programação funcional.
Por exemplo, <xref:microsoft.quantum.arrays.fold> implementa o padrão $f(f(f(s \_ {\text{initial}, x \_ 0), x \_ 1), \pontos)$ para reduzir uma função sobre uma lista.
Este padrão pode ser usado para implementar somas, produtos, minima, maxima e outras funções:

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

Da mesma forma, funções como <xref:microsoft.quantum.arrays.mapped> e <xref:microsoft.quantum.arrays.mappedbyindex> podem ser usadas para expressar conceitos de programação funcional em Q# .

## <a name="composing-operations-and-functions"></a>Composição de Operações e Funções ##

O fluxo de controlo constrói operações e funções como suas entradas, de modo a ser útil para ser capaz de compor várias operações ou funções numa única chamada.
Por exemplo, o padrão $UVU^{\dagger}} é extremamente comum na programação quântica, de modo que o cânone fornece a operação <xref:microsoft.quantum.canon.applywith> como uma abstração para este padrão.
Esta abstração também permite uma conformidade mais eficiente em circuitos, uma vez `Controlled` que agir na sequência não precisa de agir em cada um `U(qubit); V(qubit); Adjoint U(qubit);` `U` .
Para ver isto, deixe $c(U)$ ser o representante unitário `Controlled U([control], target)` e deixar $c(V)$ ser definido da mesma forma.
Em seguida, para um estado arbitrário $\ket{\psi}$, \start{align} c(U) c(U)^\\dagger \ket {1} \otimes \ket{\psi} & = \ket {1} \otimes (UVU ^{\dagger} \ket{\psi}) \\ \\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket {1} \otimes \ket{\psi}.
\end{align} pela definição de `Controlled` .
Por outro lado, \start{align} c(U) c(V) c(U)^\\dagger \ket {0} \otimes \ket{\psi} & = \ket {0} \otimes \ket{\psi} \\ \\ & = \ket \\ket \\\ket \\\ket \\ket \otimes \ket \ket{\psi} {0} otimes (UU^\dagger \ket{\psi}) \\ \\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket {0} \otimes \ket{\psi}.
\end{align} Por linearidade, podemos concluir que podemos fator $U$ desta forma para todos os estados de entrada.
Ou seja, $c (UVU^\dagger) = U c(V) U^\dagger$.
Uma vez que as operações de controlo podem ser dispendiosas em geral, a utilização de variantes controladas, como `WithC` e pode ajudar a reduzir o número de `WithCA` funtores de controlo que precisam de ser aplicados.

> [!NOTE]
> Uma outra consequência de considerar $U$ é que nem precisamos de saber como aplicar o `Controlled` functor a `U` .
> `ApplyWithCA` por conseguinte, tem uma assinatura mais fraca do que seria de esperar:
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

Podemos ir ainda mais longe pensando no controlo do fluxo em termos de aplicação parcial e funções clássicas, e podemos modelar até conceitos quânticos bastante sofisticados em termos de controlo clássico do fluxo.
Esta analogia é precisamente com o reconhecimento de que os operadores unitários correspondem exatamente aos efeitos secundários das operações de chamada, de modo a que qualquer decomposição dos operadores unitários em termos de outros operadores unitários corresponda à construção de uma sequência de chamadas específica para as subroutinas clássicas que emitem instruções para atuarem como operadores unitários específicos.
Nesta perspetiva, `Bound` é precisamente a representação do produto matriz, uma vez `Bound([A, B])(target)` que é equivalente a , que por sua vez é a sequência de chamadas correspondente a `A(target); B(target);` $BA$.

Um exemplo mais sofisticado é a [expansão Trotter-Suzuki.](https://arxiv.org/abs/math-ph/0506007v1)
Como discutido na secção de Representação do Gerador Dinâmico das estruturas de [dados,](xref:microsoft.quantum.libraries.data-structures)a expansão Trotter-Suzuki fornece uma forma particularmente útil de expressar exponencials da matriz.
Por exemplo, a aplicação da expansão na sua encomenda mais baixa rende que para qualquer operador $A$ e $B$ de tal forma que $A = A^\dagger$ e $B = B^\dagger$, \start{align} \tag{★} \label{eq:trotter-suzuki-0} \exp(i [A + B] t) = \lim_{n\to\in\to\exp(i A t/ n) \exp(i B t/ n)\right)^n.
\end{align} Coloquialmente, isto diz que podemos aproximadamente evoluir um estado sob $A + B$ evoluindo alternadamente sob $A$ e $B$ sozinho.
Se representarmos a evolução sob $A$ por uma operação `A : (Double, Qubit[]) => Unit` que se aplica $e^{i t A}$, então a representação da expansão Trotter-Suzuki em termos de reorganização das sequências de chamadas torna-se clara.
Concretamente, dada uma operação `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` de tal forma `A = U(0, _, _)` `B = U(1, _, _)` que, podemos definir uma nova operação que represente a integral de `U` $t$ gerando sequências da forma

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

Neste momento, podemos agora raciocinar sobre a expansão Trotter-Suzuki *sem qualquer referência à mecânica quântica.*
A expansão é efetivamente um padrão de iteração muito particular motivado por $\eqref{eq:trotter-suzuki-0}$.
Este padrão de iteração é implementado <xref:microsoft.quantum.canon.decomposeintotimestepsca> por:

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

A assinatura `DecomposeIntoTimeStepsCA` segue um padrão comum em , onde Q# coleções que podem ser apoiadas quer por matrizes quer por algo que os elementos computativos na mosca são representados por tuples cujos primeiros elementos são `Int` valores que indicam os seus comprimentos.

## <a name="putting-it-together-controlling-operations"></a>Junção: Controlo de Operações ##

Finalmente, o cânone baseia-se no `Controlled` functor, fornecendo formas adicionais de condicionar as operações quânticas.
É comum, especialmente na aritmética quântica, condicionar operações em estados computacionais que não $\ket{0\cdots 0}$.
Utilizando as operações de controlo e funções acima introduzidas, podemos condições quânticas mais gerais numa única declaração.
Vamos saltar para como <xref:microsoft.quantum.canon.controlledonbitstring> é que ele (sans type parâmetros), então vamos quebrar as peças um por um.
A primeira coisa que temos de fazer é definir uma operação que realmente faz o pesado levantamento da implementação do controlo em estados computacionais arbitrários.
Não vamos chamar esta operação diretamente, no entanto, e por isso adicionamos `_` ao início do nome para indicar que é uma implementação de outra construção em outro lugar.

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

Note que tomamos uma série de bits, representados como uma `Bool` matriz, que usamos para especificar o condicionamento que queremos aplicar à operação `oracle` que nos é dada.
Uma vez que esta operação faz a aplicação diretamente, precisamos também de assumir os registos de controlo e alvo, ambos aqui representados como `Qubit[]` .

Em seguida, notamos que controlar na base computacional estado $\ket{\vec{s}} = \ket{s \_ 0 s \_ 1 \dots s \_ {n - 1}}$ para uma corda de bits $\vec{s}$ pode ser realizado transformando $\ket{\vec{s}} em $\ket{0\cdots 0}$.
Em particular, $\ket{\vec{s}} = X^{s \_ 0} \otimes X^{s \_ 1} \otimes \cdots \otimes X^{s \_ {n - 1}} \ket{0\cdots 0}$.
Desde $X^{\dagger} = X$, isto implica que $\ket{0\dots 0} = X^{s \_ 0} \otimes \_ \otimes \cdots \otimes X^{s \_ {n - 1}} \ket{\vec{s}}.}
Assim, podemos aplicar $P = X^{s \_ 0} \otimes X^{s \_ 1} \otimes \otimes \otimes X^{s \_ {n - 1}}$, apply `Controlled oracle` , e transformar de volta para $\vec{s}$.
Esta construção é `ApplyWith` precisamente, por isso escrevemos o corpo da nossa nova operação em conformidade:

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

Aqui, nós usamos <xref:microsoft.quantum.canon.applypaulifrombitstring> para aplicar $P$, aplicando parcialmente sobre o seu alvo para uso com `ApplyWith` .
Note-se, no entanto, que precisamos de transformar o registo de *controlo* na nossa forma desejada, por isso aplicamos parcialmente a operação interna `(Controlled oracle)` no *alvo.*
Isto deixa `ApplyWith` agir para escoar o registo de controlo com $P$, exatamente como desejamos.

Neste momento, poderíamos estar acabados, mas é de alguma forma insatisfatório que a nossa nova operação não "sinta" a vontade de aplicar o `Controlled` functor.
Assim, terminamos a definição do nosso novo conceito de fluxo de controlo escrevendo uma função que leva o oráculo a ser controlado e que devolve uma nova operação.
Desta forma, a nossa nova função parece e parece `Controlled` muito, ilustrando que podemos facilmente definir novas construções de fluxo de controlo poderosas usando Q# e o cânone juntos:

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
