---
title: Trabalhando com qubits | Microsoft Docs
description: Trabalhando com qubits
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: 477b358c3eba58b62926b4e9094770c9741cac92
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864258"
---
# <a name="working-with-qubits"></a>Trabalhando com qubits #

Agora que já vi uma variedade de diferentes partes da linguagem Q #, vamos nos aprofundar em tudo e ver como usar o qubits em si.

## <a name="allocating-qubits"></a>Alocando qubits ##

Primeiro, para obter um qubit que possamos usar em Q #, *alocamos* qubits em um bloco de `using`:

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

Qualquer qubits alocado dessa maneira começa no $ \ket{0}$ State; no exemplo acima, `register` é, portanto, no estado $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.
No final do bloco de `using`, qualquer qubits alocada por esse bloco será imediatamente desalocada e não poderá mais ser usada.

> [!WARNING]
> Os computadores de destino esperam que qubits estejam no $ \ket{0}$ State imediatamente antes da desalocação, para que possam ser reutilizados e oferecidos a outros blocos de `using` para alocação.
> Sempre que possível, use operações de unitário para retornar qualquer qubits alocado para $ \ket{0}$.
> Se necessário, a operação de @"microsoft.quantum.intrinsic.reset" pode ser usada para medir um qubit em vez disso e usar esse resultado de medida para garantir que o qubit medido seja retornado para $ \ket{0}$. Essa medida destruirá qualquer Entanglement com a qubits restante e, portanto, poderá afetar a computação. 

## <a name="intrinsic-operations"></a>Operações intrínsecas ##

Uma vez alocada, um qubit pode ser passado para funções e operações.
De certa forma, isso é tudo o que um programa Q # pode fazer com um qubit, pois as ações que podem ser executadas são todas definidas como operações.
Veremos essas operações com mais detalhes em [operações intrínsecas e funções](xref:microsoft.quantum.libraries.standard.prelude), mas, por enquanto, mencionamos algumas operações úteis que podem ser usadas para interagir com o qubits.

Primeiro, os operadores de Pauli qubit $X $, $Y $ e $Z $ são representados em Q # pelas operações intrínsecas `X`, `Y`e `Z`, cada uma delas com o tipo `(Qubit => Unit is Adj + Ctl)`.
Conforme descrito em [operações e funções intrínsecas](xref:microsoft.quantum.libraries.standard.prelude), podemos considerar $X $ e, portanto, `X` como uma operação de inversão de bits ou não de porta.
Isso nos permite preparar Estados do formulário $ \ket{s_0 s_1 \dots s_n} $ para uma cadeia de caracteres de bits clássica $s $:

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

