---
title: Trabalhar com qubits
description: preencher descrição
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6808a852ee0de7d3a38ea44e9637eeaa6bea382a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867867"
---
# <a name="working-with-qubits"></a>Trabalhar com qubits

Qubits são o objeto fundamental da informação na computação quântica. Para uma introdução geral aos qubits, consulte [a computação quântica,](xref:microsoft.quantum.overview.understanding)e mergulhe mais profundamente na sua representação matemática, consulte [O Qubit](xref:microsoft.quantum.concepts.qubit). 

Este artigo explora como usar e trabalhar com qubits num Q# programa. 

> [!IMPORTANT]
>Nenhuma das declarações discutidas neste artigo é válida dentro do corpo de uma função. Só são válidos dentro das operações.

## <a name="allocating-qubits"></a>Atribuição de Qubits

Como os qubits físicos são um recurso precioso num computador quântico, parte do trabalho do compilador é garantir que estão a ser usados o mais eficientemente possível.
Como tal, tem de dizer Q# para *alocar* qubits para utilização dentro de um determinado bloco de declaração.
Você pode alocar qubits como um único qubit, ou como uma variedade de qubits, conhecido como um *registo*. 

### <a name="clean-qubits"></a>Qubits limpos

Utilize a `using` declaração para alocar novos qubits para utilização durante um bloco de declaração.

A declaração consiste na `using` palavra-chave, seguida de uma ligação em parênteses e do bloco de declaração dentro do qual os `( )` qubits estão disponíveis.
A ligação segue o mesmo padrão que `let` as declarações: ou um único símbolo ou um tuple de símbolos, seguido de um sinal de iguais `=` , e um único valor ou um tuple de *inicializadores correspondentes*.

Os inicializadores estão disponíveis para um único qubit, indicado como `Qubit()` , ou uma matriz de qubits, onde é uma `Qubit[n]` `n` `Int` expressão.
Por exemplo,

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

Quaisquer qubits atribuídos desta forma começam no estado $\ket$ {0} Assim, no exemplo anterior, `auxiliary` é um único qubit no estado $\ket {0} $, e está no estado de `register` cinco qubits $\ket {00000} = \ket {0} \otimes {0} \otimes \otimes \otimes \otimes \ket {0} $.
No final do `using` bloco, quaisquer qubits atribuídos por esse bloco são imediatamente transcilhados e não podem ser usados mais.

> [!WARNING]
> As máquinas-alvo podem reutilizar qubits deallocados e oferecê-los a outros `using` blocos para alocação. Como tal, a máquina-alvo espera que os qubits estejam no estado de $\ket {0} $ imediatamente antes da negociação.
> Sempre que possível, utilize operações unitárias para devolver quaisquer qubits atribuídos a $\ket {0} $.
> Se necessário, pode utilizar a @"microsoft.quantum.intrinsic.reset" operação, que devolve o qubit a $\ket {0} $ medindo-o e realizando condicionalmente uma operação com base no resultado. Tal medição destrói qualquer emaranhado com os qubits restantes e pode, assim, impactar a computação.


### <a name="borrowed-qubits"></a>Qubits emprestados

Utilize a `borrowing` declaração para alocar qubits para uso temporário, que não precisam de estar num estado específico.

Você pode usar qubits emprestados como espaço de arranhão durante uma computação.
Estes qubits geralmente não estão em um estado limpo, isto é, eles não são necessariamente inicializados em um estado conhecido como $\ket {0} $.
Estes são muitas vezes referidos como qubits "sujos" porque o seu estado é desconhecido e pode mesmo ser enredado com outras partes da memória do computador quântico.

A ligação segue o mesmo padrão e regras que a `using` declaração.
Por exemplo,
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
Os qubits emprestados estão num estado desconhecido e ficam fora de alcance no final do bloco de declaração.
O mutuário compromete-se a deixar os qubits no mesmo estado em que estavam quando os pediram emprestado; isto é, o seu estado no início e no fim do bloco de declaração deve ser o mesmo.
Como este estado não é necessariamente um estado clássico, na maioria dos casos, os âmbitos de empréstimo não devem conter medições. 

Ao pedir qubits emprestados, o sistema tenta primeiro preencher o pedido de qubits que estão em uso mas não acedidos durante o corpo da `borrowing` declaração.
Se não houver qubits suficientes, então atribui novos qubits para completar o pedido.

Entre os casos de uso conhecido de qubits sujos estão implementações de portas CNOT multi-controladas que requerem apenas muito poucos qubits e implementação de incrementadores.
Para um exemplo da sua utilização em Q# , consulte [Borrowing Qubits Exemplo](#borrowing-qubits-example) neste artigo, ou o papel [*Factoring usando 2n+2 qubits com multiplicação modular baseada em Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler e Svore 2017) para um algoritmo que utiliza qubits emprestados.

## <a name="intrinsic-operations"></a>Operações Intrínsecas

Uma vez atribuído, pode passar um qubit para funções e operações.
Em certo sentido, isto é tudo o que um Q# programa pode fazer com um qubit, uma vez que as ações que podem ser tomadas são todas definidas como operações.

