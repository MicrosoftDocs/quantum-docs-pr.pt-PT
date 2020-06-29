---
title: Q# Básicos
description: 'Conceitos básicos de Q #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: 45e6f2f33dafc2aec177091d3cfa94aca14fbf0a
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415369"
---
# <a name="q-basics"></a>Q# Básicos

Este artigo apresenta uma breve introdução aos blocos básicos de construção de Q#.

Para uma visão geral do que é Q# e onde se enquadra como componente fundamental do Kit de Desenvolvimento Quântico, veja [o que é Q#?](xref:microsoft.quantum.overview.q-sharp) 

## <a name="what-is-a-quantum-program"></a>O que é um programa quântico?

Do ponto de vista técnico, um programa quântico é um conjunto particular de sub-rotinas clássicas que, quando chamados, realizam certas operações num sistema quântico.
Uma consequência importante dessa visão é que um programa Q# não modela diretamente os qubits, mas descreve como um computador controlado clássicamente interage com esses qubits.
Por design, Q# não define estados quânticos ou outras propriedades da mecânica quântica diretamente.
Por exemplo, considere o estado $\ket{+} = \left {0} (\ket + \ket {1} \right) / \sqrt {2} $ discutido no guia quantum [Computing Concepts.](xref:microsoft.quantum.concepts.intro)
Para preparar este estado em Q#, comece com os fatos de que os qubits são inicializados no estado de $\ket {0} $, e que $\ket{+} = H\ket {0} $, onde $H$ é a [transformação Hadamard,](xref:microsoft.quantum.glossary#hadamard)implementada pela [ `H` operação](xref:microsoft.quantum.intrinsic.h). O código Q# básico para inicializar e transformar um qubit, então, é assim:

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
Para obter mais informações sobre a inicialização, ou *a atribuição,* qubits, consulte [Trabalhar com qubits.](xref:microsoft.quantum.guide.qubits)

## <a name="quantum-states-in-q"></a>Estados quânticos em Q #

Importante, o programa anterior não se refere explicitamente ao estado dentro de Q# mas descreveu como o nosso programa *transformou* o estado.
Com esta abordagem, você pode ser inteiramente agnóstico sobre o que *é* um estado quântico mesmo em cada máquina alvo, que pode ter diferentes interpretações dependendo da máquina. 

Um programa Q# não pode introspeção no estado de um qubit.
Em vez disso, um programa pode chamar operações como [`Measure`](xref:microsoft.quantum.intrinsic.measure) aprender informações de um qubit, e ligar operações como [`X`](xref:microsoft.quantum.intrinsic.x) e agir sobre o estado de um [`H`](xref:microsoft.quantum.intrinsic.h) qubit.
O que estas operações realmente *fazem* é apenas feito concreto pela máquina-alvo usada para executar o programa Q# específico.
Por exemplo, se executar o programa no nosso [simulador de estado completo,](xref:microsoft.quantum.machines.full-state-simulator)o simulador executa as operações matemáticas correspondentes ao sistema quântico simulado.
Mas olhando para o futuro, quando a máquina-alvo é um verdadeiro computador quântico, chamar tais operações em Q# direciona o computador quântico para realizar as operações *reais* correspondentes no sistema quântico *real,* por exemplo, impulsos laser precisamente cronometrado).

Um programa Q# recombina estas operações tal como definido por uma máquina-alvo para criar novas operações de alto nível para expressar a computação quântica.
Desta forma, q# torna fácil expressar a lógica subjacente a algoritmos quânticos e híbridos quânticos-clássicos, ao mesmo tempo que é geral no que diz respeito à estrutura de uma máquina-alvo ou simulador.

## <a name="q-operations-and-functions"></a>Q# operações e funções

Concretamente, um programa Q# compreende *operações,* funções e quaisquer tipos *definidos*pelo utilizador. 

As operações são usadas para descrever as transformações dos sistemas quânticos e são o bloco de construção mais fundamental dos programas Q#. Cada operação definida em Q# pode então chamar qualquer número de outras operações.

Ao contrário das operações, as funções são usadas para descrever comportamentos clássicos puramente *deterministas* e não têm quaisquer efeitos além de calcular valores clássicos. Por exemplo, suponha que queira medir os qubits no final de um programa e adicione os resultados da medição a uma matriz.
Neste caso, `Measure` é uma *operação* que instrui a máquina-alvo a efetuar uma medição nos qubits (reais ou simulados). Ao mesmo tempo, as *funções* lidam com o processo clássico de adicionar os resultados devolvidos a uma matriz.