operation Example() : Unit {

    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
    }
}
```

> [!TIP]
> Mais tarde, veremos mais formas compactadas de gravar essa operação que não exigem controle de fluxo manual.

Também podemos preparar Estados como $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ e $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ usando a transformação Hadamard $H $, que é representada em Q # pela operação intrínseca `H : (Qubit => Unit is Adj + Ctl)`:

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

## <a name="measurements"></a>Medições ##

Usando a operação `Measure`, que é uma operação não-unitário intrínseca interna, podemos extrair informações clássicas de um objeto do tipo `Qubit` e atribuir um valor clássico como resultado, que tem um tipo reservado `Result`, indicando que o resultado não é mais um estado Quantum. A entrada para `Measure` é um eixo Pauli na esfera Bloch, representado por um objeto do tipo `Pauli` (ou seja, por instância `PauliX`) e um objeto do tipo `Qubit`. 

Um exemplo simples é a operação a seguir, que cria um qubit no estado $ \ket{0}$ e, em seguida, aplica um portão Hadamard ``H`` a ele e, em seguida, mede o resultado na base `PauliZ`. 

```qsharp
operation MeasurementOneQubit () : Result {

    // The following using block creates a fresh qubit and initializes it 
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby creating the 
        // state 1/sqrt(2)(|0〉+|1〉). 
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

Um exemplo um pouco mais complicado é dado pela seguinte operação que retorna o valor booliano `true` se todos os qubits em um registro do tipo `Qubit[]` estiverem no estado zero, quando medido em uma base de Pauli especificada e `false` caso contrário. 

```qsharp
operation AllMeasurementsZero (qs : Qubit[], pauli : Pauli) : Bool {

    mutable value = true;
    for (q in qs) {
        if ( Measure([pauli], [q]) == One ) {
            set value = false;
        }
    }
    return value;
}
```

A linguagem Q # permite dependências do fluxo de controle clássico nos resultados da medição de qubits. Isso, por sua vez, permite implementar gadgets probabilística poderosos que podem reduzir o custo computacional para a implementação de unidades. Por exemplo, é fácil implementar de forma que seja chamado de *repetir-até-êxito* em Q #, que são circuitos de probabilística que têm um baixo custo *esperado* em termos de Gates elementares, mas para o qual o custo real depende de uma execução atual e de uma intercalação real de várias ramificações possíveis. 

Para facilitar os padrões do RUS (repetição até o êxito), o Q # dá suporte à construção
```qsharp
repeat {
    statementBlock1 
}
until (expression)
fixup {
    statementBlock2
}
```
onde `statementBlock1` e `statementBlock2` são zero ou mais instruções Q # e `expression` qualquer expressão válida que seja avaliada como um valor do tipo `Bool`. Em um caso de uso típico, o circuito a seguir implementa uma rotação em um eixo irracional de $ (I + 2i Z)/\sqrt{5}$ na esfera de Bloch. Isso é feito usando um padrão de RUS conhecido: 

```qsharp
operation RUScircuit (qubit : Qubit) : Unit {

    using(ancillas = Qubit[2]) {
        ApplyToEachA(H, ancillas);
        mutable finished = false;
        repeat {
            Controlled X(ancillas, qubit);
            S(qubit);
            Controlled X(ancillas, qubit);
            Z(qubit);
        }
        until(finished)
        fixup {
            if AllMeasurementsZero(ancillas, Xpauli) {
                set finished = true;
            }
        }
    }
}
```

Este exemplo mostra o uso de uma variável mutável `finished` que está no escopo de todo o loop Repeat-Until-recorretion e que é inicializado antes do loop e atualizado na etapa de correção.

Por fim, mostramos um exemplo de um padrão RUS para preparar um estado Quantum $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, começando com o estado $ \ket{+} $. Consulte também o [exemplo de teste de unidade fornecido com a biblioteca padrão](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs): 

```qsharp
operation RepeatUntilSuccessStatePreparation( target : Qubit ) : Unit {

    using( ancilla = Qubit() ) {
        H(ancilla);
        repeat {
            // We expect target and ancilla qubit to be in |+⟩ state.
            AssertProb( 
                [PauliX], [target], Zero, 1.0, 
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb( 
                [PauliX], [ancilla], Zero, 1.0,
                "ancilla qubit should be in the |+⟩ state", 1e-10 );
                
            Adjoint T(ancilla);
            CNOT(target, ancilla);
            T(ancilla);

            // The probability of measuring |+⟩ state on ancilla is 3/4.
            AssertProb( 
                [PauliX], [ancilla], Zero, 3. / 4., 
                "Error: the probability to measure |+⟩ in the first 
                ancilla must be 3/4",
                1e-10);

            // If we get measurement outcome Zero, we prepare the required state 
            let outcome = Measure([PauliX], [ancilla]);
        }
        until( outcome == Zero )
        fixup {
            // Bring ancilla and target back to |+⟩ state
            if( outcome == One ) {
                Z(ancilla);
                X(target);
                H(target);
            }
        }
        // Return ancilla back to Zero state
        H(ancilla);
    }
}
```
 
Os recursos programáticos notáveis mostrados nesta operação são uma parte `fixup` mais complexa do loop, que envolve operações de Quantum e o uso de instruções `AssertProb` para determinar a probabilidade de medir o estado Quantum em determinados pontos especificados no programa. Consulte também [testando e Depurando](xref:microsoft.quantum.techniques.testing-and-debugging) para obter mais informações sobre instruções `Assert` e `AssertProb`. 
