---
title: Trabalhar com qubits
description: preencher descrição
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 0deb0729a88c49798f32a22a943b935d383c570b
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327548"
---
# <a name="working-with-qubits"></a>Trabalhar com qubits

Tendo visto agora uma variedade de diferentes partes da língua Q#, vamos entrar no espesso dela e ver como usar os próprios qubits.

Note que nenhuma destas declarações é permitida dentro do corpo de uma função.
Só são válidos dentro das operações.

## <a name="allocating-qubits"></a>Atribuição de Qubits

### <a name="clean-qubits"></a>Qubits limpos

A `using` declaração é usada para *alocar* novos qubits para uso durante um bloco de declaração.

A declaração consiste na palavra-chave `using` , seguida de um parênteses aberto , uma `(` ligação, um parênteses `)` próximos , e o bloco de declaração dentro do qual os qubits estarão disponíveis.
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

Quaisquer qubits atribuídos desta forma começam no estado de $\ket {0} $; no exemplo acima, `register` está assim no estado $\ket = {00000} \ket {0} \otimes {0} \otimes \otimes \otimes \otimes \otimes \ket {0} $.
No final do `using` bloco, quaisquer qubits atribuídos por esse bloco são imediatamente transcilhados e não podem ser usados mais.

> [!WARNING]
> As máquinas-alvo esperam que os qubits estejam no estado de $\ket {0} $ imediatamente antes da negociação, para que possam ser reutilizados e oferecidos a outros `using` blocos para alocação.
> Sempre que possível, utilize operações unitárias para devolver quaisquer qubits atribuídos a $\ket {0} $.
> Se necessário, a @"microsoft.quantum.intrinsic.reset" operação pode ser usada para medir um qubit em vez disso, e para utilizar esse resultado de medição para garantir que o qubit medido seja devolvido a $\ket {0} $. Tal medição destruirá qualquer emaranhado com os qubits restantes e poderá, assim, impactar a computação.


### <a name="borrowed-qubits"></a>Qubits emprestados

A `borrowing` declaração é utilizada para disponibilizar qubits para uso temporário, que não precisam de estar num determinado estado.

O mecanismo de empréstimo permite a atribuição de qubits que podem ser usados como espaço de risco durante um cálculo.
Estes qubits geralmente não estão em estado limpo, ou seja, não são necessariamente inicializados num estado conhecido como $\ket {0} $.
Estes são muitas vezes referidos como qubits "sujos" porque o seu estado é desconhecido e pode mesmo ser enredado com outras partes da memória do computador quântico.

A ligação segue o mesmo padrão e regras que a de um `using` comunicado.
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
O mutuário compromete-se a deixar os qubits no mesmo estado em que estavam quando foram emprestados, ou seja, o seu estado no início e no final do bloco de declaração deverá ser o mesmo.
Este Estado, em particular, não é necessariamente um estado clássico, tal como, na maioria dos casos, os âmbitos de empréstimo não devem conter medições. 

Ao pedir qubits emprestados, o sistema tentará primeiro preencher o pedido de qubits que estão em uso mas que não são acedidos durante o corpo da `borrowing` declaração.
Se não houver qubits suficientes, então irá alocar novos qubits para completar o pedido.


Entre os casos de uso conhecido de qubits sujos estão implementações de portas CNOT multi-controladas que requerem apenas muito poucos qubits e implementação de incrementadores.
Veja o [Exemplo de Qubits Emprestado](#borrowing-qubits-example) abaixo para ver um exemplo da sua utilização em Q#, ou o papel [*Factoring usando 2n+2 qubits com multiplicação modular baseada em Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler e Svore 2017) para um algoritmo que utiliza qubits emprestados.


## <a name="intrinsic-operations"></a>Operações Intrínsecas

Uma vez atribuído, um qubit pode então ser passado para funções e operações.
Em certo sentido, isto é tudo o que um programa Q# pode fazer com um qubit, uma vez que as ações que podem ser tomadas são todas definidas como operações.
Veremos estas operações com mais detalhes em [Operações e Funções Intrínsecas,](xref:microsoft.quantum.libraries.standard.prelude)mas por enquanto, mencionamos algumas operações úteis que podem ser usadas para interagir com qubits.

Em primeiro lugar, os operadores de Pauli de um único qubit $X$, $Y$, e $Z$ são representados em Q# pelas operações intrínsecas, `X` e , cada um dos quais tem tipo `Y` `Z` `(Qubit => Unit is Adj + Ctl)` .
Como descrito em [Operações e Funções Intrínsecas, podemos](xref:microsoft.quantum.libraries.standard.prelude)pensar em $X$ e, portanto, `X` como uma operação de inversão de marcha ou portão NÃO.
A `X` operação permite-nos preparar estados do formulário $\ket{s_0 s_1 \dots s_n}$ para uma corda clássica $s$:

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
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> Mais tarde, veremos formas mais compactas de escrever esta operação que não requerem controlo manual do fluxo.

Também podemos preparar estados como $\ket{+} = \left(\ket {0} + \ket {1} \ket \right) / \sqrt {2} $ e $\ket {-} = \left (\ket {0} - \ket {1} \right) / \sqrt {2} $ usando a transformação Hadamard $H$, que é representada em Q# pela operação intrínseca `H : (Qubit => Unit is Adj + Ctl)` :

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>Medições

Utilizando a `Measure` operação, que é uma operação não-unitária intrínseca incorporada, podemos extrair informação clássica de um objeto de tipo `Qubit` e atribuir um valor clássico como resultado, que tem um tipo `Result` reservado, indicando que o resultado já não é um estado quântico.
A entrada `Measure` é um eixo Pauli na esfera Bloch, representado por um valor de tipo `Pauli` (por `PauliX` exemplo) e um valor de tipo `Qubit` .

Um exemplo simples é a seguinte operação, que atribui um qubit no estado $\ket {0} $, em seguida, aplica uma operação Hadamard `H` a ele e mede o resultado na `PauliZ` base.

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

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

## <a name="borrowing-qubits-example"></a>Exemplo de Qubits emprestado

No cânone existem exemplos que usam a `borrowing` palavra-chave, por exemplo a função `MultiControlledXBorrow` definida abaixo.
Se `controls` denotar os qubits de controlo que devem ser adicionados a uma `X` operação, então um total de `Length(controls)-2` muitas ancillas sujas serão adicionados por esta implementação.

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

Note-se que o uso extensivo do `With` combinador--- na sua forma aplicável para operações que suportam adjacentes, ou seja, `WithA` ---foi feito neste exemplo.
Este é um bom estilo de programação, porque adicionar controlo às estruturas que envolvem `With` o controlo de propagações apenas para o funcionamento interno.
Além disso, note-se que aqui, para além `body` da operação, foi explicitamente fornecida uma implementação `controlled` do corpo da operação, em vez de recorrer a um `controlled auto` comunicado.
A razão para isso é que sabemos pela estrutura do circuito como adicionar facilmente mais controlos que são benéficos em comparação com a adição de controlo a cada portão individual do `body` . 

É instrutivo comparar este código com outra função canónica `MultiControlledXClean` que alcança o mesmo objetivo de implementar uma operação controlada por multi-animais, no `X` entanto, que utiliza vários qubits limpos usando o `using` mecanismo. 

## <a name="next-steps"></a>Próximos passos

Saiba mais sobre [o Control Flow](xref:microsoft.quantum.guide.controlflow) em Q#.