Este artigo discute algumas operações úteis Q# que pode usar para interagir com qubits.
Para obter mais detalhes sobre estes e outros, consulte [Operações e Funções Intrínsecas.](xref:microsoft.quantum.libraries.standard.prelude) 

Em primeiro lugar, os operadores de Pauli de um único qubit $X$, $Y$, e $Z$ são representados Q# pelas operações intrínsecas, [`X`](xref:microsoft.quantum.intrinsic.x) e , cada uma delas tem tipo [`Y`](xref:microsoft.quantum.intrinsic.y) [`Z`](xref:microsoft.quantum.intrinsic.z) `(Qubit => Unit is Adj + Ctl)` .

Como descrito em [Operações e Funções Intrínsecas,](xref:microsoft.quantum.libraries.standard.prelude)pense em $X$ e, portanto, `X` como uma operação de inversão de marcha ou portão NÃO.
Você pode usar a `X` operação para preparar estados do formulário $\ket{s_0 s_1 \dots s_n}$ para algum fio de bit clássico $s$:

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit
is Adj + Ctl {
    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Remember to reset the qubits before deallocation:
        ResetAll(register);
    }
}
```

> [!TIP]
> Mais tarde, verá formas mais compactas de escrever esta operação que não requerem fluxo manual de controlo.

Também pode preparar estados como $\ket{+} = \left(\ket {0} + \ket {1} \ket \right) / \sqrt {2} $ e $\ket {-} = \left(\ket {0} \ket {1} \right) / \sqrt {2} $ usando a transformação Hadamard $H$, que é representada Q# pela operação intrínseca [`H`](xref:microsoft.quantum.intrinsic.h) (também do tipo (Qubit => Unidade é Aj + Ctl)):)):

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString in the earlier example.
    PrepareBitString(bitstring, register);
    // Next, use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the desired state.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>Medições

As medições de qubits individuais podem ser realizadas em diferentes bases, cada uma representada por um eixo Pauli na [esfera bloch.](xref:microsoft.quantum.glossary#bloch-sphere)
A *base computacional* refere-se à `PauliZ` base, e é a base mais comum utilizada para a medição.

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a>Meça um único qubit na `PauliZ` base

Utilize a [`M`](xref:microsoft.quantum.intrinsic.m) operação, que é uma operação não unitária incorporada, para medir um único qubit na `PauliZ` base e atribuir um valor clássico ao resultado.
`M`tem um tipo de retorno reservado, `Result` que só pode tomar valores ou corresponder aos `Zero` `One` estados medidos $\ket {0} $ ou $\ket {1} $ - indicando que o resultado já não é um estado quântico.

Um exemplo simples é a seguinte operação, que atribui um qubit no estado $\ket {0} $, em seguida, aplica uma operação Hadamard `H` a ele e mede o resultado na `PauliZ` base.

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // Apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, return the result of the measurement.
        return result;
    }
}
```

### <a name="measure-one-or-more-qubits-in-specific-bases"></a>Medir um ou mais qubits em bases específicas

Para medir um conjunto de um ou mais qubits em bases específicas, pode utilizar a [`Measure`](xref:microsoft.quantum.intrinsic.measure) operação.

As entradas `Measure` são uma matriz de `Pauli` tipos (por exemplo, `[PauliX, PauliZ, PauliZ]` ) e uma matriz de qubits.

Um exemplo um pouco mais complicado é dado pela seguinte operação, que devolve o valor Boolean `true` se todos os qubits num registo de tipo `Qubit[]` estiverem no estado zero quando medidos numa base Pauli especificada, e que retorna `false` de outra forma.

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

Note que este exemplo ainda só funciona `Measure` em qubits individuais um de cada vez, mas a operação pode ser estendida a medições articulares em múltiplos qubits.

## <a name="borrowing-qubits-example"></a>Exemplo de Qubits emprestado

Existem exemplos no cânone que usam a `borrowing` palavra-chave, como a seguinte função `MultiControlledXBorrow` . Se `controls` denotar os qubits de controlo para adicionar a uma `X` operação, então o número de [ancillas sujas adicionadas](xref:microsoft.quantum.glossary#ancilla) por esta implementação é `Length(controls)-2` .

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

Note-se que este exemplo utilizou extensivamente o `With` combinador, na sua forma aplicável às operações que suportam, por exemplo, `WithA` .
Este é um bom estilo de programação, porque adicionar controlo às estruturas que envolvem `With` o controlo de propagações apenas para o funcionamento interno.
Note-se ainda que, para além `body` da operação, foi explicitamente fornecida uma implementação `controlled` do corpo da operação, em vez de recorrer a um `controlled auto` comunicado.
A razão para isso é que, devido à estrutura do circuito, é fácil adicionar mais controlos, o que é benéfico em comparação com a adição de controlo a cada portão do `body` . 

É instrutivo comparar este código com outra função canónica `MultiControlledXClean` que alcança o mesmo objetivo de implementar uma operação controlada por multi-animais, no `X` entanto, que utiliza vários qubits limpos usando o `using` mecanismo. 

## <a name="next-steps"></a>Passos seguintes

Saiba mais sobre [o Control Flow](xref:microsoft.quantum.guide.controlflow) em Q# .