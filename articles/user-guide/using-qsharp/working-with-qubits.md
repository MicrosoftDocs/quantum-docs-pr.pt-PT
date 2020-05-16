---
title: Trabalhar com qubits
description: preencher descrição
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: e89b9ccfe2a0796e01eedfc99f7ce71038d85f38
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430939"
---
# <a name="working-with-qubits"></a>Trabalhar com qubits

Tendo agora visto uma variedade de diferentes partes da língua Q#, vamos entrar no espesso dela e ver como usar os próprios qubits.

Note que nenhuma destas declarações é permitida dentro do corpo de uma função.
Só são válidos dentro das operações.

## <a name="allocating-qubits"></a>Alocadoqubits

### <a name="clean-qubits"></a>Qubits limpos

A `using` declaração é utilizada para *alocar* novos qubits para utilização durante um bloco de declaração.

A declaração consiste na palavra-chave `using` , seguida de um parêntese aberto , uma `(` ligação, um parêntese próximo `)` , e o bloco de declaração dentro do qual estarão disponíveis os qubits.
A ligação segue o mesmo padrão que `let` as declarações: um único símbolo ou um tuple de símbolos, seguido de um sinal `=` igual, e um único valor ou uma túnica correspondente de *iniciais*.

Os iniciais estão disponíveis para um único qubit, indicado como `Qubit()` , ou uma variedade de qubits, onde é uma `Qubit[n]` `n` `Int` expressão.
Por exemplo,

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

Quaisquer qubits atribuídos desta forma começam no estado $\ket {0} $; no exemplo acima, `register` está assim no estado $\ket = {00000} {0} \ket \otimes {0} \otimes \cdots \otimes \ket \ket \ket \otimes \ket \ket \ket {0} \ket $.
No final do `using` bloco, quaisquer qubits atribuídos por esse bloco são imediatamente transferidos e não podem ser utilizados mais.

> [!WARNING]
> As máquinas-alvo esperam que os qubits estejam no estado $\ket {0} $ imediatamente antes da desalocação, para que possam ser reutilizados e oferecidos a outros `using` blocos para alocação.
> Sempre que possível, utilize operações unitárias para devolver quaisquer qubits atribuídos a $\ket {0} $.
> Se necessário, a @"microsoft.quantum.intrinsic.reset" operação pode ser usada para medir um qubit em vez disso, e para usar esse resultado de medição para garantir que o qubit medido seja devolvido a $\ket {0} $. Tal medição destruirá qualquer emaranhado com os restantes qubits e pode, assim, impactar o cálculo.


### <a name="borrowed-qubits"></a>Qubits emprestados

A `borrowing` declaração é utilizada para disponibilizar qubits para uso temporário, que não necessitam de estar num estado específico.

O mecanismo de empréstimo permite a atribuição de qubits que podem ser usados como espaço de risco durante um cálculo.
Estes qubits geralmente não estão em um estado limpo, ou seja, não são necessariamente inicializados em um estado conhecido como $\ket {0} $.
Estes são frequentemente referidos como qubits "sujos" porque o seu estado é desconhecido e pode até ser enredado com outras partes da memória do computador quântico.

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
Os qubits emprestados estão num estado desconhecido e saem do âmbito no final do bloco de declaração.
O mutuário compromete-se a deixar os qubits no mesmo estado em que estavam quando foram emprestados, ou seja, o seu estado no início e no final do bloco de declaração deverá ser o mesmo.
Este Estado, em particular, não é necessariamente um estado clássico, de tal forma que, na maioria dos casos, os âmbitos de empréstimo não devem conter medições. 

Ao pedir qubits emprestados, o sistema tentará primeiro preencher o pedido de qubits que estão em uso, mas que não são acedidos durante o corpo da `borrowing` declaração.
Se não houver qubits suficientes, então irá alocar novos qubits para completar o pedido.


