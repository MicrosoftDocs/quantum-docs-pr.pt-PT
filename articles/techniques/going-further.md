---
title: Ir mais longe - Q# técnicas / Microsoft Docs
description: Ir mais longe - Técnicas Q#
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.going-further
ms.openlocfilehash: 41713827a93d2cc97e198fa4ad377012c846cf8b
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036241"
---
# <a name="going-further"></a>Indo mais longe #

Agora que já viu como escrever programas quânticos interessantes em Q#, esta secção vai mais longe introduzindo alguns tópicos mais avançados que devem ser úteis para avançar.


## <a name="generic-operations-and-functions"></a>Operações e Funções Genéricas ##

> [!TIP]
> Esta secção assume alguma familiaridade básica com [genéricos C#em, ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics) [genéricos em, F# ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/) [ C++ modelos,](https://docs.microsoft.com/cpp/cpp/templates-cpp)ou abordagens semelhantes à metaprogramação em outras línguas.

Muitas funções e operações que podemos querer definir não dependem muito dos tipos das suas inputs, mas apenas utilizam implicitamente os seus tipos através de outra função ou operação.
Por exemplo, considere o conceito de *mapa* comum a muitas línguas funcionais; dada uma função $f(x)$ e uma coleção de valores $\{x_1, x_2, \dots, x_n\}$, o mapa devolve uma nova coleção $\{f(x_1), f(x_2), \dots, f(x_n)\}$.
Para implementar isto em Q#, podemos tirar partido dessas funções são de primeira classe.
Vamos escrever um exemplo rápido de `Map`, usando ★ como espaço reservado enquanto descobrimos que tipos precisamos.

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Note que esta função parece muito a mesma, independentemente dos tipos reais em que substituímos.
Um mapa de inteiros a Paulis, por exemplo, parece muito parecido com um mapa de números de pontos flutuantes a cordas:

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Em princípio, poderíamos escrever uma versão de `Map` para cada par de tipos que encontramos, mas isso introduz uma série de dificuldades.
Por exemplo, se encontrarmos um bug em `Map`, então temos de garantir que a correção seja aplicada uniformemente em todas as versões de `Map`.
Além disso, se construirmos um novo tuple ou UDT, então temos agora de construir também um novo `Map` para acompanhar o novo tipo.
Embora isto seja tratável para um pequeno número de tais funções, à medida que recolhemos cada vez mais funções da mesma forma que `Map`, o custo da introdução de novos tipos torna-se irracionalmente grande em ordem bastante curta.

Grande parte desta dificuldade resulta, no entanto, do facto de não termos dado ao compilador a informação de que necessita para reconhecer como estão relacionadas as diferentes versões de `Map`.
Efetivamente, queremos que o compilador trate `Map` como uma espécie de função matemática dos *tipos* Q# para as funções Q#.
Esta noção é formalizada permitindo que funções e operações tenham *parâmetros de tipo,* bem como os seus parâmetros normais de tuple.
Nos exemplos acima referidos, queremos pensar em `Map` como tendo parâmetros de tipo `Int, Pauli` no primeiro caso e `Double, String` no segundo caso.
Na maior parte dos casos, estes parâmetros de tipo podem então ser usados como se fossem tipos comuns: usamos valores de parâmetros de tipo para fazer matrizes e tuples, funções de chamada e operações, e atribuir a variáveis ordinárias ou mutáveis.

> [!NOTE]
> O caso mais extremo de dependência indireta é o dos qubits, onde um programa Q# não pode depender diretamente da estrutura do tipo `Qubit`, mas **deve** passar esses tipos para outras operações e funções.

Voltando ao exemplo acima, podemos ver que precisamos de `Map` para ter parâmetros de tipo, um para representar a entrada para `fn` e outro para representar a saída de `fn`.
Em Q#, isto é escrito adicionando suportes de ângulo (isto é `<>`, não travões $\braket{}$!) após o nome de uma função ou operação na sua declaração, e listando cada parâmetro de tipo.
O nome de cada parâmetro de tipo deve começar com um tique `'`, indicando que se trata de um parâmetro tipo e não de um tipo ordinário (também conhecido como tipo *de concreto).*
Para `Map`, escrevemos assim:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Note que a definição de `Map<'Input, 'Output>` se parece extremamente com as versões que escrevemos anteriormente.
A única diferença é que informamos explicitamente o compilador de que `Map` não depende diretamente do que `'Input` e `'Output` são, mas funciona para qualquer dois tipos, utilizando-os indiretamente através `fn`.
Uma vez definido`Map<'Input, 'Output>` desta forma, podemos chamá-lo como se fosse uma função comum:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Escrever funções e operações genéricas é um lugar onde "tuple-in tuple-out" é uma forma muito útil de pensar sobre as funções e operações q#.
> Uma vez que cada função requer exatamente uma entrada e devolve exatamente uma saída, uma entrada de tipo `'T -> 'U` corresponde a *qualquer* função Q# qualquer.
> Da mesma forma, qualquer operação pode ser passada para uma entrada de tipo `'T => 'U`.

Como segundo exemplo, considere o desafio de escrever uma função que retorne a composição de duas outras funções:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Aqui, temos de especificar exatamente quais são os `A`, `B`e `C`, limitando assim severamente a utilidade da nossa nova função `Compose`.
Afinal, `Compose` só depende de `A`, `B`e `C` *via* `innerFn` e `outerFn`.
Como alternativa, podemos, então, adicionar parâmetros de tipo a `Compose` que indiquem que funciona para *qualquer* `A`, `B`e `C`, desde que estes parâmetros correspondam aos esperados por `innerFn` e `outerFn`:

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

As bibliotecas padrão Q# fornecem uma gama dessas operações e funções paramétricas tipo para facilitar o fluxo de controlo de ordem mais fácil de expressar.
Estes são discutidos mais no guia padrão da [biblioteca Q#](xref:microsoft.quantum.libraries.standard.intro).

## <a name="borrowing-qubits"></a>Qubits emprestados ##

O mecanismo de empréstimo permite a atribuição de qubits que podem ser usados como espaço de risco durante um cálculo. Estes qubits geralmente não estão em um estado limpo, ou seja, não são necessariamente inicializados em um estado conhecido como $\ket{0}$. Fala-se também de qubits "sujos", uma vez que o seu estado é desconhecido e pode até ser enredado com outras partes da memória do computador quântico. Entre os casos de utilização conhecidos de qubits sujos estão implementações de portões CNOT multi-controlados que requerem apenas muito poucos qubits e implementação de incrementadores.

No cândia existem exemplos que usam a palavra-chave `borrowing`, por exemplo, a função `MultiControlledXBorrow` definida abaixo.
Se `controls` denota os qubits de controlo que devem ser adicionados a uma operação `X`, então uma geral de `Length(controls)-2` muitas auxiliares sujas serão adicionadas por esta implementação.

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

Note-se que foi feita uma utilização extensiva do `With` combinador---na sua forma aplicável às operações que suportam a adjoint, ou seja, `WithA`---foi feita neste exemplo, que é um bom estilo de programação como um bom estilo de programação como um bom estilo de programação como um bom estilo de programação como um bom estilo de programação como um bom estilo de programação como um bom estilo de programação como um bom estilo de programação como um bom estilo de programação como a adição de controlo às estruturas que envolvem `With` apenas propaga o controlo à operação interna. Note-se ainda que, para além do `body` da operação, foi explicitamente fornecida uma execução do organismo `controlled` da operação, em vez de recorrer a uma declaração `controlled auto`. A razão para isso é que sabemos pela estrutura do circuito como adicionar facilmente mais controlos que são benéficos em comparação com a adição de controlo a cada portão individual do `body`. 

É instrutivo comparar este código com outra função canon `MultiControlledXClean` que atinja o mesmo objetivo de implementar uma operação de `X` controlada por multiplicação, no entanto, que utiliza vários qubits limpos utilizando o mecanismo `using`. 
