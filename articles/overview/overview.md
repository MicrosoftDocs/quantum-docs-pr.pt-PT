---
title: Introdução à computação quântica
description: Saiba o que é a computação quântica, o que os computadores quânticos fazem e como pode aprender a trabalhar com a computação quântica.
author: bradben
ms.author: bradben
ms.date: 05/05/2020
ms.topic: overview
uid: microsoft.quantum.overview.introduction
ms.openlocfilehash: 7c55420bd35f9b6e0e7ec80ddffe8a861cb7df39
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430786"
---
# <a name="introduction-to-quantum-computing-and-the-quantum-development-kit"></a>Introdução à computação quântica e ao Quantum Development kit

O Microsoft Quantum Development Kit (QDK) é um conjunto de ferramentas open-source criado para ajudar os programadores a aprender o que são algoritmos quânticos e a escrever programas quânticos. A computação quântica promete resolver alguns dos maios desafios do nosso planeta nas áreas do ambiente, da agricultura, da saúde, da energia, do cliente, da ciência dos materiais, entre outros com que ainda nem nos deparámos.  

E mesmo os nossos computadores mais poderosos têm dificuldade em resolver alguns desses problemas. Embora a tecnologia quântica ainda esteja a começar a impactar o mundo da computação, poderá ter um grande alcance e mudar a forma como a encaramos.

## <a name="what-is-quantum-computing"></a>O que é a computação quântica?

No uso moderno, o termo "quântico" refere-se à unidade discreta mais pequena possível de qualquer propriedade física, referindo-se, normalmente, às propriedades de partículas atómicas ou subatómicas. Os computadores quânticos utilizam partículas quânticas reais, átomos artificiais ou propriedades coletivas de partículas quânticas como unidades de processamento e são dispositivos grandes, complexos e caros.

Tirando partido do comportamento único da física quântica e aplicando-o à computação, os computadores quânticos introduzem conceitos novos nos métodos de programação tradicionais ao recorrerem a comportamentos físicos quânticos como sobreposição, entrelaçamento e interferência quântica.

## <a name="what-can-a-quantum-computer-do"></a>O que pode fazer um computador quântico?

Um computador quântico não é um supercomputador que consegue fazer tudo mais depressa, mas há algumas áreas em que funciona excecionalmente bem.

