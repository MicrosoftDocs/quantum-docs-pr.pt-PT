---
title: Introdução às técnicas de desenvolvimento do Quantum | Microsoft Docs
description: Introdução às técnicas de desenvolvimento do Quantum
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 702d23293a1c340ddd3d7032d0e05294345469b2
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442567"
---
# <a name="q-program-overview"></a>Visão geral do programa Q #

O Q # é uma linguagem de programação específica de domínio de vários paradigmas escalonáveis para a computação Quantum. Q # é uma linguagem de programação Quantum no que pode ser usada para descrever como as instruções são executadas em computadores Quantum. Os computadores que podem ser direcionados variam de simuladores até o hardware Quantum real. O Q # é escalonável: pode ser usado para escrever programas de demonstração simples, como teleport, que são executados em alguns qubits, mas também oferece suporte à criação de programas grandes e sofisticados, como simulações de moléculas complexas que exigirão máquinas grandes com milhões de qubits. Embora grandes máquinas físicas ainda estejam no futuro, o Q # permite que um programador programe algoritmos de Quantum complexos agora. O que é mais, Q # dá suporte a várias tarefas, como depuração, criação de perfil, estimativa de recursos e determinadas simulações de finalidade especial de maneira escalonável. 

Do ponto de vista técnico, um programa Quantum pode ser visto como um conjunto específico de funções clássicas que, quando chamado, geram circuitos Quantum como seus efeitos colaterais. Uma consequência importante dessa exibição é que um programa escrito em Q # não modele diretamente o qubits em si, mas descreve como um computador de controle clássico interage com esses qubits.
Por design, p #, portanto, não define os Estados Quantum ou outras propriedades da mecânica quantum diretamente, mas sim indiretamente por meio da ação das várias sub-rotinas definidas no idioma.
Por exemplo, considere o estado $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ discutido no guia de [conceitos da computação Quantum](xref:microsoft.quantum.concepts.intro) .
Para preparar esse estado em Q #, usamos os fatos que os qubits são inicializados no estado $ \ket{0}$ e que $ \ket{+} = H\ket{0}$, em que $H $ é a transformação Hadamard:

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0〉.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0〉 = |+〉, as we wanted.
}
```
## <a name="q-tranformations-of-quantum-states"></a>Q # tranformations de Estados da Quantum

O mais importante é que, ao escrever o programa acima, não nos referimos explicitamente ao estado em Q #, mas, em vez disso, descrevemos como o estado foi *transformado* por nosso programa.
Assim, assim como um programa de sombreador de gráficos acumula uma descrição de transformações em cada vértice, um programa Quantum em Q # acumula transformações em Estados Quantum.
Isso nos permite ser totalmente independente do que um estado Quantum ainda *está* em cada computador de destino, que pode ter interpretações diferentes dependendo do computador. 

Da perspectiva de um programa Q #, um qubit é uma referência totalmente opaca à estrutura interna de um computador de destino.
Um programa Q # não tem a capacidade de introspecção no estado de um qubit, sua representação em um computador de destino ou até mesmo se ele é o mesmo qubit que qualquer outro qubit disponível para o programa.
Em vez disso, um programa pode chamar operações como `Measure` para aprender informações de um qubit e chamar operações como `X` e `H` para agir no estado de um qubit.
Essas operações não têm nenhuma definição intrínseca dentro do idioma e se tornam concretas apenas pela máquina de destino usada para executar um programa de Q # específico.
Um programa Q # recombina essas operações conforme definido por um computador de destino para criar operações novas e de nível mais alto para a computação da Quantum Express.
Dessa forma, o Q # torna fácil expressar os algoritmos Quantum subjacente e Quantum híbrido clássico, além de ser geral em relação à estrutura de um computador de destino ou simulador.

## <a name="q-operations-and-functions"></a>Operações e funções do Q #

Concretamente, um programa Q # é composto de uma ou mais *operações*, uma ou mais *funções*e tipos definidos pelo usuário. As operações são usadas para descrever as transformações do estado de uma máquina Quantum e são o bloco de construção mais básico de programas do Q #. Cada operação definida em Q # pode então chamar qualquer número de outras operações, incluindo as operações *intrínsecas* internas implementadas por um computador de destino.
Quando compilada, cada operação é representada como um tipo de classe do .NET que pode ser fornecido para os computadores de destino.

Em contraste com as operações, as funções são usadas para descrever o comportamento puramente clássico e não têm nenhum efeito além de calcular os valores de saída clássicas. Q # é uma linguagem fortemente tipada e vem com um conjunto de tipos primitivos internos, bem como suporte para tipos definidos pelo usuário. 

Durante o restante deste guia, veremos como usar diferentes conceitos de linguagem e construções para nos ajudar a definir programas de Quantum complexos por meio dos blocos de construção básicos de operações, funções e tipos. 

## <a name="structure-of-q-source-files"></a>Estrutura de arquivos de origem do Q #

No mínimo, um arquivo de origem Q # consiste em uma *declaração de namespace*, que especifica um namespace .NET que conterá as definições no arquivo de origem.
As definições de outros arquivos de origem Q # e bibliotecas podem ser incluídas usando a instrução `open`.
Por exemplo, a maioria das operações que definem Gates fundamentais são definidas no namespace <xref:microsoft.quantum.intrinsic>.
Para disponibilizar isso para nosso código, simplesmente `open` o namespace na parte superior de cada arquivo:

```qsharp
namespace Example {
    open Microsoft.Quantum.Intrinsic;

    // ...
}
```

Dentro de um namespace, cada arquivo de origem Q # pode definir qualquer combinação de *operações*, *funções*e *tipos definidos pelo usuário*.
No restante desta seção, descreveremos cada uma delas por vez e forneceremos exemplos de como elas podem ser usadas na prática para criar programas de Quantum úteis.
