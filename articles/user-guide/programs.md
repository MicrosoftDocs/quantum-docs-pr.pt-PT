---
title: Q# Introdução
description: 'Introdução rápida em programas quânticos em Q #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234319"
---
# <a name="q-quantum-programming-language"></a>Q# Linguagem de Programação Quântica

Tudo o que precisa de saber sobre a linguagem de programação Q# é detalhado no [guia de idiomas Q#](xref:microsoft.quantum.qsharp.index). Como qualquer outra coisa, o nosso [processo de design de línguas](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) é de fonte aberta e congratulamo-nos com as contribuições.
Para mais informações sobre as fundações e motivação por trás de Q#, veja [por que precisamos de Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)  
Q# é enviado como parte do Kit de Desenvolvimento Quântico (QDK) Para uma visão geral rápida, confira [O que é o QDK?](xref:microsoft.quantum.overview.q-sharp). . 

## <a name="what-is-a-quantum-program"></a>O que é um programa quântico?

Um programa quântico pode ser visto como um conjunto particular de subrotinas clássicas que, quando chamados, realizam uma computação interagindo com um sistema quântico; um programa escrito em Q# não modela diretamente o estado quântico, mas descreve como um computador de controlo clássico interage com qubits.
Isto permite-nos ser totalmente agnósticos sobre o que *é* um estado quântico em cada máquina-alvo, que pode ter interpretações diferentes dependendo da máquina. 

Uma consequência importante disso é que Q# não tem capacidade de introspeção no estado de um qubit ou outras propriedades da mecânica quântica diretamente, o que garante que um programa Q# pode ser executado fisicamente num computador quântico.
Em vez disso, um programa pode chamar operações como [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) extrair informações clássicas de um qubit.

Uma vez atribuído, um qubit pode ser passado para operações e funções, também referidas como *callables*. Em certo sentido, isto é tudo o que um programa Q# pode fazer com um qubit; Quaisquer ações diretas sobre o estado de um qubit são todas definidas por calcárias *intrínsecas,* tais como e - isto [`X`](xref:Microsoft.Quantum.Intrinsic.X) [`H`](xref:Microsoft.Quantum.Intrinsic.H) é, calíveis cujas implementações não são definidas dentro de Q# mas são definidas pela máquina-alvo. O que estas operações realmente *fazem* é apenas feito concreto pela máquina-alvo que usamos para executar o programa Q# específico.

Por exemplo, se executar o programa no nosso [simulador de estado completo,](xref:microsoft.quantum.machines.full-state-simulator)o simulador executa as operações matemáticas correspondentes ao sistema quântico simulado.
Mas olhando para o futuro, quando a máquina-alvo é um verdadeiro computador quântico, chamar tais operações em Q# irá direcionar o computador quântico para realizar as operações *reais* correspondentes no sistema quântico *real* (por exemplo, pulsos laser precisamente cronometrado).

Um programa Q# recombina estas operações tal como definido por uma máquina-alvo para criar novas operações de alto nível para expressar a computação quântica.
Desta forma, q# torna fácil expressar a lógica subjacente a algoritmos quânticos e híbridos quânticos-clássicos, ao mesmo tempo que é geral no que diz respeito à estrutura de uma máquina-alvo ou simulador.

Um exemplo simples é o seguinte programa, que atribui um qubit no estado $\ket {0} $, em seguida, aplica uma operação Hadamard `H` ao mesmo e mede o resultado na `PauliZ` base.

```qsharp
@EntryPoint()
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

Os [nossos Quantum Katas](https://github.com/microsoft/QuantumKatas#introduction) dão uma boa introdução em [Conceitos de Computação Quântica,](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) tais como operações quânticas comuns e como manipular qubits. Mais exemplos também podem ser encontrados [em Operações e Funções Intrínsecas.](xref:microsoft.quantum.libraries.standard.prelude)



