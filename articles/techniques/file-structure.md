---
title: Q# visão geral do programa - Técnicas Q# / Microsoft Docs
description: Visão geral do programa - Técnicas Q#
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.file-structure
ms.openlocfilehash: e8f52e6b0d4382331665a8e845ef19a3a1beabf9
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820832"
---
# <a name="q-program-overview"></a>Descrição geral do programa Q#

Q# é uma linguagem de programação escalável, multi-paradigma, específica de domínio para computação quântica. Q# é uma linguagem de programação quântica na qual pode ser usada para descrever como as instruções são executadas em máquinas quânticas. As máquinas que podem ser direcionadas vão desde simuladores a hardware quântico real. Q# é escalável: pode ser usado para escrever programas de demonstração simples como teleport que funcionam em alguns qubits, mas também suporta a escrita de grandes e sofisticados programas como simulações de moléculas complexas que exigirão grandes máquinas com milhões de qubits. Mesmo que as grandes máquinas físicas ainda estejam no futuro, Q# permite que um programador programe algoritmos quânticos complexos agora. Além disso, Q# suporta várias tarefas como depuração, perfis, estimativa de recursos e certas simulações de propósito especial de uma forma escalável. 

Do ponto de vista técnico, um programa quântico pode ser visto como um conjunto particular de funções clássicas que, quando chamadas, geram circuitos quânticos como seus efeitos colaterais. Uma consequência importante dessa visão é que um programa escrito em Q# não modela diretamente qubits em si, mas descreve como um computador de controlo clássico interage com esses qubits.
Por design, Q# assim não define estados quânticos ou outras propriedades da mecânica quântica diretamente, mas sim faz-o indiretamente através da ação das várias subrotinas definidas na linguagem.
Por exemplo, considere o estado $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discutido no guia [Quantum Computing Concepts.](xref:microsoft.quantum.concepts.intro)
Para preparar este estado em Q#, usamos os factos de que os qubits são inicializados no estado de $\ket{0}$, e que $\ket{+} = H\ket{0}$, onde $H$ é a transformação de Hadamard:

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0〉.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0〉 = |+〉, as we wanted.
}
```
## <a name="q-tranformations-of-quantum-states"></a>Q# tranformações de estados quânticos

Importante, ao escrever o programa acima, não nos referimos explicitamente ao estado dentro de Q#, mas sim descrevemos como o estado foi *transformado* pelo nosso programa.
Assim, semelhante à forma como um programa de som gráfico acumula uma descrição das transformações a cada vértice, um programa quântico em Q# acumula transformações em estados quânticos.
Isto permite-nos ser inteiramente agnósticos sobre o que um estado quântico *é* mesmo em cada máquina-alvo, que pode ter interpretações diferentes dependendo da máquina. 

Do ponto de vista de um programa Q#, um qubit é uma referência inteiramente opaca à estrutura interna de uma máquina-alvo.
Um programa Q# não tem capacidade de introspeção no estado de um qubit, a sua representação numa máquina-alvo, ou mesmo se é o mesmo qubit que qualquer outro qubit disponível para o programa.
Pelo contrário, um programa pode chamar operações como `Measure` para aprender informações a partir de um qubit, e chamar operações como `X` e `H` para agir sobre o estado de um qubit.
Estas operações não têm definição intrínseca dentro da linguagem, e são feitas de concreto apenas pela máquina-alvo usada para executar um programa Q# particular.
Um programa Q# recombina estas operações como definida por uma máquina-alvo para criar novas operações de alto nível para expressar a computação quântica.
Desta forma, Q# torna fácil expressar a lógica subjacente aos algoritmos quânticos e híbridos quânticos-clássicos, ao mesmo tempo que é geral no que diz respeito à estrutura de uma máquina-alvo ou simulador.

## <a name="q-operations-and-functions"></a>Q# operações e funções

Concretamente, um programa Q# é composto por uma ou mais *operações,* uma ou mais *funções,* e tipos definidos pelo utilizador. As operações são usadas para descrever as transformações do estado de uma máquina quântica e são o bloco de construção mais básico dos programas Q#. Cada operação definida em Q# pode então ligar para qualquer número de outras operações, incluindo as operações *intrínsecas* incorporadas implementadas por uma máquina-alvo.
Quando compilado, cada operação é representada como um tipo de classe .NET que pode ser fornecido às máquinas-alvo.

Em contraste com as operações, as funções são usadas para descrever comportamentos puramente clássicos e não têm quaisquer efeitos além de calcular valores de saída clássicos. Q# é uma linguagem fortemente dactilografada e vem com um conjunto de tipos primitivos incorporados, bem como suporte para tipos definidos pelo utilizador. 

Ao longo do resto deste guia, veremos como usar diferentes conceitos e construções linguísticas para nos ajudar a definir programas quânticos complexos através dos blocos básicos de construção de operações, funções e tipos. 

## <a name="structure-of-q-source-files"></a>Estrutura de Ficheiros De Origem Q#

Minimamente, um ficheiro de origem Q# consiste numa declaração de *espaço de nome,* que especifica um espaço de nome .NET que conterá as definições no ficheiro fonte.
As definições de outros ficheiros e bibliotecas de origem Q# podem ser incluídas utilizando a declaração `open`.
Por exemplo, a maioria das operações que definem portões fundamentais são definidas no espaço de nome <xref:microsoft.quantum.intrinsic>.
Para disponibilizar isto ao nosso código, simplesmente `open` esse espaço de nome no topo de cada ficheiro:

```qsharp
namespace Example {
    open Microsoft.Quantum.Intrinsic;

    // ...
}
```

Dentro de um espaço de nome, cada ficheiro de origem Q# pode definir qualquer combinação de *operações,* *funções*e *tipos definidos pelo utilizador*.
No resto desta secção, descreveremos cada um por sua vez e forneceremos exemplos de como podem ser usados na prática para fazer programas quânticos úteis.
