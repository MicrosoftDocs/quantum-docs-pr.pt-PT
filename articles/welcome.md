---
uid: microsoft.quantum.welcome
title: Introdução ao Quantum Development Kit (QDK)
description: Saiba como começar a programar projetos quânticos em Q# com o Microsoft Quantum Development Kit (QDK).
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: overview
ms.openlocfilehash: cea39e47ec5e7e2ad97adbbb39ba586274564967
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907635"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Introdução ao Quantum Development Kit (QDK)

Bem-vindo ao Microsoft Quantum Development Kit!  
O QDK contém todas as ferramentas de que precisa para criar os seus próprios programas quânticos e experiências com Q#, uma linguagem de programação concebida especificamente para o desenvolvimento de aplicações quânticas. 

Para começar já, pode ir para o [guia de instalação do QDK](xref:microsoft.quantum.install).
Em seguida, será guiado pelo processo de instalação do Quantum Development Kit nos computadores Windows, Linux ou MacOS para que possa escrever os seus próprios programas quânticos.

Se ainda não se sentir pronto para começar a programar, mas quiser saber mais sobre computação quântica e Q#, encorajamo-lo a continuar a ler este artigo para que possa ter uma ideia dos recursos à sua disposição. Na secção [cinco perguntas sobre computação quântica](#five-questions-about-quantum-computing), encontrará ligações precisamente para os conteúdos de que está à procura!

## <a name="get-started-programming"></a>Comece a programar

O Quantum Development Kit dá-lhe várias formas de aprender a desenvolver um programa quântico com Q#.
Para começar a trabalhar com o poder do quantum, pode experimentar os nossos *inícios rápidos*:

