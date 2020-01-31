---
title: Trabalhar com Qubits
description: Trabalhar com Qubits - Técnicas Q#
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: dc6db93dadc37534aece9624fe516125d919f8cd
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819999"
---
# <a name="working-with-qubits"></a>Trabalhar com Qubits

Tendo agora visto uma variedade de diferentes partes da língua Q#, vamos entrar no espesso dela e ver como usar os próprios qubits.

## <a name="allocating-qubits"></a>Alocadoqubits

Primeiro, para obter um qubit que podemos usar em Q#, *atribuímos* qubits dentro de um bloco `using`:

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

Quaisquer qubits atribuídos desta forma começam no estado de $\ket{0}$; no exemplo acima, `register` está assim no estado $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \otimes \otimes \otimes \otimes \ket \ket{0}$.
No final do bloco `using`, quaisquer qubits atribuídos por esse bloco são imediatamente transferidos e não podem ser utilizados mais.

> [!WARNING]
> As máquinas-alvo esperam que os qubits estejam no estado de $\ket{0}$ imediatamente antes da desalocação, para que possam ser reutilizados e oferecidos a outros blocos `using` para alocação.
> Sempre que possível, utilize operações unitárias para devolver quaisquer qubits atribuídos a $\ket{0}$.
> Se necessário, a operação @"microsoft.quantum.intrinsic.reset" pode ser usada para medir um qubit em vez disso, e para usar esse resultado de medição para garantir que o qubit medido seja devolvido a $\ket{0}$. Tal medição destruirá qualquer emaranhado com os restantes qubits e pode, assim, impactar o cálculo.

## <a name="intrinsic-operations"></a>Operações Intrínsecas

Uma vez atribuído, um qubit pode então ser passado para funções e operações.
Em certo sentido, isto é tudo o que um programa Q# pode fazer com um qubit, uma vez que as ações que podem ser tomadas são definidas como operações.
Veremos estas operações mais detalhadamente em [Operações e Funções Intrínsecas,](xref:microsoft.quantum.libraries.standard.prelude)mas por enquanto, mencionamos algumas operações úteis que podem ser usadas para interagir com qubits.

Em primeiro lugar, os operadores de Moqubit Pauli $X$, $Y$, e $Z$ são representados no Q# pelas operações intrínsecas `X`, `Y`e `Z`, cada uma das quais tem `(Qubit => Unit is Adj + Ctl)`tipo .
Como descrito em [Operações e Funções Intrínsecas,](xref:microsoft.quantum.libraries.standard.prelude)podemos pensar em $X$ e, portanto, de `X` como uma operação de flip bit ou não portão.
A operação `X` permite-nos preparar estados do formulário $\ket{s_0 s_1 \dots s_n}$ para uma série clássica $s$:

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

Também podemos preparar estados como $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ e $\ket{-} = \left (\ket{0} - \ket{1}\right) / \sqrt{2}$ através da transformação hadamard $H$, que está representada no Q# pela operação intrínseca `H : (Qubit => Unit is Adj + Ctl)`:

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

Utilizando a operação `Measure`, que é uma operação não unitária incorporada, podemos extrair informação clássica de um objeto de tipo `Qubit` e atribuir um valor clássico como resultado, que tem um tipo reservado `Result`, indicando que o resultado já não é um estado quântico.
A entrada para `Measure` é um eixo Pauli na esfera bloch, representado por um valor de tipo `Pauli` (por exemplo `PauliX`) e um valor de tipo `Qubit`.

Um exemplo simples é a seguinte operação, que atribui um qubit no estado de $\ket{0}$, em seguida, aplica uma operação Hadamard `H`-lhe e mede o resultado na base `PauliZ`.

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

Um exemplo um pouco mais complicado é dado pela operação seguinte, que devolve o valor booleano `true` se todos os qubits num registo de tipo `Qubit[]` estiverem no estado zero quando medidos numa base pauli especificada, e que devolve `false` o contrário.

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

A linguagem Q# permite que o fluxo de controlo clássico dependa dos resultados da medição dos qubits.
Esta capacidade, por sua vez, permite implementar poderosos gadgets probabilísticos que podem reduzir o custo computacional para a implementação de unitários.
Como exemplo, é fácil implementar os chamados padrões *Repeat-Until-Success* (RUS) em Q#.
Estes padrões RUS são programas probabilísticos que têm um baixo custo *esperado* em termos de portões elementares, mas para os quais o verdadeiro custo depende de uma execução real e de uma interparação real de várias ramificações possíveis.

Para facilitar os padrões de repetição até ao sucesso (RUS), Q# suporta a construção

```qsharp
repeat {
    statementBlock1
}
until (expression)
fixup {
    statementBlock2
}
```

quando `statementBlock1` e `statementBlock2` são declarações de Q# zero ou mais, e `expression` qualquer expressão válida que avalie um valor de tipo `Bool`.
Num caso de uso típico, a seguinte operação Q# implementa uma rotação em torno de um eixo irracional de $(I + 2i Z)/\sqrt{5}$ na esfera bloch. Isto é conseguido usando um padrão RUS conhecido:

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

Este exemplo mostra a utilização de uma variável mutável `finished` que está no âmbito de todo o ciclo de repetição até à fixação e que é inicializada antes do loop e atualizada na etapa de fixação.

Finalmente, mostramos um exemplo de um padrão RUS para preparar um estado quântico $\frac{1}{\sqrt{3}}\left (\sqrt{2}\ket{0}+\ket{1}\right)$, a partir do estado de $\ket{+}$.
Consulte também a [amostra de teste da unidade fornecida com a biblioteca padrão:](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+⟩ state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+⟩ state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+⟩ state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+⟩ in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+⟩ state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

Características programáticas notáveis mostradas nesta operação são uma parte mais complexa `fixup` do loop, que envolve operações quânticas, e o uso de declarações `AssertProb` para apurar a probabilidade de medir o estado quântico em certos pontos especificados do programa.
Consulte também [testes e depuração](xref:microsoft.quantum.techniques.testing-and-debugging) para obter mais informações sobre as operações [`Assert`](xref:microsoft.quantum.intrinsic.assert) e [`AssertProb`.](xref:microsoft.quantum.intrinsic.assertprob)
