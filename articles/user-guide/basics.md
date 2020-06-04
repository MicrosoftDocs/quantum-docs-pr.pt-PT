---
title: Q# Básicos
description: 'Conceitos básicos de Q #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: e77b52d1a6eb7e2f62ab12dedd75d00ac8fec4be
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327327"
---
# <a name="q-basics"></a>Q# Básicos

Nesta secção apresentamos uma breve introdução aos blocos básicos de construção de Q#.

Para uma visão geral rápida do que é Q# e onde se enquadra como componente fundamental do Kit de Desenvolvimento Quântico, pode verificar [o que é Q#?](xref:microsoft.quantum.overview.q-sharp) 

## <a name="what-is-a-quantum-program"></a>O que é um programa quântico?

Do ponto de vista técnico, um programa quântico pode ser visto como um conjunto particular de sub-rotinas clássicas que, quando chamados, realizam certas operações num sistema quântico.
Uma consequência importante dessa visão é que um programa escrito em Q# não modela diretamente os qubits, mas descreve como um computador de controlo clássico interage com esses qubits.
Por design, Q# assim não define estados quânticos ou outras propriedades da mecânica quântica diretamente.
Por exemplo, considere o estado $\ket{+} = \left {0} (\ket + \ket {1} \right) / \sqrt {2} $ discutido no guia quantum [Computing Concepts.](xref:microsoft.quantum.concepts.intro)
Para preparar este estado em Q#, usamos os fatos que os qubits são inicializados no estado de $\ket {0} $, e que $\ket{+} = H\ket {0} $, onde $H$ é a transformação Hadamard, implementada pela `H` [operação](xref:microsoft.quantum.intrínseco.h):

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a>Estados quânticos em Q #

Importante, ao escrever o programa acima, não nos referimos explicitamente ao estado dentro de Q#, mas sim descrever como o estado foi *transformado* pelo nosso programa.
Isto permite-nos ser totalmente agnósticos sobre o que *é* um estado quântico em cada máquina-alvo, que pode ter interpretações diferentes dependendo da máquina. 

Um programa Q# não tem capacidade de introspeção no estado de um qubit.
Em vez disso, um programa pode chamar operações como [`Measure`](xref:microsoft.quantum.intrinsic.measure) aprender informações de um qubit, e ligar operações como [`X`](xref:microsoft.quantum.intrinsic.x) e agir sobre o estado de um [`H`](xref:microsoft.quantum.intrinsic.h) qubit.
O que estas operações realmente *fazem* é apenas feito concreto pela máquina-alvo que usamos para executar o programa Q# específico.
Por exemplo, se executar o programa no nosso [simulador de estado completo,](xref:microsoft.quantum.machines.full-state-simulator)o simulador realizará as operações matemáticas correspondentes ao sistema quântico simulado.
Mas olhando para o futuro, quando a máquina-alvo é um verdadeiro computador quântico, chamar tais operações em Q# irá direcionar o computador quântico para realizar as operações *reais* correspondentes no sistema quântico *real* (por exemplo, pulsos laser precisamente cronometrado).

Um programa Q# recombina estas operações tal como definido por uma máquina-alvo para criar novas operações de alto nível para expressar a computação quântica.
Desta forma, q# torna fácil expressar a lógica subjacente a algoritmos quânticos e híbridos quânticos-clássicos, ao mesmo tempo que é geral no que diz respeito à estrutura de uma máquina-alvo ou simulador.

## <a name="q-operations-and-functions"></a>Q# operações e funções

Concretamente, um programa Q# é composto por *operações,* funções e quaisquer tipos *definidos*pelo utilizador. 

As operações são usadas para descrever as transformações dos sistemas quânticos e são o bloco de construção mais básico dos programas Q#. Cada operação definida em Q# pode então chamar qualquer número de outras operações.

Ao contrário das operações, as funções são usadas para descrever comportamentos clássicos puramente *deterministas* e não têm quaisquer efeitos além de calcular valores clássicos. Por exemplo, suponha que gostaríamos de medir os nossos qubits no final de um programa, e adicionar os resultados da medição a uma matriz.
Neste `Measure` caso, é uma *operação* que instrui a máquina-alvo a efetuar uma medição dos qubits (reais ou simulados) e o processo clássico de adição dos resultados devolvidos a uma matriz será tratado por *funções*.

