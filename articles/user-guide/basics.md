---
title: Q# Básicos
description: 'Conceitos básicos de Q #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: fd0ea47f00b1456ec460808ef7d451c8427677cd
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431160"
---
# <a name="q-basics"></a>Q# Básicos

Nesta secção apresentamos uma breve introdução aos blocos básicos de construção de Q#.

Para uma visão geral rápida do que é Q# e onde se encaixa como um componente fundamental do Kit de Desenvolvimento Quântico, você pode verificar [o que é Q#?](xref:microsoft.quantum.overview.q-sharp) 

## <a name="what-is-a-quantum-program"></a>O que é um programa quântico?

Do ponto de vista técnico, um programa quântico pode ser visto como um conjunto particular de subrotinas clássicas que, quando chamadas, realizam certas operações num sistema quântico.
Uma consequência importante dessa visão é que um programa escrito em Q# não modela diretamente qubits em si, mas descreve como um computador de controlo clássico interage com esses qubits.
Por design, Q# assim não define estados quânticos ou outras propriedades da mecânica quântica diretamente.
Por exemplo, considere o estado $\ket{+} = \left(\ket {0} + \ket {1} \right) / \sqrt {2} $ discutido no guia Quantum [Computing Concepts.](xref:microsoft.quantum.concepts.intro)
Para preparar este estado em Q#, usamos os factos de que os qubits são inicializados no estado $\ket {0} $, e que $\ket{+} = H\ket {0} $, onde $H$ é a transformação hadamard, implementada pela [ `H` operação](](xref:microsoft.quantum intrínseco.h):

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a>Estados quânticos em Q #

Importante, ao escrever o programa acima, não nos referimos explicitamente ao estado dentro de Q#, mas sim descrevemos como o estado foi *transformado* pelo nosso programa.
Isto permite-nos ser inteiramente agnósticos sobre o que um estado quântico *é* mesmo em cada máquina-alvo, que pode ter interpretações diferentes dependendo da máquina. 

Um programa Q# não tem capacidade de introspeção no estado de um qubit.
Pelo contrário, um programa pode chamar operações como [`Measure`](xref:microsoft.quantum.intrinsic.measure) para aprender informações a partir de um qubit, e chamar operações como [`X`](xref:microsoft.quantum.intrinsic.x) e agir sobre o estado de um [`H`](xref:microsoft.quantum.intrinsic.h) qubit.
O que estas operações realmente *fazem* é feito concreto pela máquina-alvo que usamos para executar o programa Q# particular.
Por exemplo, se executar o programa no nosso [simulador de estado completo,](xref:microsoft.quantum.machines.full-state-simulator)o simulador realizará as operações matemáticas correspondentes ao sistema quântico simulado.
Mas olhando para o futuro, quando a máquina-alvo é um verdadeiro computador quântico, chamar tais operações em Q# irá direcionar o computador quântico para realizar as operações *reais* correspondentes no sistema quântico *real* (por exemplo, pulsos laser precisamente cronometrados).

Um programa Q# recombina estas operações como definida por uma máquina-alvo para criar novas operações de alto nível para expressar a computação quântica.
Desta forma, Q# torna fácil expressar a lógica subjacente aos algoritmos quânticos e híbridos quânticos-clássicos, ao mesmo tempo que é geral no que diz respeito à estrutura de uma máquina-alvo ou simulador.

## <a name="q-operations-and-functions"></a>Q# operações e funções

Concretamente, um programa Q# é composto por *operações,* *funções,* e quaisquer tipos definidos pelo utilizador. 

As operações são usadas para descrever as transformações dos sistemas quânticos e são o bloco de construção mais básico dos programas Q#. Cada operação definida em Q# pode então ligar para qualquer número de outras operações.

Em contraste com as operações, as funções são usadas para descrever comportamentos clássicos puramente *determinísticos* e não têm quaisquer efeitos além da computação de valores clássicos. Por exemplo, suponha que gostaríamos de medir os nossos qubits no final de um programa, e adicionar os resultados de medição a uma matriz.
Neste caso, trata-se de `Measure` uma *operação* que instrui a máquina-alvo a efetuar uma medição dos qubits (reais ou simulados) e o processo clássico de adição dos resultados devolvidos a uma matriz será manuseado por *funções*.

Em conjunto, as operações e funções são referidas como *callables*, e a sua estrutura e comportamento subjacentes é introduzido na página [Operações e Funções na](xref:microsoft.quantum.guide.operationsfunctions) página Q#