Juntos, as operações e funções são conhecidas como *callables*. A sua estrutura e comportamento subjacentes são introduzidos e detalhados em [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions).


## <a name="q-syntax-overview"></a>Visão geral da sintaxe Q#

A sintaxe de uma linguagem descreve as diferentes combinações de símbolos que formam um programa sintáticamente correto.
Em Q#, os elementos de sintaxe são classificados em três grupos diferentes: tipos, expressões e declarações.

### <a name="types"></a>Tipos
Q# é uma linguagem fortemente dactilografada, de modo que o uso cuidadoso de tipos pode ajudar o compilador a fornecer garantias fortes sobre os programas Q# no momento da compilação.
Para além dos tipos primitivos integrados standard e específicos quânticos, por exemplo, `Int` `Bool` , e , `Qubit` `Result` Q# fornece suporte para tipos definidos pelo utilizador.

Para descrições de todos os tipos primitivos, detalhes para tipos de matriz e tuple, e passos para definir novos tipos dentro de um ficheiro Q#, consulte [Tipos em Q#](xref:microsoft.quantum.guide.types).

### <a name="expressions"></a>Expressions (Expressões)
Uma expressão numa linguagem de programação é uma combinação de uma ou mais constantes, variáveis, operadores e funções que a linguagem de programação interpreta e avalia a um valor específico.
Mais simplesmente, para cada tipo de linguagem, expressões desse tipo podem ser *literais* ou símbolos ligados a um valor desse tipo.
Por exemplo, `5` é um `Int` literal (portanto, também uma expressão do `Int` tipo), e se o símbolo está `count` ligado ao valor `5` inteiro, então `count` é também uma expressão inteiro.

Além disso, uma expressão pode consistir em outras expressões combinadas por certos operadores.
Por exemplo, outra `Int` expressão que avalia é `5` `2+3` .

Para obter mais informações sobre expressões e operadores compatíveis em Q#, consulte [Expressões tipo em Q#](xref:microsoft.quantum.guide.expressions). 

### <a name="statements"></a>Instruções 
Uma declaração é uma unidade sintática de uma linguagem de programação imperativa que expressa alguma ação a realizar. As declarações contrastam com expressões em que as declarações não devolvem resultados e são executadas apenas pelos seus efeitos secundários. As expressões, no entanto, devolvem sempre um resultado e muitas vezes não têm efeitos colaterais. Em suma, as declarações Q# são executadas, enquanto as expressões são avaliadas.

Um simples exemplo de uma declaração em Q# é atribuir um símbolo a uma expressão:
```qsharp
let count = 5;
```

Um exemplo mais interessante é a `for` afirmação que suporta a iteração e inclui um *bloco de declaração.*
Suponha que `qubits` seja o símbolo ligado a um registo de qubits (tecnicamente de `Qubit[]` tipo, ou uma matriz de `Qubit` tipos). Então
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
é uma declaração que itera sobre cada qubit no registo, realizando a `H` operação em cada um. Note que `H(qubit);` esta é uma afirmação em si mesma também.

Pode utilizar qualquer expressão de chamada do tipo `Unit` (um `Unit` tipo não devolve nenhuma informação) como declaração.
Este tipo de expressão é útil quando se chama operações em qubits que regressam `Unit` porque o objetivo da declaração é modificar o estado quântico implícito.
As declarações de avaliação de expressão requerem um ponto de terminação.

Você usa declarações para construir quase todos os aspetos de um programa Q#, e nenhuma página poderia abranger toda a informação que lhes diz respeito.
Para obter mais informações sobre a sua estrutura lexical e formatação, consulte [a Estrutura de Ficheiros Q#](xref:microsoft.quantum.guide.filestructure); para a atribuição e âmbito de ligação de [símbolos, ver Variáveis em Q#](xref:microsoft.quantum.guide.variables); e para ciclos de fluxo de controlo tais como `for` , ver Control Flow em [Q#](xref:microsoft.quantum.guide.controlflow).

## <a name="next-steps"></a>Passos seguintes

Comece a aprender sobre [tipos em Q#](xref:microsoft.quantum.guide.types).

Para mais informações sobre as fundações e motivação por trás de Q#, veja [por que precisamos de Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)
