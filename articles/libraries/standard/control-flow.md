---
title: 'P # bibliotecas padrão – controle e fluxo | Microsoft Docs'
description: 'P # bibliotecas padrão – controle e fluxo'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5e865dbb48029724b6f507ecb63b85d10d80c9a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185652"
---
# <a name="higher-order-control-flow"></a>Fluxo de controle de ordem superior #

Uma das principais funções da biblioteca padrão é tornar mais fácil expressar ideias de algoritmos de alto nível como [programas Quantum](https://en.wikipedia.org/wiki/Quantum_programming).
Assim, o Q # Canon fornece uma variedade de diferentes construções de controle de fluxo, cada uma implementada usando aplicativos parciais de funções e operações.
Passando imediatamente para um exemplo, considere o caso em que um deseja construir uma "escada CNOT" em um registro:

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

Podemos expressar esse padrão usando loops de iteração e de `for`:

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

Expresso em termos de <xref:microsoft.quantum.canon.applytoeachca> e funções de manipulação de matriz, como <xref:microsoft.quantum.arrays.zip>, no entanto, isso é muito mais curto e mais fácil de ler:

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

No restante desta seção, forneceremos vários exemplos de como usar as várias operações de controle de fluxo e funções fornecidas pela Canon para os programas Quantum Compact expressamente.

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>Aplicando operações e funções em matrizes e intervalos ##

Uma das abstrações primárias fornecidas pela Canon é a de iteração.
Por exemplo, considere um meio do formato $U \otimes U \otimes \cdots \otimes U $ para um único-qubit unitário $U $.
Em Q #, podemos usar <xref:microsoft.quantum.arrays.indexrange> para representar isso como um loop de `for` sobre um registro:

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation HAll(register : Qubit[]) : Unit 
is Adj + Ctl {

    for (qubit in register) {
        H(qubit);
    }
}
```

Em seguida, podemos usar essa nova operação como `HAll(register)` para aplicar $H \otimes H \otimes \cdots \otimes H $.

No entanto, isso é complicado, especialmente em um algoritmo maior.
Além disso, essa abordagem é especializada para a operação específica que desejamos aplicar a cada qubit.
Podemos usar o fato de que as operações são de primeira classe para expressar esse conceito de algoritmo mais explicitamente:

```qsharp
ApplyToEachCA(H, register);
```

Aqui, o sufixo `CA` indica que a chamada para `ApplyToEach` é, por sua vez, adjacente e controlável.
Portanto, se `U` oferecer suporte a `Adjoint` e `Controlled`, as seguintes linhas serão equivalentes:

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

Em particular, isso significa que as chamadas para `ApplyToEachCA` podem aparecer em operações para as quais uma especialização adjacente é gerada automaticamente.
Da mesma forma, <xref:microsoft.quantum.canon.applytoeachindex> é útil para representar padrões do formulário `U(0, targets[0]); U(1, targets[1]); ...`e oferece versões para cada combinação de transmissão functors com suporte em sua entrada.

> [!TIP]
> o `ApplyToEach` é de tipo parametrizado, de modo que possa ser usado com operações que usam entradas diferentes de `Qubit`.
> Por exemplo, suponha que `codeBlocks` seja uma matriz de valores de <xref:microsoft.quantum.errorcorrection.logicalregister> que precisam ser recuperados.
> Em seguida, `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` aplicará o código de correção de erros `code` e a função de recuperação `recoveryFn` para cada bloco de forma independente.
> Isso contém até mesmo para entradas clássicas: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` aplicará uma rotação de $ \pi/$2 sobre $X $ seguido de uma rotação de $pi/$3 sobre $Y $.

O Q # Canon também fornece suporte para padrões de enumeração clássicas familiares à programação funcional.
Por exemplo, <xref:microsoft.quantum.arrays.fold> implementa o $f padrão (f (f (s\_{\Text{Initial}}, x\_0), x\_1), \dots) $ para reduzir uma função em uma lista.
Esse padrão pode ser usado para implementar somas, produtos, mínimo, máximo e outras funções desse tipo:

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

Da mesma forma, funções como <xref:microsoft.quantum.arrays.mapped> e <xref:microsoft.quantum.arrays.mappedbyindex> podem ser usadas para expressar conceitos de programação funcional em Q #.

## <a name="composing-operations-and-functions"></a>Compondo operações e funções ##

As construções de fluxo de controle oferecidas pela Canon tomam operações e funções como suas entradas, de modo que é útil poder compor várias operações ou funções em um único callable.
Por exemplo, o padrão $UVU ^ {\dagger} $ é extremamente comum na programação Quantum, de modo que a Canon fornece a operação <xref:microsoft.quantum.canon.applywith> como uma abstração para esse padrão.
Essa abstração também permite um compliation mais eficiente em circuitos, pois `Controlled` atuando na sequência `U(qubit); V(qubit); Adjoint U(qubit);` não precisa agir em cada `U`.
Para ver isso, permita que $c (U) $ seja o unitário que representa `Controlled U([control], target)` e permita que $c (V) $ seja definido da mesma maneira.
Em seguida, para um estado arbitrário $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU ^ {\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes U ^ \dagger) \ ket{1} \otimes \ket{\psi}.
\end{align} pela definição de `Controlled`.
Por outro lado, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU ^ \dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c ( V)) (\boldone \otimes U ^ \dagger) \ket{0} \otimes \ket{\psi}.
\end{align} por linearidade, podemos concluir que podemos fatorar $U $ out dessa maneira para todos os Estados de entrada.
Ou seja, $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.
Como o controle de operações pode ser caro em geral, o uso de variantes controladas como `WithC` e `WithCA` pode ajudar a reduzir o número de transmissão functors de controle que precisam ser aplicados.