* O [gerador de números aleatórios quântico](xref:microsoft.quantum.quickstarts.qrng) é uma aplicação do estilo "Hello World" em Q# que lhe dá uma breve introdução aos conceitos quânticos, ao mesmo tempo que lhe permite criar e executar uma aplicação quântica em minutos.
* As [Noções básicas dos programas quânticos com Q#](xref:microsoft.quantum.write-program) orientam-no na escrita de um programa em Q# que demonstra alguns dos conceitos fundamentais da programação quântica. 
    Se ainda não estiver preparado para começar a programar, poderá, ainda assim, acompanhar sem instalar o QDK e obter uma descrição geral da linguagem de programação Q# e dos conceitos iniciais da computação quântica.
* O [algoritmo de pesquisa de Grover](xref:microsoft.quantum.quickstarts.search) fornece um exemplo de um programa em Q# para lhe dar uma ideia do poder do Q# para expressar o algoritmo quântico de forma a criar uma síntese das operações quânticas de baixo nível. 
    Este início rápido irá orientá-lo no desenvolvimento do programa numa variedade de ambientes de programação (com um anfitrião Python ou o anfitrião de linguagem .NET e com o Visual Studio ou o Visual Studio Code).

### <a name="learning-further"></a>Aprofundar conhecimentos
* Se quiser aprofundar o seu conhecimento da programação em Q#, veja o [Quantum Katas](https://github.com/Microsoft/QuantumKatas), uma coleção de exercícios de programação personalizados que servem de introdução à computação quântica através de exercícios de programação em Q#.
    Muitos destes katas também estão disponíveis como Blocos de Notas de Q#. 
* O nosso [repositório de exemplos](https://github.com/Microsoft/Quantum) apresenta vários exemplos que demonstram como escrever programas quânticos com o Q#. A maioria destes exemplos é escrita com as nossas [bibliotecas quânticas](https://github.com/Microsoft/QuantumLibraries) open-source, incluindo as nossas bibliotecas [padrão](xref:microsoft.quantum.libraries.standard.intro) e de [química](xref:microsoft.quantum.chemistry.concepts.intro) (mais informações sobre as mesmas abaixo).

## <a name="five-questions-about-quantum-computing"></a>Cinco questões sobre a computação quântica

Se só agora conheceu o desenvolvimento quântico, percebemos que se sinta um pouco assoberbado. Fornecemos recursos para ajudá-lo a iniciar o seu percurso de aprendizagem em computação quântica. Com a ajuda destes breves artigos, acreditamos que em menos de nada ficará ansioso por começar a programar.
* [O que é a computação quântica?](xref:microsoft.quantum.overview.what)
* [O que podem fazer os computadores quânticos?](xref:microsoft.quantum.overview.computers)
* [Razões para aprender computação quântica?](xref:microsoft.quantum.overview.why)
* [O que é a Q#?](xref:microsoft.quantum.overview.qsharp)
* [Como aprender computação quântica com o Q#](xref:microsoft.quantum.overview.learn)

## <a name="quantum-development-kit-documentation"></a>Documentação do Quantum Development Kit

A documentação atual inclui os seguintes tópicos adicionais.

### <a name="using-q"></a>Utilizar o Q#
* As [técnicas de desenvolvimento quântico](xref:microsoft.quantum.techniques.intro) especificam os conceitos fundamentais utilizados para criar programas quânticos em Q#. Os tópicos incluem estruturas de ficheiros, operações e funções, a utilização de qubits e alguns tópicos avançados.
* A [referência da linguagem Q#](xref:microsoft.quantum.language.intro) explica a linguagem Q#, incluindo o modelo de tipo, expressões, declarações e utilização do compilador.
* Os [simuladores quânticos e aplicações anfitriãs](xref:microsoft.quantum.machines) descrevem como os algoritmos quânticos são executados, que computadores quânticos estão disponíveis e como escrever um controlador não Q# para o programa quântico.

### <a name="q-libraries"></a>Bibliotecas Q#
* As [bibliotecas padrão Q#](xref:microsoft.quantum.libraries.standard.intro) descrevem as operações e funções que suportam tanto o requisito de controlo de linguagem clássica como os algoritmos quânticos Q#. 
    Os tópicos incluem o fluxo de controlo, estruturas de dados, correção de erros, testes e depuração. 
* A [biblioteca de química Q#](xref:microsoft.quantum.chemistry.concepts.intro) descreve as operações e funções que suportam a simulação de química quântica, uma aplicação crítica da computação quântica. Os tópicos incluem a simulação da dinâmica Hamiltoniana e da estimativa da fase quântica, entre outros.
* A [biblioteca numérica Q#](xref:microsoft.quantum.numerics.intro) descreve as operações e funções que suportam a expressão de funções aritméticas complicadas em termos das operações nativas dos computadores de destino.
* A [referência da biblioteca Q#](xref:microsoft.quantum.standardlibsintro) contém informações de referência sobre entidades da biblioteca por espaço de nomes.

### <a name="general-quantum-computing"></a>Computação quântica geral
* Os [conceitos de computação quântica](xref:microsoft.quantum.concepts.intro) incluem tópicos como a relevância da álgebra linear para a computação quântica, a natureza e utilização de um qubit, como ler um circuito quântico e muito mais.
* O [glossário de computação quântica](xref:microsoft.quantum.glossary) é um glossário de alguns termos cruciais específicos da computação quântica e do desenvolvimento de programas. 
    Se é novo neste campo, este glossário pode ser uma referência útil enquanto lê a nossa documentação.
* A secção [Mais recursos](xref:microsoft.quantum.more-information) contém referências selecionadas especificamente para lhe dar uma cobertura detalhada dos tópicos da computação quântica.

### <a name="additional-info"></a>Informações adicionais
* [Notas de versão do Microsoft Quantum Development Kit](xref:microsoft.quantum.relnotes).


## <a name="be-a-part-of-the-q-open-source-community"></a>Faça parte da Comunidade Open-Source do Q#
O Quantum Development Kit é um development kit open-source que confere aos programadores as capacidades necessárias para fazer com que a computação quântica seja mais acessível a todos, para que possamos superar alguns dos desafios mais prementes do mundo.  As instituições académicas que necessitem de software open-source poderão implementar o Q# para os seus processos de aprendizagem e desenvolvimento quânticos. Disponibilizar o development kit em open-source também dá aos programadores e especialistas em domínios a oportunidade de contribuir com melhorias e ideias através do respetivo código.

Os seus comentários, participação e contributos para o Quantum Development Kit é importante.  Para saber mais sobre as origens do Quantum Development Kit, fornecer comentários e saber como pode participar nas decisões e contribuir para esta plataforma de desenvolvimento quântico em crescimento, veja [Contribuir para o Quantum Development Kit](xref:microsoft.quantum.contributing).

Se quiser informações mais gerais sobre a iniciativa de computação quântica da Microsoft, veja [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/).