Em conjunto, as operações e funções são referidas como *callables,* e a sua estrutura e comportamento subjacentes é introduzida na página [Operações e Funções na página Q#.](xref:microsoft.quantum.guide.operationsfunctions)


## <a name="q-syntax-overview"></a>Visão geral da sintaxe Q#

A sintaxe de uma linguagem descreve as diferentes combinações de símbolos que formam um programa sintáticamente correto.
Em Q# podemos classificar os elementos da sua sintaxe em três grupos diferentes: tipos, expressões e declarações.

### <a name="types"></a>Tipos
Q# é uma linguagem fortemente dactilografada, de modo que o uso cuidadoso de tipos pode ajudar o compilador a fornecer garantias fortes sobre os programas Q# no momento da compilação.
Para além dos tipos primitivos integrados standard e específicos quânticos (por `Int` `Bool` exemplo, `Qubit` , e , `Result` Q# fornece suporte para tipos definidos pelo utilizador.
Todos os vários tipos primitivos de Q#são descritos na página Tipos na página [Q#,](xref:microsoft.quantum.guide.types) juntamente com detalhes sobre os tipos de matriz e tuple, bem como como definir novos tipos dentro de um ficheiro Q#.

### <a name="expressions"></a>Expressions (Expressões)
Uma expressão numa linguagem de programação é uma combinação de uma ou mais constantes, variáveis, operadores e funções que a linguagem de programação interpreta e avalia a um valor específico.
Mais simplesmente, para cada tipo de linguagem, expressões desse tipo podem ser *literais* ou símbolos ligados a um valor desse tipo.
Por exemplo, `5` é um `Int` literal (portanto, também uma expressão do `Int` tipo), e se o símbolo está `count` ligado ao valor `5` inteiro, então `count` é também uma expressão inteiro.

Além disso, uma expressão pode consistir em outras expressões combinadas com certos operadores.
Daí outro exemplo de uma `Int` expressão que avalia `5` `2+3` é.

As possíveis expressões de tipos em Q#, bem como os operadores compatíveis que podem ser usados para forme-los, são detalhados na página Tipo Expressões na página [Q#.](xref:microsoft.quantum.guide.expressions) 

### <a name="statements"></a>Instruções 
Uma declaração é uma unidade sintática de uma linguagem de programação imperativa que expressa alguma ação a ser realizada. As declarações contrastam com expressões em que as declarações não devolvem resultados e são executadas apenas pelos seus efeitos colaterais, enquanto as expressões devolvem sempre um resultado e muitas vezes não têm efeitos colaterais.
Esta distinção é frequentemente observada na redação: uma expressão é avaliada, enquanto uma declaração é executada.

Um exemplo muito básico de uma declaração em Q# é atribuir um símbolo a uma expressão:
```qsharp
let count = 5;
```

Um exemplo um pouco mais interessante é a `for` afirmação que suporta a iteração e inclui um *bloco de declaração.*
Suponha que `qubits` seja o símbolo ligado a um registo de qubits (tecnicamente de `Qubit[]` tipo, isto é, uma matriz de `Qubit` tipos). Então
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
é uma declaração que itera sobre cada qubit no registo, realizando a `H` operação em cada um. Note que `H(qubit);` esta é uma afirmação em si mesma também.

De facto, qualquer expressão de chamada do tipo `Unit` (os calíveis que não devolvem nenhuma informação) pode ser usada como declaração.
Isto é principalmente útil quando se chama operações em qubits que regressam `Unit` porque o objetivo da declaração é modificar o estado quântico implícito.
As declarações de avaliação de expressão requerem um ponto de terminação.

Quase todos os aspetos de um programa Q# são construídos usando declarações, por isso nenhuma página poderia abranger toda a informação que lhes diz respeito.
No entanto, a sua estrutura lexical e formatação são descritas na página [Q# Estrutura de Ficheiros,](xref:microsoft.quantum.guide.filestructure) atribuição de ligação de símbolos e âmbito [em Variáveis em Q#](xref:microsoft.quantum.guide.variables), e ciclos de fluxo de controlo tais como `for` no Control Flow in [Q#](xref:microsoft.quantum.guide.controlflow).

## <a name="next-steps"></a>Próximos passos
Ao longo do resto deste guia, vamos mostrar-lhe como usar q# para construir programas quânticos complexos através dos blocos básicos de construção de operações, funções e tipos.

Para começar, pode começar a aprender sobre [tipos em Q#](xref:microsoft.quantum.guide.types).

Se está interessado em aprender mais sobre as fundações e motivação por trás da Q#, confira [por que precisamos de Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)