Entre os casos de utilização conhecidos de qubits sujos estão implementações de portões CNOT multi-controlados que requerem apenas muito poucos qubits e implementação de incrementadores.
Veja o Exemplo de [Empréstimos qubits](#borrowing-qubits-example) abaixo para ver um exemplo da sua utilização em Q#, ou o papel [*Factoring usando 2n+2 qubits com multiplicação modular baseada em Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler e Svore 2017) para um algoritmo que utiliza qubits emprestados.


## <a name="intrinsic-operations"></a>Operações Intrínsecas

Uma vez atribuído, um qubit pode então ser passado para funções e operações.
Em certo sentido, isto é tudo o que um programa Q# pode fazer com um qubit, uma vez que as ações que podem ser tomadas são definidas como operações.
Veremos estas operações mais detalhadamente em [Operações e Funções Intrínsecas,](xref:microsoft.quantum.libraries.standard.prelude)mas por enquanto, mencionamos algumas operações úteis que podem ser usadas para interagir com qubits.

Em primeiro lugar, os operadores de pauli de um único qubit $X$, $Y$, e $Z$ são representados em Q# pelas operações intrínsecas `X` , e , cada um dos quais tem tipo `Y` `Z` `(Qubit => Unit is Adj + Ctl)` .
Como descrito em [Operações e Funções Intrínsecas,](xref:microsoft.quantum.libraries.standard.prelude)podemos pensar em $X$ e, portanto, `X` como uma operação de flip bit ou não portão.
A `X` operação permite-nos preparar estados do formulário $\ket{s_0 s_1 \dots s_n}$ para uma série clássica $s$:

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
> Mais tarde, veremos formas mais compactas de escrever esta operação que não requerem controlo manual de fluxos.

Também podemos preparar estados como $\ket{+} = \left(\ket {0} + \ket {1} \right) / \sqrt {2} $ e $\ket {-} = \left (\ket {0} - \ket {1} \direita) / \sqrt {2} $ através da transformação hadamard $H$, que está representada em Q# pela operação intrínseca `H : (Qubit => Unit is Adj + Ctl)` :

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

Utilizando a `Measure` operação, que é uma operação não unitária incorporada, podemos extrair informação clássica de um objeto de tipo `Qubit` e atribuir um valor clássico como resultado, que tem um tipo `Result` reservado, indicando que o resultado já não é um estado quântico.
A entrada `Measure` é um eixo Pauli na esfera bloch, representado por um valor de tipo `Pauli` (por `PauliX` exemplo) e um valor de `Qubit` tipo.

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

Um exemplo um pouco mais complicado é dado pela seguinte operação, que devolve o valor `true` Booleanse se todos os qubits num registo de tipo `Qubit[]` estiverem no estado zero quando medidos numa base pauli especificada, e que retorna de `false` outra forma.

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

No cândia existem exemplos que utilizam a `borrowing` palavra-chave, por exemplo, a função `MultiControlledXBorrow` definida abaixo.
Se `controls` denotar os qubits de controlo que devem ser adicionados a uma `X` operação, uma geral de `Length(controls)-2` muitas auxiliares sujas serão adicionadas por esta implementação.

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

Note-se que foi feita ---este exemplo uma utilização extensiva do `With` combinador---na sua forma aplicável às operações que suportam a djoint, ou seja, `WithA` ---foi feita neste exemplo.
Este é um bom estilo de programação, porque adicionar controlo às estruturas que envolvem `With` propagates controla apenas ao funcionamento interno.
Note ainda que, para além `body` da operação, foi expressamente fornecida uma execução do corpo da operação, em vez de `controlled` recorrer a um `controlled auto` comunicado.
A razão para isso é que sabemos pela estrutura do circuito como adicionar facilmente mais controlos que são benéficos em comparação com a adição de controlo a cada portão individual do `body` . 

É instrutivo comparar este código com outra função canon `MultiControlledXClean` que alcança o mesmo objetivo de implementar uma operação controlada por `X` multiplicação, no entanto, que utiliza vários qubits limpos utilizando o `using` mecanismo. 

## <a name="whats-next"></a>O que se segue?
Saiba mais sobre [o Control Flow](xref:microsoft.quantum.guide.controlflow) em Q#.