- [Simulação quântica](xref:microsoft.quantum.overview.introduction#quantum-simulation)
- [Criptografia](xref:microsoft.quantum.overview.introduction#cryptography-and-shors-algorithm)
- [Pesquisa](xref:microsoft.quantum.overview.introduction#search-and-grovers-algorithm)
- [Otimização](xref:microsoft.quantum.overview.introduction#quantum-inspired-computing-and-optimization)
- [Machine learning](xref:microsoft.quantum.overview.introduction#quantum-machine-learning)

## <a name="quantum-simulation"></a>Simulação quântica

Uma vez que os computadores quânticos utilizam fenómenos quânticos na computação, são adequados para modelar outros sistemas quânticos. Alguns exemplos de mecanismos quânticos que os programas quânticos podem simular incluem fotossíntese, supercondutividade e formações moleculares complexas.

## <a name="cryptography-and-shors-algorithm"></a>Criptografia e algoritmo de Shor

Em 1994, Peter Shor demonstrou que um computador quântico dimensionável era capaz de descodificar técnicas de encriptação muito utilizadas, como o algoritmo RSA. A criptografia clássica baseia-se na complexidade dos problemas, como fatorização de números inteiros ou logaritmos discretos, muitos dos quais podem ser resolvidos de forma mais eficiente com computadores quânticos.

## <a name="search-and-grovers-algorithm"></a>Pesquisa e algoritmo de Grover

Em 1996, Lov Grover desenvolveu um algoritmo quântico que acelerou significativamente a solução para pesquisas de dados não estruturados, executando as pesquisas em menos passos do que qualquer algoritmo clássico conseguia.

## <a name="quantum-inspired-computing-and-optimization"></a>Computação e otimização inspiradas na quântica

Os algoritmos inspirados na quântica utilizam princípios quânticos para aumentar a velocidade e a precisão, mas são implementados em sistemas de computadores clássicos. Com esta abordagem, os programadores podem tirar partido das capacidades das novas técnicas quânticas hoje sem terem de esperar por hardware quântico, que ainda é uma indústria emergente.

A otimização é o processo de encontrar a melhor solução para um problema, tendo em conta o resultado pretendido e as limitações. Fatores como custo, qualidade ou tempo de produção têm um papel importante nas decisões críticas que a indústria e a ciência tomam. Os algoritmos de otimização inspirados na quântica, executados nos computadores clássicos dos nossos dias, conseguem encontrar soluções que eram impossíveis até hoje. Além da otimização do fluxo de tráfego para reduzir congestionamentos, há decisões quanto a atribuição de portas de embarque dos aeroportos, entrega de encomendas, agendamento de trabalhos, entre outras. Com as inovações na ciência de materiais, existirão novas formas de energia, baterias com mais capacidade e materiais mais leves e resistentes.

> [!NOTE]
> Leia mais sobre como é que a computação inspirada na quântica da Microsoft está a ser utilizada na [ciência de materiais](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/), na [gestão de riscos](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/) e na [medicina](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/).

## <a name="quantum-machine-learning"></a>Machine learning quântico

O machine learning nos computadores clássicos está a revolucionar o mundo das ciências e dos negócios. No entanto, o elevado custo computacional de preparar os modelos está a limitar o desenvolvimento e o âmbito desta área. A área do machine learning quântico explora de que forma se pode conceber e implementar software quântico que resulte na execução mais rápida do machine learning em computadores clássicos.

O Quantum Development kit inclui a [biblioteca de machine learning quântico](xref:microsoft.quantum.machine-learning.concepts.intro) que lhe permite executar experimentações de machine learning quânticas/clássicas híbridas. A biblioteca inclui exemplos e tutoriais e disponibiliza as ferramentas necessárias para implementar um novo algoritmo quântico/clássico híbrido, o classificador quântico centrado em circuitos, para resolver problemas de classificação supervisionados.

## <a name="q-and-the-microsoft-quantum-development-kit-qdk"></a>Q# e Microsoft Quantum Development Kit (QDK)

O Q# é a linguagem de programação open-source da Microsoft para desenvolver e executar algoritmos quânticos. Faz parte do [QDK](https://docs.microsoft.com/quantum/), um development kit completo para Q# que pode ser utilizado com ferramentas e linguagens padrão para o desenvolvimento de aplicações quânticas que pode executar em vários ambientes, incluindo no simulador quântico de estado completo incorporado.

Inclui extensões para o Visual Studio e o VS Code e pacotes para utilização com Python e Jupyter Notebook.

O QDK conta com uma biblioteca padrão e bibliotecas especializadas em química, machine learning e números.

A documentação inclui um guia para a linguagem Q#, tutoriais e código de exemplo para que possa começar rapidamente, bem como artigos úteis para compreender melhor os conceitos da computação quântica.  

## <a name="microsoft-quantum-hardware-partners"></a>Parceiros de hardware quântico da Microsoft

A Microsoft está a estabelecer parcerias com empresas de hardware quântico para dar aos programadores acesso na cloud a este tipo de hardware. Tirando partido da plataforma [Azure Quantum](https://azure.microsoft.com/services/quantum/) e da linguagem Q#, os programadores poderão explorar algoritmos quânticos e executar os seus próprios programas quânticos em diferentes tipos de hardware quântico.

Tanto a [IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) como a [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) utilizam processadores **com base em barreira iónica**, que recorrem a iões individuais presos num campo eletrónico, ao passo que a [QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) utiliza circuitos supercondutores.

## <a name="next-steps"></a>Passos seguintes

[Conceitos-chave da computação quântica](xref:microsoft.quantum.overview.understanding)
[Inícios rápidos](xref:microsoft.quantum.welcome)