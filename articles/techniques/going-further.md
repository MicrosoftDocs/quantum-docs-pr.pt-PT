---
title: 'Técnicas de Q # – indo além | Microsoft Docs'
description: 'Técnicas de Q #-aprofundando'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4677b0f9c4f64a9c1bc46d34e8a883dc006ba8f0
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183306"
---
# <a name="going-further"></a>Indo mais #

Agora que você já viu como escrever programas de Quantum interessantes em Q #, esta seção vai além, apresentando alguns tópicos mais avançados que devem ser úteis no futuro.

<!-- Moved Debugging and Testing Quantum Programs section to a separate article -->

## <a name="generic-operations-and-functions"></a>Operações e funções genéricas ##

> [!TIP]
> Esta seção pressupõe alguma familiaridade básica com [genéricos C# ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), em [genéricos, em F# ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/) [ C++ modelos](https://docs.microsoft.com/cpp/cpp/templates-cpp), ou abordagens semelhantes à metaprogramação em outras linguagens.

Muitas funções e operações que desejamos definir não dependem muito dos tipos de suas entradas, mas, em vez disso, apenas usam implicitamente seus tipos por meio de alguma outra função ou operação.
Por exemplo, considere o conceito de *mapa* comum a muitas linguagens funcionais; dada uma função $f (x) $ e uma coleção de valores $\{x_1, x_2, \dots, x_n\}$, MAP retorna uma nova coleção $\{f (x_1), f (x_2), \dots, f (x_n)\}$.
Para implementar isso em Q #, podemos aproveitar essas funções como primeira classe.
Vamos escrever um exemplo rápido de `Map`, usando ★ como um espaço reservado enquanto descobrimos quais tipos precisamos.

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Observe que essa função parece muito boa, independentemente de quais tipos reais substituímos.
Um mapa de inteiros para Paulis, por exemplo, parece muito o mesmo que um mapa de números de ponto flutuante para cadeias de caracteres:

```qsharp
function MapIntsToPaulis(fn : Int -> Pauli, values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : Double -> String, values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Em princípio, poderíamos escrever uma versão do `Map` para cada par de tipos que encontramos, mas isso apresenta uma série de dificuldades.
Por exemplo, se encontrarmos um bug no `Map`, devemos garantir que a correção seja aplicada uniformemente em todas as versões do `Map`.
Além disso, se construirmos uma nova tupla ou UDT, agora devemos também construir um novo `Map` para acompanhar o novo tipo.
Embora isso seja indevido a um pequeno número dessas funções, à medida que coletamos cada vez mais funções da mesma forma que `Map`, o custo da introdução de novos tipos torna-se razoavelmente grande em ordem razoavelmente curta.

No entanto, grande parte dessa dificuldade faz com que não tenhamos dado ao compilador as informações de que ele precisa para reconhecer como as diferentes versões do `Map` estão relacionadas.
Efetivamente, queremos que o compilador trate `Map` como um tipo de função matemática de *tipos* q # para funções q #.
Essa noção é formalizada permitindo que funções e operações tenham *parâmetros de tipo*, bem como seus parâmetros de tupla comuns.
Nos exemplos acima, desejamos considerar `Map` como tendo parâmetros de tipo `Int, Pauli` no primeiro caso e `Double, String` no segundo caso.
Na maior parte, esses parâmetros de tipo podem ser usados como se fossem tipos comuns: usamos valores de parâmetros de tipo para criar matrizes e tuplas, chamar funções e operações e atribuir a variáveis comuns ou mutáveis.

> [!NOTE]
> O caso mais extremo de dependência indireta é o de qubits, em que um programa Q # não pode contar diretamente com a estrutura do tipo de `Qubit`, mas **deve** passar esses tipos para outras operações e funções.

Retornando ao exemplo acima, podemos ver que precisamos que `Map` tenha parâmetros de tipo, um para representar a entrada para `fn` e outro para representar a saída de `fn`.
Em Q #, isso é escrito pela adição de colchetes angulares (`<>`, não brakets $ \braket{}$!) após o nome de uma função ou operação em sua declaração e listando cada parâmetro de tipo.
O nome de cada parâmetro de tipo deve começar com um `'`de tique, indicando que ele é um parâmetro de tipo e não um tipo comum (também conhecido como um tipo *concreto* ).
Por `Map`, portanto, escrevemos:

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Observe que a definição de `Map<'Input, 'Output>` é muito semelhante às versões que escrevemos antes.
A única diferença é que nós informamos explicitamente o compilador de que `Map` não depende diretamente do que `'Input` e `'Output` são, mas funciona para dois tipos usando-os indiretamente por meio de `fn`.
Depois de definirmos `Map<'Input, 'Output>` dessa forma, podemos chamá-lo como se fosse uma função comum:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Escrever funções e operações genéricas é um lugar em que "tupla-in-out" é uma maneira muito útil de pensar em funções e operações do Q #.
> Como cada função usa exatamente uma entrada e retorna exatamente uma saída, uma entrada do tipo `'T -> 'U` corresponde a *qualquer* função Q # qualquer.
> Da mesma forma, qualquer operação pode ser passada para uma entrada do tipo `'T => 'U`.

Como um segundo exemplo, considere o desafio de escrever uma função que retorne a composição de duas outras funções:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Aqui, devemos especificar exatamente o que `A`, `B`e `C` são, portanto, limitando seriamente o utilitário de nossa nova função `Compose`.
Afinal, `Compose` depende apenas `A`, `B`e `C` *via* `innerFn` e `outerFn`.
Como alternativa, podemos adicionar parâmetros de tipo a `Compose` que indicam que ele funciona para *qualquer* `A`, `B`e `C`, contanto que esses parâmetros correspondam aos esperados por `innerFn` e `outerFn`:

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

As bibliotecas padrão de Q # fornecem uma variedade de operações e funções parametrizadas por tipo para facilitar o expressar o fluxo de controle de ordem mais alta.
Eles são abordados mais detalhadamente no [Guia de biblioteca padrão do Q #](xref:microsoft.quantum.libraries.standard.intro).

## <a name="borrowing-qubits"></a>Qubits emprestando ##

O mecanismo de empréstimo permite a alocação de qubits que pode ser usada como espaço transitório durante uma computação. Esses qubits geralmente não estão em um estado limpo, ou seja, eles não são necessariamente inicializados em um estado conhecido, como $ \ket{0}$. Um também fala sobre o qubits "sujo", pois seu estado é desconhecido e pode até mesmo ser confusas com outras partes da memória do computador Quantum. Entre os casos de uso conhecidos de qubits sujos estão implementações de Gates de CNOT de vários controle que exigem apenas poucos qubits e implementação de incrementais.

Na Canon, há exemplos que usam a palavra-chave `borrowing`, por exemplo, a função `MultiControlledXBorrow` definida abaixo.
Se `controls` denota o qubits de controle que deve ser adicionado a uma operação `X`, um geral de `Length(controls)-2` muitos ancillas sujos serão adicionados por essa implementação.

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

Observe que o uso extensivo do `With` combinador---em seu formato aplicável a operações que dão suporte a adpositivo, ou seja, `WithA`---foi feita neste exemplo, o que é bom estilo de programação como adicionar controle a estruturas que envolvem apenas `With` propaga o controle para a operação interna. Observe ainda que, além do `body` da operação, uma implementação do `controlled` corpo da operação foi explicitamente fornecida, em vez de recorrer a uma instrução `controlled auto`. O motivo disso é que sabemos da estrutura do circuito como adicionar com facilidade mais controles, o que é benéfico em comparação à adição de controle a cada porta individual na `body`. 

É instrutivo comparar esse código com outra função Canon `MultiControlledXClean` que atinge o mesmo objetivo de implementar uma operação de `X` com controle de multiplicação, no entanto, que usa várias qubits limpas usando o mecanismo de `using`. 
