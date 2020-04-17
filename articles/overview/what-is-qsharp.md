---
title: O que é C# e o QDK?
description: Saiba mais sobre o Q#, uma linguagem de programação criada pela Microsoft para desenvolver aplicações para computadores quânticos e um componente fundamental do Microsoft Quantum Development Kit
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: a4bf21887e34ac85f75e5e0b9a033138464fd09d
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/16/2020
ms.locfileid: "77907006"
---
# <a name="what-are-q-and-the-qdk"></a>O que é C# e o QDK?

Q# é uma linguagem de programação com funcionalidades concebidas especificamente para utilização na computação quântica.
Como componente fundamental do Microsoft Quantum Development Kit (QDK), providencia aos programadores quânticos uma estrutura que lhe permite concentrar-se nos algoritmos sem ter de se preocupar com detalhes técnicos como a otimização da sequência das portas ou a implementação física de um computador quântico.

O QDK compreende uma vasta gama de ferramentas que dão aos programadores tudo o que precisam para começarem a escrever programas quânticos.
Além da linguagem Q#, o QDK inclui:
* *bibliotecas Q#* , que permitem aos programadores criar rapidamente aplicações quânticas reais
* vários *computadores de destino* em que os programas Q# podem ser executados. Estão incluídas estimativas de recursos e simuladores para programas quânticos maiores, bem como um simulador quântico de estado completo, que se comporta como um computador quântico sem ruído. A funcionalidade anterior é muito útil para mexer com ideias, depurar programas e aprender sobre física quântica, mas é eficiente apenas para programas com relativamente poucos qubits. Estamos ansiosos por disponibilizar hardware de computação quântica como computadores de destino no futuro.
* *ferramentas* para fazer o trabalho com Q# da forma mais perfeita possível, como extensões para o Visual Studio e VS Code, e pacotes para utilização com o Python e Jupyter Notebooks.
* *API de documentação* para emparelhar o Q# com linguagens de anfitrião clássicas, como Python e C#

As aplicações desenvolvidas com o Microsoft Quantum Development Kit consiste normalmente em duas partes:
1. Um ou mais algoritmos quânticos, implementados com a linguagem de programação quântica Q#, e invocados pelo programa anfitrião clássico. São constituídos por 
    - operações Q#: sub-rotinas com operações quânticas, e 
    - funções Q#: sub-rotinas clássicas utilizadas no algoritmo quântico.
2. Um programa clássico, implementado numa linguagem de programação clássica como Python ou C# e que serve como ponto de entrada principal e invocará operações Q# quando quiser executar um algoritmo quântico.

## <a name="write-quantum-programs-not-quantum-circuits"></a>Escreva programas quânticos e não circuitos quânticos

Nos primórdios da computação quântica, os algoritmos eram visualizados como diagramas da mesma forma que os diagramas de circuito na computação clássica.
Apesar de o modelo de circuito ter sido útil na investigação da computação quântica durante muitos anos, aqui na Microsoft, acreditamos que os programadores podem ir para além dos circuitos quânticos e desenvolver algoritmos e aplicações quânticos com a linguagem Q#.
A linguagem Q# foi criada para tirar partido daquilo que aprendemos ao longo de décadas de desenvolvimento de softwares clássicos e para capacitar os programadores quânticos com uma funcionalidade de linguagem de alto nível direcionada para a computação quântica.

## <a name="how-does-q-work"></a>Como é que a Q# funciona?

A linguagem de programação Q# fornece-lhe um conjunto intuitivo de tipos, operações e expressões lógicas para desenvolver algoritmos sem ter de se preocupar com a lógica interna do computador quântico.

Um dos blocos modulares fundamentais da Q# é o tipo de `Qubit`, que não pode ser copiado nem acedido diretamente, tal como um verdadeiro qubit.
Em vez disso, podemos medi-lo e armazenar o resultado da medição numa variável de `Result`, um tipo de Q# que pode assumir dois valores possíveis: `Zero` e `One`.
Construções como esta garantem que os algoritmos respeitam sempre as leis da física quântica e que podem ser executados corretamente em computadores quânticos ou simuladores.

O Q# também inclui funcionalidades lógicas clássicas como condicionais e ciclos com algumas distinções subtis de forma a garantir que todas as regras quânticas estão a ser respeitadas.
Por exemplo, a restrição da forma como os ciclos são executados para garantir que as operações quânticas não são chamadas dentro das funções que apenas possam conter sub-rotinas clássicas deterministas.

Os programas Q# são muitas vezes associados a um programa anfitrião escrito em C# ou em Python, que pode providenciar uma organização conveniente de código clássico e quântico.
Além de suportar linguagens como C# e Python, o QDK dá suporte ao Jupyter Notebook com o kernel do Jupyter em IQ#.

## <a name="what-can-i-use-q-for"></a>Para que posso utilizar o Q#?

### <a name="use-q-to-learn-quantum-computing"></a>Utilizar a Q# para aprender computação quântica

Até agora, para aprender computação quântica precisava de aprender o modelo de circuito para compreender os algoritmos no formato de sequências ordenadas de portas e medições quânticas. Com a Q# pode ir por outro caminho: aprender computação quântica ao escrever programas quânticos.

### <a name="use-q-to-design-quantum-algorithms"></a>Utilizar o Q# para criar algoritmos quânticos

O Q# fornece-lhe um número crescente de bibliotecas e tipos definidos pelo utilizador que irão ajudar a implementar ferramentas e compilar algoritmos quânticos avançados. Por exemplo, precisa de entrelaçar dois qubits: q1 e q2? Em vez de aplicar as portas necessárias individualmente para que os qubits sejam entrelaçados, pode utilizar a operação `PrepareEntangledState([q1], [q2])` já integrada.

### <a name="use-q-to-estimate-quantum-resources"></a>Utilizar o Q# para estimar os recursos quânticos

Pode simular a execução do programa em Q# com o simulador quântico de estado completo fornecido com o Quantum Development Kit (QDK).  O QDK também disponibiliza estimadores de recursos que fornecem informações sobre o desempenho dos programas em Q# demasiado grandes para serem executados num simulador,  o que é muito valioso para os designers de algoritmos, uma vez que podem ajustar os programas para utilizarem menos recursos (por exemplo, menos qubits em execução para um número menor de operações), para serem executados em hardware quântico de menor escala.

### <a name="use-q-to-validate-hardware-performance"></a>Utilizar o Q# para validar o desempenho de hardware

A beleza do Q# é que um programa pode ser escrito uma vez e executado em simuladores quânticos para depuração, além de poder ser executado em hardware de computadores quânticos diferentes.  Os programas de referência escritos em Q# podem ser executados para validar o desempenho do hardware e comparar os resultados à medida que os computadores quânticos evoluem e surgem outros novos.  

## <a name="next-steps"></a>Passos seguintes

* [Como posso saber mais sobre computação quântica?](xref:microsoft.quantum.overview.learn)
* [Introdução ao Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