## <a name="q-syntax-overview"></a>Q# visão geral da sintaxe

A sintaxe de uma linguagem descreve as diferentes combinações de símbolos que formam um programa sintáticamente correto.
Em Q# podemos classificar os elementos da sua sintaxe em três grupos diferentes: tipos, expressões e declarações.

### <a name="types"></a>Tipos
Q# é uma linguagem fortemente dactilografada, de tal forma que o uso cuidadoso dos tipos pode ajudar o compilador a fornecer fortes garantias sobre os programas Q# no momento da compilação.
Além dos tipos primitivos incorporados padrão e quânticos específicos (por `Int` exemplo, `Bool` , `Qubit` `Result` Q# fornece suporte para tipos definidos pelo utilizador.
Todos os vários tipos primitivos de Q#são descritos na página De Tipos [em Q#,](xref:microsoft.quantum.guide.types) juntamente com detalhes sobre tipos de matriz e tuple, bem como como definir novos tipos dentro de um ficheiro Q#.

### <a name="expressions"></a>Expressões
Uma expressão numa linguagem de programação é uma combinação de uma ou mais constantes, variáveis, operadores e funções que a linguagem de programação interpreta e avalia a um valor específico.
Mais simplesmente, para cada tipo de linguagem, expressões desse tipo podem ser *literais* ou símbolos ligados a um valor desse tipo.
Por exemplo, `5` é uma expressão literal `Int` (portanto também uma expressão de `Int` tipo), e se o símbolo está `count` ligado ao valor `5` inteiro, então `count` também é uma expressão inteiro.

Além disso, uma expressão pode consistir em outras expressões combinadas com certos operadores.
Daí outro exemplo de uma `Int` expressão que avalia é `5` `2+3` .

As possíveis expressões de tipos em Q#, bem como os operadores compatíveis que podem ser usados para forme-os, são detalhados na página [Q#.](xref:microsoft.quantum.guide.expressions) 

### <a name="statements"></a>Instruções 
Uma declaração é uma unidade sintática de uma linguagem de programação imperativa que expressa alguma ação a ser realizada. As declarações contrastam com as expressões em que as declarações não devolvem resultados e são executadas apenas pelos seus efeitos secundários, enquanto as expressões devolvem sempre um resultado e muitas vezes não têm efeitos secundários.
Esta distinção é frequentemente observada na redação: uma expressão é avaliada, enquanto uma declaração é executada.

Um exemplo muito básico de uma declaração em Q# é atribuir um símbolo a uma expressão:
```qsharp
let count = 5;
```

Um exemplo um pouco mais interessante é a afirmação que suporta a `for` iteração e inclui um bloco de *declaração.*
Suponha `qubits` que o símbolo é ligado a um registo de qubits (tecnicamente de `Qubit[]` tipo, ou seja, uma variedade de `Qubit` tipos). Então
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
é uma declaração que iterates sobre cada qubit no registo, executando a `H` operação em cada um. Note que `H(qubit);` é uma afirmação em si também.

De facto, qualquer expressão de chamada de tipo `Unit` (os chamadores que não devolvem qualquer informação) pode ser usada como declaração.
Isto é principalmente útil quando se ligam para operações em qubits que regressam `Unit` porque o objetivo da declaração é modificar o estado quântico implícito.
As declarações de avaliação da expressão requerem um ponto e vírgula terminando.

Quase todos os aspetos de um programa Q# são construídos usando declarações, por isso nenhuma página poderia abranger toda a informação relacionada com eles.
No entanto, a sua estrutura lexical e formatação são descritas na página [Q# Estrutura](xref:microsoft.quantum.guide.filestructure) de Ficheiros, atribuição de ligação de símbolos e âmbito em [Variáveis em Q#](xref:microsoft.quantum.guide.variables), e circuitos de fluxo de controlo como `for` no Control Flow em [Q#](xref:microsoft.quantum.guide.controlflow).


## <a name="whats-next"></a>Passos seguintes?
Ao longo do resto deste guia, vamos mostrar-lhe como usar Q# para construir programas quânticos complexos através dos blocos básicos de construção de operações, funções e tipos.

Para começar, você pode começar a aprender sobre [tipos em Q#](xref:microsoft.quantum.guide.types).

Se está interessado em aprender mais sobre as fundações e motivação por trás do Q#, confira [por que precisamos de Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
