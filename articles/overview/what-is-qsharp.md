---
title: O que é a Q#?
description: Saiba mais sobre a Q#, uma linguagem de programação criada pela Microsoft para desenvolver aplicações para computadores quânticos
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: e04228ff62092a15c529297bd56b9ee48399f4a5
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443958"
---
# <a name="what-is-q"></a>O que é a Q#?

A Q# é uma linguagem de programação com funcionalidades especiais para a computação quântica. A Q# providencia aos programadores quânticos uma estrutura que permite que se concentre nos algoritmos sem ter de se preocupar com detalhes técnicos como a otimização da sequência das portas ou a implementação física de um computador quântico.

A linguagem de programação Q# fornece-lhe um conjunto intuitivo de tipos, operações e expressões lógicas para desenvolver algoritmos sem ter de se preocupar com a lógica interna do computador quântico.

## <a name="code-algorithms"></a>Programar algoritmos

Nos primórdios da computação quântica, os algoritmos eram visualizados como diagramas da mesma forma que os diagramas de circuito na computação clássica.  Apesar de o modelo de circuito ter sido muito útil na investigação da computação quântica durante muitos anos, aqui na Microsoft, acreditamos que os programadores podem ir para além dos circuitos quânticos e desenvolver algoritmos e aplicações quânticos com a Q#. A linguagem Q# foi criada para tirar partido daquilo que aprendemos ao longo de décadas de desenvolvimento de softwares clássicos e para capacitar os programadores quânticos com uma funcionalidade de linguagem de alto nível especialmente direcionada para a computação quântica.


## <a name="how-does-q-work"></a>Como é que a Q# funciona?

Um dos blocos modulares fundamentais da Q# é o tipo de `Qubit`, que não pode ser copiado nem acedido diretamente, tal como um verdadeiro qubit. Em vez disso, podemos medi-lo e armazenar o resultado da medição numa variável de `Result`, um tipo de Q# que pode assumir dois valores possíveis: `Zero` e `One`. Construções como esta garantem que os algoritmos respeitam sempre as leis da física quântica e que podem ser executados corretamente em computadores quânticos ou simuladores.

A Q# também inclui funcionalidades lógicas clássicas como condicionais ou ciclos com algumas distinções subtis, de forma a garantir que todas as regras quânticas estão a ser respeitadas. Por exemplo, as operações quânticas têm de ser reversíveis, o que impõe algumas restrições à forma como os ciclos são executados.

Os programas Q# são muitas vezes associados a um programa anfitrião escrito em C# ou em Python, que pode providenciar uma organização conveniente de código clássico e quântico. Além de suportar linguagens .NET como C# e Python, o QDK dá suporte ao Jupyter Notebook com o kernel do Jupyter em IQ#.

## <a name="use-q-to-learn-quantum-computing"></a>Utilizar a Q# para aprender computação quântica

Até agora, para aprender computação quântica precisava de aprender o modelo de circuito para compreender os algoritmos no formato de sequências ordenadas de portas e medições quânticas. Com a Q# pode ir por outro caminho: aprender computação quântica ao escrever programas quânticos.

## <a name="use-q-to-design-quantum-algorithms"></a>Utilizar o Q# para criar algoritmos quânticos

O Q# fornece-lhe um número crescente de bibliotecas e tipos definidos pelo utilizador que irão ajudar a implementar ferramentas e compilar algoritmos quânticos avançados. Por exemplo, precisa de entrelaçar dois qubits: q1 e q2? Em vez de aplicar as portas necessárias individualmente para que os qubits sejam entrelaçados, pode utilizar a operação `PrepareEntangledState([q1], [q2])` já integrada.

## <a name="use-q-to-estimate-quantum-resources"></a>Utilizar o Q# para estimar os recursos quânticos

Pode simular a execução do programa em Q# com o simulador quântico de estado completo fornecido com o Quantum Development Kit (QDK).  O QDK também fornece estimadores de recursos que fornecem informações sobre o desempenho dos programas em Q# demasiado grandes para serem executados num simulador,  o que é muito valioso para os designers de algoritmos, uma vez que podem ajustar os programas para utilizarem menos recursos (por exemplo, menos qubits em execução para um número menor de operações), para serem executados em hardware quântico de menor escala.   

## <a name="use-q-to-validate-hardware-performance"></a>Utilizar o Q# para validar o desempenho de hardware

A beleza do Q# é que um programa pode ser escrito uma vez e executado em simuladores quânticos para depuração e no hardware de vários computadores quânticos.  Os programas de referência escritos em Q# podem ser executados para validar o desempenho do hardware e comparar os resultados à medida que os computadores quânticos evoluem e surgem outros novos.  

## <a name="next-steps"></a>Passos seguintes

* [Como posso aprender computação quântica?](xref:microsoft.quantum.overview.learn)
* [Introdução ao Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