> [!NOTE]
> Uma outra consequência de fatorar $U $ é que não precisamos nem saber como aplicar o `Controlled` functor ao `U`.
> `ApplyWithCA`, portanto, tem uma assinatura mais fraca do que pode ser esperado:
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

Da mesma forma, <xref:microsoft.quantum.canon.bind> produz operações que aplicam uma sequência de outras operações por vez.
Por exemplo, os seguintes são equivalentes:

```qsharp
H(qubit); X(qubit);
Bind([H, X], qubit);
```

Combinar com padrões de iteração pode tornar isso especialmente útil:

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bind([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>Composição de tempo ordenado ###

Podemos continuar ainda mais pensando no controle de fluxo em termos de aplicativos parciais e funções clássicas e pode modelar conceitos de Quantum ainda mais sofisticados em termos de controle de fluxo clássico.
Essa analogia se torna precisa pelo reconhecimento de que os operadores unitários correspondem exatamente aos efeitos colaterais das operações de chamada, de modo que qualquer decomposição de operadores unitários em termos de outros operadores unitários corresponde à construção de um determinado sequência de chamada para sub-rotinas clássicas que emite instruções para atuar como operadores unitários específicos.
Nessa exibição, `Bind` é precisamente a representação do produto de matriz, uma vez que `Bind([A, B])(target)` é equivalente a `A(target); B(target);`, que, por sua vez, é a sequência de chamada correspondente ao $BA $.

Um exemplo mais sofisticado é a [expansão Trotter – Suzuki](https://arxiv.org/abs/math-ph/0506007v1).
Conforme discutido na seção representação do gerador dinâmico de [estruturas de dados](xref:microsoft.quantum.libraries.data-structures), a expansão Trotter – Suzuki fornece uma maneira particularmente útil de expressar exponencials de matriz.
Por exemplo, aplicar a expansão em sua ordem mais baixa produz isso para qualquer operador $A $ e $B $ de modo que $A = A ^ \dagger $ e $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \lim_{n\to\infty} \left (\exp (i t/n) \exp (i B/n ) \right) ^ n.
\end{align} coloquialmente, isso diz que podemos expandir um estado em $A + B $ em constante evolução em $A $ e $B $ sozinho.
Se representarmos a evolução em $A $ por uma operação `A : (Double, Qubit[]) => Unit` que se aplica $e ^ {i t A} $, a representação da expansão Trotter – Suzuki em termos de reorganizar as sequências de chamada torna-se clara.
Concretamente, dada uma operação `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` de modo que `A = U(0, _, _)` e `B = U(1, _, _)`, podemos definir uma nova operação representando o integral de `U` no tempo $t $ gerando sequências do formulário

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

Neste ponto, agora podemos ter uma razão da expansão Trotter – Suzuki *sem referência à mecânica quantum*.
A expansão é efetivamente um padrão de iteração muito específico motivado por $ \eqref{EQ: Trotter-Suzuki-0} $.
Esse padrão de iteração é implementado por <xref:microsoft.quantum.canon.decomposeintotimestepsca>:

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

A assinatura de `DecomposeIntoTimeStepsCA` segue um padrão comum em Q #, em que coleções podem ser apoiadas por matrizes ou por algo que os elementos de computação em tempo real são representados por tuplas cujos primeiros elementos são `Int` valores que indicam seus comprimentos.

## <a name="putting-it-together-controlling-operations"></a>Juntando-as: controlando as operações ##

Por fim, a Canon baseia-se no `Controlled` functor fornecendo maneiras adicionais de operações de Quantum de condição.
É comum, especialmente em aritmética de Quantum, para operações de condição em Estados de base computacional diferentes de $ \ket{0\cdots 0} $.
Usando as operações de controle e as funções apresentadas acima, podemos obter mais condições de Quantum geral em uma única instrução.
Vamos pular para o modo como <xref:microsoft.quantum.canon.controlledonbitstring> (os parâmetros de tipo Sans), em seguida, dividiremos as partes uma a uma.
A primeira coisa que precisaremos fazer é definir uma operação que realmente faça o trabalho pesado de implementar o controle em Estados de base computacional arbitrários.
No entanto, não chamaremos essa operação diretamente e, portanto, adicionamos `_` ao início do nome para indicar que é uma implementação de outra construção em outro lugar.

```qsharp
operation _ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl),
        controlRegister : Qubit[],
        targetRegister: Qubit[]) 
: Unit 
is Adj + Ctl {
```

Observe que pegamos uma cadeia de caracteres de bits, representada como uma matriz `Bool`, que usamos para especificar o condicionamento que queremos aplicar à operação `oracle` que recebemos.
Como essa operação realmente faz o aplicativo diretamente, também precisamos pegar o controle e os registros de destino, ambos representados aqui como `Qubit[]`.

Em seguida, observamos que o controle do estado de base computacional $ \ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n-1}} $ para uma cadeia de caracteres de bits $ \vec{s} $ pode ser realizado com a transformação de $ \ket{\vec{s}} $ em $ \ket{0\cdots 0} $.
Em particular, $ \ket{\vec{s}} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{0\cdots 0} $.
Como $X ^ {\dagger} = X $, isso implica que $ \ket{0\dots 0} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{\vec{s}} $.
Portanto, podemos aplicar $P = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} $, aplicar `Controlled oracle`e transformar de volta em $ \vec{s} $.
Essa construção é precisamente `ApplyWith`, portanto, escrevemos o corpo da nossa nova operação de acordo:

```qsharp
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

Aqui, usamos <xref:microsoft.quantum.canon.applypaulifrombitstring> para aplicar $P $, parcialmente aplicando seu destino para uso com `ApplyWith`.
No entanto, observe que precisamos transformar o registro de *controle* em nosso formato desejado, portanto, aplicamos parcialmente a operação interna `(Controlled oracle)` no *destino*.
Isso deixa `ApplyWith` atuando para colocar o registro de controle com $P $, exatamente como desejamos.

Neste ponto, poderíamos ser feito, mas está, de alguma forma, desconhecendo que nossa nova operação não "sente", como aplicar o `Controlled` functor.
Portanto, terminamos de definir nosso novo conceito de fluxo de controle escrevendo uma função que usa o Oracle para ser controlado e que retorna uma nova operação.
Dessa forma, nossa nova função parece ser muito parecida com a `Controlled`, ilustrando que podemos facilmente definir novas construções poderosas de fluxo de controle usando Q # e a Canon juntas:

```qsharp
function ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl)) 
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
