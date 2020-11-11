---
title: Notas de versão do Quantum Development kit
description: Fique a par das mais recentes atualizações à pré-visualização do Microsoft Quantum Development kit.
author: bradben
ms.author: v-benbra
ms.date: 8/30/2020
ms.topic: article
uid: microsoft.quantum.relnotes
no-loc:
- Q#
- $$v
ms.openlocfilehash: d38482be17e67f180441440ee8ccc7f1f64ebc9d
ms.sourcegitcommit: fb75d8f30f1d91f644b2a594f46867eb5968cfda
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/10/2020
ms.locfileid: "94448349"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a>Notas de Versão do Microsoft Quantum Development Kit

Este artigo contém informações sobre cada versão do Quantum Development Kit.

Para obter as instruções de instalação, veja o [guia de instalação](xref:microsoft.quantum.install).

Para obter as instruções de atualização, veja o [guia de atualização](xref:microsoft.quantum.update).

## <a name="version-01320111004"></a>Versão 0.13.20111004

*Data de lançamento: 10 de novembro de 2020*

Esta versão desativa as funcionalidades do IntelliSense para Q# ficheiros no Visual Studio e visual Studio Code quando um ficheiro do projeto não está presente. Isto resolve um problema em que as funcionalidades do IntelliSense podem deixar de funcionar depois de adicionar um novo Q# ficheiro a um projeto (ver [qsharp-compilador#720).](https://github.com/microsoft/qsharp-compiler/issues/720)

## <a name="version-01320102604"></a>Versão 0.13.20102604

*Data de lançamento: 27 de outubro de 2020*

Esta versão contém o seguinte:

- A estimativa de recursos emite agora estimativas de profundidade e largura simultaneamente alcançáveis, para além da contagem de qubits. Consulte [aqui](xref:microsoft.quantum.machines.resources-estimator#metrics-reported) para mais detalhes.

Consulte a lista completa de PRs fechados para [bibliotecas,](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22) [compilador,](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22) [tempo de execução,](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22) [amostras,](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22) [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22) e [Katas.](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22)

## <a name="version-01220100504"></a>Versão 0.12.20100504

*Data de lançamento: 5 de outubro de 2020*

Esta versão corrige um bug que afeta a carga de Q# cadernos (ver [iqsharp#331](https://github.com/microsoft/iqsharp/pull/331)).

## <a name="version-01220092803"></a>Versão 0.12.20092803

*Data de lançamento: 29 de setembro de 2020*

Esta versão contém o seguinte:

- O anúncio e o projeto de especificação da [Representação Intermediária Quântica (QIR)](https://github.com/microsoft/qsharp-language/tree/main/Specifications/QIR#quantum-intermediate-representation-qir) destinam-se a ser um formato comum em diferentes extremidades frontais e traseiras. Consulte também a nossa publicação de [blog](https://devblogs.microsoft.com/qsharp/introducing-quantum-intermediate-representation-qir) na QIR.
- Lançamento do nosso novo [ Q# repo linguístico](https://github.com/microsoft/qsharp-language) contendo também a [ Q# documentação](https://github.com/microsoft/qsharp-language/tree/main/Specifications/Language#q-language)completa.
- Melhorias de desempenho para o QuantumSimulator para programas que envolvam um grande número de qubits: melhor aplicação das decisões de fusão de portas; melhor paralelização no sistema Linux; programação inteligente adicionada da execução do portão; correções de insetos.
- As funcionalidades intelliSense são agora suportadas por Q# ficheiros em Visual Studio e Visual Studio Code mesmo sem um ficheiro de projeto.
- Várias Q# melhorias de interoperabilidade /Python e correções de bugs, incluindo um melhor suporte para tipos de dados NumPy.
- Melhorias no espaço de nomes Microsoft.Quantum.Arrays (ver [microsoft/QuantumLibraries#313](https://github.com/microsoft/QuantumLibraries/issues/313)).
- Adicionei uma nova [amostra de Repetição-Até-Sucesso](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/repeat-until-success) que usa apenas dois qubits.

Desde a última libertação, o ramo padrão em cada um dos nossos repositórios de código aberto foi renomeado para `main` .

Consulte a lista completa de PRs fechados para [bibliotecas,](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24) [compilador,](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24) [tempo de execução,](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24) [amostras,](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24) [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24) e [Katas.](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24)

## <a name="version-01220082513"></a>Versão 0.12.20082513

*Data de lançamento: 25 de agosto de 2020*

Esta versão contém o seguinte:

- Novo [espaço de nome Microsoft.Quantum.Random,](xref:Microsoft.Quantum.Random)fornecendo uma forma mais conveniente de provar valores aleatórios dentro dos Q# programas. ([QuantumLibraries#311](https://github.com/microsoft/QuantumLibraries/pull/311), [qsharp-runtime#328](https://github.com/microsoft/qsharp-runtime/pull/328))
- Melhor espaço de [nome Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics) com nova [ `DumpOperation` operação,](xref:Microsoft.Quantum.Diagnostics.DumpOperation)e novas operações para restringir a atribuição de qubits e chamadas oráculos. ([QuantumLibraries#302)](https://github.com/microsoft/QuantumLibraries/pull/302)
- Novo [ `%project` comando mágico](xref:microsoft.quantum.iqsharp.magic-ref.project) em I Q# e [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) em Python para apoiar referências a Q# projetos fora da atual pasta do espaço de trabalho. Consulte [o iqsharp #277](https://github.com/microsoft/iqsharp/issues/277) para as limitações atuais desta funcionalidade. 
- Suporte para carregar automaticamente `.csproj` ficheiros para Q# anfitriões I/Python, que permite que referências de projeto ou pacote externos sejam carregadas no momento da inicialização. Consulte o guia para usar [ Q# com os Cadernos Python e Jupyter](xref:microsoft.quantum.guide.host-programs) para mais detalhes.
- Amostra de Correção de Erro adicionada.Síndrome.
- Adicione acoplamento incapaz ao SimpleIsing.
- Amostra deShift Oculta atualizada.
- Amostra adicionada para resolver o Sudoku com o algoritmo de Grover (contribuição externa)
- Correções gerais de insetos.

Consulte a lista completa de PRs fechados para [bibliotecas,](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) [compilador,](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed) [tempo de execução,](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed) [amostras,](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) e [Katas.](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)  

## <a name="version-01220072031"></a>Versão 0.12.20072031

*Data de lançamento: 21 de julho de 2020*

Esta versão contém o seguinte:

- Espaços de nome abertos em Q# cadernos estão agora disponíveis quando executam todas as células futuras. Isto permite, por exemplo, que os espaços de nomes sejam abertos uma vez numa célula no topo do caderno, em vez de precisarem de abrir espaços de nome relevantes em cada célula de código. Um novo `%lsopen` comando mágico exibe a lista de espaços de nomes atualmente abertos.

Consulte a lista completa de PRs fechados para [bibliotecas,](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) [compilador,](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed) [tempo de execução,](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed) [amostras,](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) e [Katas.](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)  

## <a name="version-01220070124"></a>Versão 0.12.20070124

*Data de lançamento: 2 de julho de 2020*

Esta versão contém o seguinte:

- Nova `qdk-chem` ferramenta para converter formatos de serialização de problemas de estrutura electrónica legacy (por exemplo: FCIDUMP) para [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)
- Novas funções e operações no espaço de [`Microsoft.Quantum.Synthesis`](xref:Microsoft.Quantum.Synthesis) nome para aplicar coerentemente oráculos clássicos usando algoritmos de síntese baseados na transformação e decomposição.
- Agora Q# permito argumentos para os `%simulate` comandos `%estimate` mágicos e outros. Consulte a referência do [ `%simulate` comando mágico](xref:microsoft.quantum.iqsharp.magic-ref.simulate) para mais detalhes.
- Novas opções de visualização de fase em I Q# . Consulte a referência do [ `%config` comando mágico](xref:microsoft.quantum.iqsharp.magic-ref.config) para mais detalhes.
- Eu Q# e o pacote Python somos agora fornecidos através de `qsharp` pacotes conda[(qsharp](https://anaconda.org/quantum-engineering/qsharp) e [iqsharp](https://anaconda.org/quantum-engineering/iqsharp)) para simplificar a instalação local da Q# funcionalidade Jupyter e Python para um ambiente conda. Consulte os [ Q# Cadernos Jupyter](xref:microsoft.quantum.install.jupyter) e com guias de instalação [ Q# Python](xref:microsoft.quantum.install.python) para mais detalhes.
- Ao utilizar o simulador, os qubits já não precisam de estar no estado de [0⟩ após a libertação, mas podem ser automaticamente reiniciados se forem medidos imediatamente antes de serem libertados.
- Atualizações para facilitar aos utilizadores de I Q# consumir pacotes de bibliotecas com diferentes versões QDK, exigindo apenas grandes & números de versão menores correspondem em vez da mesma versão exata
- Removido espaço de nome precotado `Microsoft.Quantum.Primitive.*`
- Operações de deslocação:
  - `Microsoft.Quantum.Intrinsic.Assert` é agora `Microsoft.Quantum.Diagnostics.AssertMeasurement`
  - `Microsoft.Quantum.Intrinsic.AssertProb` é agora `Microsoft.Quantum.Diagnostics.AssertMeasurementProbability`
- Correções de erros 

Consulte a lista completa de PRs fechados para [bibliotecas,](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) [compilador,](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed) [tempo de execução,](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed) [amostras,](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) e [Katas.](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)  

## <a name="version-0112006403"></a>Versão 0.11.2006.403

*Data da versão: 4 de junho de 2020*

Esta versão corrige um bug que afeta a compilação de Q# projetos.

## <a name="version-0112006207"></a>Versão 0.11.2006.207

*Data da versão: 3 de junho de 2020*

Esta versão contém o seguinte:

- Q# cadernos e programas de anfitrião Python não vai mais falhar quando um Q# ponto de entrada está presente
- Atualizações à [Biblioteca padrão](xref:microsoft.quantum.libraries.standard.intro) para utilizar modificadores de acesso
- Agora, o compilador permite o plug-in de passos de reescrita entre passos de reescrita incorporados
- Várias funções e operações preteridas foram removidas de acordo com a agenda descrita nos nossos [princípios de API](xref:microsoft.quantum.contributing.api-design). Q# os programas e bibliotecas que constroem sem avisos na versão 0.11.2004.2825 continuarão a funcionar sem modificação.

Consulte a lista completa de PRs fechados para [bibliotecas,](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) [compilador,](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed) [tempo de execução,](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed) [amostras,](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) e [Katas.](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)  

> [!NOTE]
> Esta versão contém um bug que afeta a compilação de Q# projetos. Recomendamos a atualização para uma versão mais recente.

## <a name="version-01120042825"></a>Versão 0.11.2004.2825

*Data da versão: 30 de abril de 2020*

Esta versão contém o seguinte:

- Novo suporte para Q# aplicações, que já não requerem um ficheiro de anfitrião C# ou Python. Para obter mais informações sobre como começar com Q# as aplicações, consulte [aqui.](xref:microsoft.quantum.install.standalone)
- Início rápido atualizado do gerador de números aleatórios quânticos no sentido de deixar de precisar de um ficheiro anfitrião em C# ou Python. Veja o [Início Rápido](xref:microsoft.quantum.quickstarts.qrng) atualizado
- Melhorias de desempenho nas imagens I Q# Docker

> [!NOTE]
> Q# As aplicações que utilizam o novo [`@EntryPoint()`](xref:Microsoft.Quantum.Core.EntryPoint) atributo não podem ser chamadas atualmente a partir de programas de anfitrião Python ou .NET.
> Veja os guias sobre a interoperabilidade do [Python](xref:microsoft.quantum.install.python) e [.NET](xref:microsoft.quantum.install.cs) para obter mais informações.

## <a name="version-01120033107"></a>Versão 0.11.2003.3107

*Data da versão: 31 de março de 2020*

Esta versão contém pequenas correções de erros para a versão 0.11.2003.2506.

## <a name="version-01120032506"></a>Versão 0.11.2003.2506

*Data da versão: 26 de março de 2020*

Esta versão contém o seguinte:

- Novo suporte para modificadores de acesso em Q# , para mais informações ver Estruturas de [Ficheiros](xref:microsoft.quantum.guide.filestructure)
- Atualizado para SDK de .NET Core 3.1

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilador](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01020022610"></a>Versão 0.10.2002.2610

*Data da versão: 27 de fevereiro de 2020*

Esta versão contém o seguinte:

- Nova biblioteca de Machine Learning Quântico; para obter mais informações, aceda à nossa [página de documentos de QML](xref:microsoft.quantum.machine-learning.concepts.intro).
- Eu Q# bug corre, resultando num aumento de desempenho de 10-20x ao carregar pacotes NuGet

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilador](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01020012831"></a>Versão 0.10.2001.2831

*Data da versão: 29 de janeiro de 2020*

Esta versão contém o seguinte:

- O novo pacote NuGet Microsoft.Quantum.SDK, que substituirá o pacote NuGet Microsoft.Quantum.Development.Kit quando forem criados projetos novos. O pacote NuGet Microsoft.Quantum.Development.Kit continuará a ser suportado para os projetos existentes. 
- Suporte para Q# extensões de compilador, ativado pelo novo packge Microsoft.Quantum.SDK NuGet, para obter mais informações consulte a [documentação no Github,](https://github.com/microsoft/qsharp-compiler/tree/main/src/QuantumSdk#extending-the-q-compiler)a amostra de extensões do [compilador](https://github.com/microsoft/qsharp-compiler/tree/main/examples/CompilerExtensions) e o [ Q# Dev Blog](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/)
- Suporte adicionado para .NET Core 3.1; recomenda-se vivamente ter instalada a versão 3.1.100, uma vez que compilar com versões mais antigas do SDK de .NET Core pode provocar problemas
- Novas transformações de compilador disponíveis em Microsoft.Quantum.QsCompiler.Experimental
- Nova funcionalidade para expor vetores do estado de saída como HTML em IQ#
- Suporte adicionado para EstimateFrequencyA a Microsoft.Quantum.Characterization para testes Hadamard e SWAP
- AmplitudeAmplificação espaço de nome agora usa Q# guia de estilo

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilador](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019120501"></a>Versão 0.10.1912.0501

*Data da versão: 5 de dezembro de 2019*

Esta versão contém o seguinte:

- Novo atributo de teste para Q# testes de unidade, consulte [a](xref:Microsoft.Quantum.Diagnostics.Test) documentação atualizada da API aqui e testes atualizados & guia de depuração [aqui](xref:microsoft.quantum.guide.testingdebugging)
- Vestígios de pilha adicionados no caso de um Q# erro de execução do programa
- Suporte para pontos de interrupção no Visual Studio Code devido a uma atualização na [extensão OmniSharp C# Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilador](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019111607"></a>Versão 0.10.1911.1607

*Data da versão: 17 de novembro de 2019*

Esta versão contém o seguinte:

- Correção de desempenho para [Quantum Katas](https://github.com/Microsoft/QuantumKatas) e blocos de notas Jupyter

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilador](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  


## <a name="version-0101911307"></a>Versão 0.10.1911.307

*Data da versão: 1 de novembro de 2019*

Esta versão contém o seguinte:

- Atualizações para Visual Studio Code & extensões do Visual Studio para implementar servidor de linguagem como um ficheiro executável autossuficiente, eliminando a dependência da versão .NET Core SDK  
- Migração para o .NET Core 3.0
- Alteração interruptiva ao Microsoft.Quantum.Simulation.Core.IOperationFactory com a introdução do novo método `Fail`. Apenas afeta os simuladores personalizados que não abrangem o SimulatorBase. Para obter mais detalhes, [veja o pedido Pull no GitHub](https://github.com/microsoft/qsharp-runtime/pull/59).
- Novo suporte para atributos Preteridos

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilador](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-0919093002"></a>Versão 0.9.1909.3002

*Data da versão: 30 de setembro de 2019*

Esta versão contém o seguinte:

- Novo suporte para Q# a conclusão de código no Visual Studio 2019 (versões 16.3 & depois) & Código do Estúdio Visual
- O novo [Quantum Kata](https://github.com/Microsoft/QuantumKatas) para somadores quânticos

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilador](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-09-packagereference-0919082902"></a>Versão 0.9 ( *PackageReference 0.9.1908.2902* )

*Data da versão: 29 de agosto de 2019*

Esta versão contém o seguinte:

- Novo apoio às [declarações de conjugação](xref:microsoft.quantum.guide.operationsfunctions#conjugations) em Q#
- Novas ações de código no compilador, como: “substituir por”, “adicionar documentação” e uma atualização simples de item de matriz
- Foi adicionado um modelo de instalação e novos comandos de projeto à extensão do Visual Studio Code
- Foram adicionadas novas variantes do combinador ApplyIf, como [Microsoft.Quantum.Canon.ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Quantum Katas](https://github.com/Microsoft/QuantumKatas) adicionais convertidos em Jupyter Notebooks
- A Extensão do Visual Studio agora requer o Visual Studio 2019

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilador](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

As alterações estão resumidas aqui, bem como as instruções para atualizar os programas existentes.  Leia mais sobre estas alterações no [ Q# blog dev.](https://devblogs.microsoft.com/qsharp)

## <a name="version-08-packagereference-0819071701"></a>Versão 0.8 ( *PackageReference 0.8.1907.1701* )

*Data da versão: 12 de julho de 2019*

Esta versão contém o seguinte:

- Novos locais de indexação para segmentar as matrizes; [veja a referência de linguagem](xref:microsoft.quantum.guide.expressions#array-slices) para obter mais informações.
- Added Dockerfile hospedado no [Registo de Contentores](https://github.com/microsoft/ContainerRegistry)da Microsoft , consulte o [ Q# repositório I para obter mais informações](https://github.com/microsoft/iqsharp/blob/main/README.md)
- Alteração interruptiva do [simulador de rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro), atualização das definições de configuração, alterações de nome; veja o [Browser da API .NET para obter os nomes atualizados](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration).

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) e [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-07-packagereference-0719053109"></a>Versão 0.7 ( *PackageReference 0.7.1905.3109* )

*Data da versão: 31 de maio de 2019*

Esta versão contém o seguinte:
- adições à Q# linguagem, 
- Atualizações à biblioteca de química. 
- Uma nova biblioteca numérica.

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) e [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

As alterações estão resumidas aqui, bem como as instruções para atualizar os programas existentes.  Leia mais sobre estas alterações no [ Q# blog dev.](https://devblogs.microsoft.com/qsharp)

### <a name="no-locq-language-syntax"></a>Q# sintaxe linguística
Esta versão adiciona uma nova Q# sintaxe linguística:
* Adicione de itens nomeados para [tipos definidos pelo utilizador](xref:microsoft.quantum.guide.types#user-defined-types).  
* Os construtores de tipos definidos pelo utilizador podem agora ser utilizados como funções.
* Adicione de suporte para [copiar-e-atualizar](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) e [aplicar-e-reatribuir ](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) em tipos definidos pelo utilizador.
* O bloco de correções para ciclos [repetir-até-obter-êxito](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) é agora opcional.
* Agora oferecemos suporte durante ciclos em funções (não em operações).

### <a name="library"></a>Biblioteca 

Esta versão adiciona uma biblioteca numérica: Saiba mais sobre como [utilizar a nova biblioteca numérica](xref:microsoft.quantum.numerics.usage) e experimente as [novas amostras](https://github.com/microsoft/quantum/tree/main/Numerics).  [PR 102](https://github.com/Microsoft/QuantumLibraries/pull/102).  

Esta versão reorganiza as extensões e atualiza a biblioteca de química:
* Melhora a modularidade dos componentes, a extensibilidade e a limpeza de código geral.  [PR 58](https://github.com/microsoft/QuantumLibraries/pull/58).
* Adicione suporte para [wavefunctions de várias referências](xref:microsoft.quantum.chemistry.concepts.multireference), wavefunctions de várias referências dispersas e cluster conjugado unitário.  [PR 110](https://github.com/Microsoft/QuantumLibraries/pull/110).
* (Obrigado!) Contribuidor do [1QBit](https://1qbit.com) ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)): avaliação energética com ansatz de variação. [PR 120](https://github.com/Microsoft/QuantumLibraries/pull/120).
* Atualização do esquema [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) para a nova [versão 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2), ao adicionar a especificação de cluster conjugado unitário. [Problema 65](https://github.com/microsoft/QuantumLibraries/issues/65).
* Adicione interoperabilidade Python às funções da biblioteca de química. Experimente esta [amostra](https://github.com/microsoft/Quantum/tree/main/Chemistry/PythonIntegration). [Problema 53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).

## <a name="version-061905"></a>Versão 0.6.1905

*Data da versão: 3 de maio de 2019*

Esta versão contém o seguinte:
- altera a Q# linguagem, 
- Reestrutura as bibliotecas do Quantum Development Kit. 
- Adiciona novas amostras. 
- Corrige bugs.  Vários PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) e [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

As alterações estão resumidas aqui, bem como as instruções para atualizar os programas existentes.  Pode ler mais sobre estas alterações em devblogs.microsoft.com/qsharp.

### <a name="no-locq-language-syntax"></a>Q# sintaxe linguística
Esta versão adiciona uma nova Q# sintaxe linguística:
* Adicione uma [forma abreviada de expressar especializações de operações quânticas](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations) (controlo e adjacentes) com operadores `+`.  A sintaxe antiga foi preterida.  Os programas que utilizam a sintaxe antiga (por exemplo, `: adjoint`) continuarão a funcionar, mas será gerado um aviso de tempo de compilação.  
* Adicione um novo operador para [copiar-e-atualizar](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions); `w/` pode ser utilizado para expressar a criação de matriz como uma modificação de uma matriz existente.
* Adicione a [instrução aplicar-e-atualizar](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) comum; por exemplo, `+=`, `w/=`.
* Adicione uma forma para especificar um nome abreviado para os espaços de nomes nas [diretivas abertas](xref:microsoft.quantum.guide.filestructure#open-directives).

Com esta versão, deixámos de permitir que um elemento de matriz seja especificado no lado esquerdo de uma instrução definida.  Tal deve-se ao facto de que essa sintaxe indica que as matrizes são mutáveis quando, na verdade, o resultado da operação sempre foi a criação de uma nova matriz com a modificação.  Em vez disso, será gerado um erro do compilador com uma sugestão para utilizar o novo operador copiar-e-colar, `w/`, para conseguir o mesmo resultado.  

### <a name="library-restructuring"></a>Reestruturação das bibliotecas
Esta versão reorganiza as bibliotecas para permitir o aumento das bibliotecas de forma consistente:
* Renomeia o espaço de nomes Microsoft.Quantum.Primitive para Microsoft.Quantum.Intrinsic.  Estas operações são implementadas pelo computador de destino.  O espaço de nomes Microsoft.Quantum.Primitive foi preterido.  Um aviso de runtime indicará quando os programas chamarem operações e funções com nomes preteridos.

* Renomeia o pacote Microsoft.Quantum.Canon para Microsoft.Quantum.Standard.  Este pacote contém espaços de nome que são comuns à maioria Q# dos programas.  Isto inclui:  
    - Microsoft.Quantum.Canon para operações comuns
    - Microsoft.Quantum.Arithmetic para operações aritméticas para fins gerais
    - Microsoft.Quantum.Preparation para operações utilizadas para preparar o estado de qubit
    - Microsoft.Quantum.Simulation para a funcionalidade de simulação

Com esta alteração, poderão ocorrer erros de compilação nos programas que incluem uma única instrução “aberta” para o espaço de nomes Microsoft.Quatum.Canon se o programa referenciar operações que foram movidas para os outros três novos espaços de nomes.  Adicionar as instruções abertas adicionais aos três novos espaços de nomes é uma maneira simples de resolver este problema.  

* Vários espaços de nomes foram preteridos porque as operações no seu interior foram reorganizadas para outros espaços de nomes. Os programas que utilizam estes espaços de nomes vão continuar a funcionar e um aviso de tempo de compilação denotará o espaço de nomes onde é definida a operação.  

* O espaço de nomes Microsoft.Quantum.Arithmetic foi normalizado para utilizar o tipo definido pelo utilizador <xref:Microsoft.Quantum.Arithmetic.LittleEndian>. Utilize a função [BigEndianAsLittleEndian](xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian), quando necessário, para converter para little endian.  

* Os nomes de várias chamadas (funções e operações) foram alterados de acordo com o [ Q# Guia de Estilo.](xref:microsoft.quantum.contributing.style)  Os antigos nomes disponíveis foram preteridos.  Os programas que utilizam os antigos nomes disponíveis continuarão a funcionar com um aviso de tempo de compilação. 

### <a name="new-samples"></a>Novos Exemplos

Adicionámos uma [amostra de utilização Q# com o condutor F#](https://github.com/Microsoft/Quantum/pull/164).  

**Obrigado** ao seguinte contribuidor da nossa base de código aberto em http://github.com/Microsoft/Quantum. Estas contribuições acrescentam significativamente às ricas amostras de Q# código:

* Mathias Soeken ([@msoeken](https://github.com/msoeken)): síntese da função Oracle. [PR 135](https://github.com/Microsoft/Quantum/pull/135).

### <a name="migrating-existing-projects-to-061905"></a>Migração de projetos existentes para 0.6.1905.

Veja o [guia de instalação](xref:microsoft.quantum.install) para atualizar o QDK.
  
Se tem Q# projetos existentes a partir da versão 0.5 do Kit de Desenvolvimento Quântico, os seguintes são os passos para migrar esses projetos para a versão mais recente.

1. Os projetos precisam de ser atualizados por ordem.  Se tiver uma solução com vários projetos, atualize cada um deles pela ordem em que estão referenciados.
2. A partir de um pedido de comando, corra `dotnet clean` para remover todos os binários existentes e ficheiros intermédios.
3. Num editor de texto, edite o ficheiro .csproj para alterar a versão de todas as `PackageReference` do “Microsoft.Quantum” para a versão 0.6.1904 e altere o nome do pacote “Microsoft.Quantum.Canon” para “Microsoft.Quantum.Standard”, por exemplo:

    ```xml
    <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
    <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
    ```
4. A partir da pronta de comando, executar este comando: `dotnet msbuild`  
5. Depois de o fazer, poderá continuar a precisar de resolver manualmente os erros relacionados com as alterações listadas acima.  Em muitos casos, estes erros também serão comunicados pelo IntelliSense no Visual Studio ou no Visual Studio Code.
    - Abra a pasta raiz do projeto ou a solução contida no Visual Studio 2019 ou no Visual Studio Code.
    - Depois de abrir um ficheiro .qs no editor, deverá ver a saída da extensão do Q# idioma na janela de saída.
    - Depois de carregar o projeto com êxito (indicado na janela de resultados), abra cada ficheiro manualmente para resolver todos os problemas restantes.

> [!NOTE]
> * Na versão 0.6, o servidor de linguagem incluído no Quantum Development Kit não suporta várias áreas de trabalho.
> * Para trabalhar com um projeto no Visual Studio Code, abra a pasta raiz que contém o projeto em si e todos os projetos referenciados.   
> * Para poder trabalhar com uma solução no Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das suas subpastas.  
> * As referências entre projetos migrados para a versão 0.6 e posterior e os projetos que utilizam versões de pacotes mais antigas **não** são suportadas.

## <a name="version-051904"></a>Versão 0.5.1904

*Data da versão: 15 de abril de 2019*

Esta versão contém correções de bugs.


## <a name="version-051903"></a>Versão 0.5.1903

*Data da versão: 27 de março de 2019*

Esta versão contém o seguinte:

- Adiciona suporte ao Jupyter Notebook, que oferece uma ótima maneira de aprender Q# sobre.  [Veja os novos exemplos do Jupyter Notebook e saiba como escrever os seus próprios Notebooks](xref:microsoft.quantum.install). 

- Adiciona aritmética de somador de números inteiros à biblioteca Quantum Canon.  Veja também um Jupyter Notebook que [descreve como utilizar os novos somadores de números inteiros](https://github.com/microsoft/Quantum/blob/main/samples/arithmetic/AdderExample.ipynb).

- Correção de bug para o problema do DumpRegister comunicado pela Comunidade ([148](https://github.com/Microsoft/Quantum/issues/148)).

- Foi adicionada a capacidade de devolução a partir de uma [instrução de utilização](xref:microsoft.quantum.guide.qubits#allocating-qubits).

- [Guia de introdução](xref:microsoft.quantum.install) remodelado.


## <a name="version-051902"></a>Versão 0.5.1902

*Data da versão: 27 de fevereiro de 2019*

Esta versão contém o seguinte:

- Adiciona suporte para um anfitrião Python de várias plataformas.  O `qsharp` pacote para Python facilita a simulação de Q# operações e funções a partir de Dentro de Python. Saiba mais sobre a [interoperabilidade do Python](xref:microsoft.quantum.install). 

- As extensões do Visual Studio e do Visual Studio Code agora suportam a alteração de nome dos símbolos (por exemplo, funções e operações).

- A extensão do Visual Studio agora pode ser instalada no Visual Studio 2019.

## <a name="version-041901"></a>Versão 0.4.1901

*Data da versão: 30 de janeiro de 2019*

Esta versão contém o seguinte:

- Adiciona suporte para um novo tipo primitivo, BigInt, que representa um número inteiro com sinal de tamanho arbitrário.  Saiba mais sobre o [tipo BigInt](xref:microsoft.quantum.guide.types).
- Adiciona o novo simulador Toffoli, um simulador rápido para fins gerais que pode simular operações quânticas X, CNOT e X com vários controladores com números muito grandes de qubits.  Saiba mais sobre o [Simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator).
- adiciona um simples estimador de recursos que estima os recursos necessários para executar uma determinada instância de uma Q# operação num computador quântico.  Saiba mais sobre o [Estimador de Recursos](xref:microsoft.quantum.machines.resources-estimator).


## <a name="version-0318112802"></a>Versão 0.3.1811.2802

*Data da versão: 28 de novembro de 2018*

Embora a nossa extensão do VS Code não a estivesse a utilizar, foi sinalizada e removida do marketplace durante [a remoção de extensões](https://code.visualstudio.com/blogs/2018/11/26/event-stream) relacionada com o pacote NPM `event-stream`. Esta versão remove todas as dependências de runtime que podem fazer com que a extensão acione sinalizadores vermelhos.

Se anteriormente tiver instalado a extensão, terá de instalá-la novamente. Para tal, aceda à extensão [Microsoft Quantum Development Kit para Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode) no Marketplace do Visual Studio e prima Instalar. Lamentamos o inconveniente.


## <a name="version-0318111511"></a>Versão 0.3.1811.1511

*Data da versão: 20 de novembro de 2018*

Esta versão corrige um bug que impedia que alguns utilizadores carregassem com êxito a extensão do Visual Studio.

## <a name="version-031811203"></a>Versão 0.3.1811.203

*Data da versão: 2 de novembro de 2018*

Esta versão inclui algumas correções de bugs, incluindo:

* A invocação de `DumpMachine` poderia alterar o estado do simulador em determinadas situações.
* Foram removidos os avisos de compilação durante a compilação de projetos com uma versão do .NET Core anterior à 2.1.403.
* Limpeza da documentação, especialmente das descrições mostradas durante a passagem do rato no VS Code ou no Visual Studio.

## <a name="version-0318102508"></a>Versão 0.3.1810.2508

*Data da versão: 29 de outubro de 2018*

Esta versão inclui novos recursos de linguagem e uma experiência de programação melhorada:

* Esta versão inclui um servidor de idiomas Q# para, bem como as integrações do cliente para Visual Studio e Visual Studio Code. Tal permite um novo conjunto de funcionalidades do IntelliSense, juntamente com os comentários em direto sobre a escrita de sublinhados ondulados de erros e avisos. 
* Esta atualização melhora bastante as mensagens de diagnóstico em geral, com navegação fácil e intervalos precisos para diagnóstico e detalhes adicionais nas informações apresentadas durante a passagem do rato.
* A Q# linguagem foi estendida de forma a unificar a forma como os desenvolvedores podem fazer operações comuns e novos melhoramentos às características linguísticas para expressar poderosamente a computação quântica.  Há um punhado de mudanças de rutura na Q# linguagem com esta versão.   

Esta versão também inclui uma nova biblioteca de química quântica:

* A biblioteca de química contém novas funcionalidades de simulação Hamiltoniana, incluindo:
    - Integradores de Trotter–Suzuki de ordem arbitrária igual para melhorar a precisão da simulação.
    - Técnica de simulação de “qubitization” com otimizações específicas de química para reduzir a complexidade de $T $-gate.
* Foi introduzido um novo esquema open source, chamado esquema Broombridge (em referência a um [ponto de referência](https://en.wikipedia.org/wiki/Broom_Bridge) celebrado como o lugar de nascimento dos Hamiltonianos), para importar representações de moléculas e para as simular.
* São fornecidas várias representações químicas definidas com o esquema Broombridge.  Estes modelos foram gerados por [NWChem](http://www.nwchem-sw.org/), uma ferramenta química computacional de alto desempenho open source.
* Os tutoriais e exemplos descrevem como utilizar a biblioteca de química e os modelos de dados Broombridge para:
    - Construir Hamiltonianos simples com a biblioteca de química
    - Visualizar energias no estado estacionário e de excitação de Hidreto de Lítio com a estimativa de fase.
    - Executar estimativas de recursos da simulação química quântica.
    - Estimar os níveis de energia de moléculas representados pelo esquema Broombridge.
* A documentação descreve como usar o NWChem para gerar modelos químicos adicionais para simulação quântica com Q# .

Saiba mais sobre a [biblioteca de química do Quantum Development Kit](xref:microsoft.quantum.chemistry.concepts.intro).

Com a nova biblioteca de química, estamos a separar as bibliotecas num novo repositório GitHub, [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries).  Os exemplos continuam no repositório [Microsoft/Quantum](https://github.com/Microsoft/Quantum).  As contribuições para ambos são bem-vindas!

Esta versão inclui correções de bugs e funcionalidades para problemas denunciados pela comunidade:

* Intellisense Q# para? ([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).
* Ficheiros .qs ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).
* Melhore a mensagem de erro quando as chavetas são abreviadas na instrução if ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).
* Suporte para desconstrução de cadeias de identificação na (re)vínculação mutável ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).
* Erro ao executar BitFlipCode fornecido ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).
* A H2SimulationGUI às vezes apresenta picos elevados ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).

### <a name="community-contributions"></a>Contribuições da Comunidade

**Obrigado** aos seguintes contribuidores da nossa base de código aberto em http://github.com/Microsoft/Quantum. Estas contribuições acrescentam significativamente às ricas amostras de Q# código:

* Rolf Huisman [@RolfHuisman](https://github.com/RolfHuisman) (): Melhorou a experiência para os desenvolvedores da QASM, Q# criando um QASM para Q# tradutor. [PR 58](https://github.com/Microsoft/Quantum/pull/58).

* Andrew Helwer ([@ahelwer](https://github.com/ahelwer)):  contribuiu com um exemplo ao implementar o Jogo CHSH, um jogo quântico relacionado com a não localidade.  [PR 84](https://github.com/Microsoft/Quantum/pull/84).

Agradecemos também a Rohit Gupta ([@guptarohit](https://github.com/guptarohit),[PR 90](https://github.com/Microsoft/quantum/pull/90)), Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[PR 289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)) e Lee James O'Riordan ([@mlxd](https://github.com/mlxd),[PR 96](https://github.com/Microsoft/Quantum/pull/96)) por todo o trabalho em melhorar o conteúdo para todos nós através da correção da documentação, da ortografia e de gralhas. 

## <a name="version-021809701"></a>Versão 0.2.1809.701

*Data da versão: 10 de setembro de 2018*

Esta versão inclui correções de bugs para problemas denunciados pela comunidade. Incluindo:

* Não é possível utilizar o operador shift ([GitHub](https://github.com/Microsoft/Quantum/issues/75)).
* `DumpMachine` / `DumpRegister` falha no `QCTraceSimulator` ao imprimir para a consola ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680)).
* Permitir a alocação de 0 qubits ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits)).
* O `AssertQubitState` requer a chamada Complex() explícita ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call)).
* A operação `Measure` devolve sempre `One` no macOS ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).

Obrigado! 

## <a name="version-0218063001"></a>Versão 0.2.1806.3001

*Data da versão: 30 de junho de 2018*

Esta versão é apenas uma correção rápida para [o problema #48 reportada no GitHub](https://github.com/Microsoft/Quantum/issues/48) Q# (a compilação falha se o nome do utilizador contiver um espaço em branco). Siga as mesmas instruções de atualização que a `0.2.1806.1503` com a nova versão correspondente (`0.2.1806.3001-preview`).

## <a name="version-0218061503"></a>Versão 0.2.1806.1503

*Data da versão: 22 de junho de 2018*

Esta versão inclui várias contribuições da comunidade, bem como uma experiência de depuração melhorada e um melhor desempenho.  Mais concretamente:

* Melhorias no desempenho em simulações pequenas e grandes no computador de destino QuantumSimulator.
* Funcionalidade de depuração melhorada.
* Contribuições da comunidade para correções de bugs, novas funções do programa auxiliar, operações e novos exemplos.

### <a name="performance-improvements"></a>Melhorias no desempenho

Esta atualização inclui melhorias significativas no desempenho para a simulação de números grandes e pequenos de qubits em todos os computadores de destino.  Esta melhoria é facilmente visível com a simulação H<sub>2</sub>, que é um exemplo padrão no Quantum Development Kit.

### <a name="improved-debugging-functionality"></a>Funcionalidade de depuração melhorada

Esta atualização adiciona a nova funcionalidade de depuração:
* Foram adicionadas duas novas operações, @"microsoft.quantum.extensions.diagnostics.dumpmachine" e @"microsoft.quantum.extensions.diagnostics.dumpregister", que geram informações de função de onda sobre o computador quântico num determinado momento.  
* No Visual Studio, a probabilidade de medir um $\ket{1}$ num único qubit é agora mostrada automaticamente na janela de depuração do computador de destino QuantumSimulator.
* No Visual Studio, foi melhorada a apresentação das propriedades variáveis nas janelas de depuração **Automóveis** e **Locais**. 

Saiba mais sobre [Teste e Depuração](xref:microsoft.quantum.guide.testingdebugging).

### <a name="community-contributions"></a>Contribuições da Comunidade

A Q# comunidade de codificadores está a crescer e estamos entusiasmados por ver o primeiro utilizador a contribuir com bibliotecas e amostras que foram submetidas à nossa base de código aberto em http://github.com/Microsoft/quantum .  **O nosso muito obrigado** aos seguintes contribuidores:
* Mathias Soeken ([@msoeken](https://github.com/msoeken)): contribuiu com um exemplo que define um método de síntese de lógica baseado em transformação que constrói redes Toffoli para implementar uma determinada permutação. O código está escrito inteiramente em Q# funções e operações.  [PR 41](https://github.com/Microsoft/Quantum/pull/41).
* RolfHuisman [@RolfHuisman](https://github.com/RolfHuisman) (): Microsoft MVP Rolf Huisman contribuiu com uma amostra que gera código QASM plano a partir de Q# código para uma classe restrita de programas que não têm fluxo de controlo clássico e operações quânticas restritas. [PR 59](https://github.com/Microsoft/Quantum/pull/59)
* Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)): ajudou a melhorar a nossa base de código ao submeter uma função de biblioteca para operações controladas. [PR 53](https://github.com/Microsoft/Quantum/pull/53)
* Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)): corrigiu @"microsoft.quantum.canon.quantumphaseestimation" e criou novos testes de unidade.  [PR 54](https://github.com/Microsoft/Quantum/pull/54)
* Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)): limpou o exemplo de Teletransporte ao garantir que a instância do QuantumSimulator é eliminada. [PR 20](https://github.com/Microsoft/Quantum/pull/20)

Além disso, um enorme **obrigado** a estes Engenheiros de Software da Microsoft dos contribuidores da equipa de Serviços de Engenharia Comercial, que fizeram alterações valiosas à nossa documentação durante a Hackathon.  As alterações melhoraram muito a clareza e a experiência de integração para todos nós:
* Sascha Corti
* Mihaela Curmei
* John Donnelly
* Kirill Logachev
* Jan Pospisil
* Anita Ramanan
* Frances Tibble
* Alessandro Vozza

### <a name="update-existing-projects"></a>Atualizar projetos existentes

Esta versão é totalmente compatível com versões anteriores. Basta atualizar os pacotes NuGet nos projetos para a versão `0.2.1806.1503-preview` e fazer uma **recompilação completa** para garantir que todos os ficheiros intermediários são regenerados.

No Visual Studio, siga as instruções normais sobre como [atualizar um pacote](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package).

Para atualizar os modelos do projeto da linha de comandos, execute o seguinte comando:
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

Depois de executar este comando, todos os novos projetos criados com o `dotnet new <project-type> -lang Q#` utilizarão automaticamente esta versão do Quantum Development Kit.

Para atualizar um projeto existente para utilizar a versão mais recente, execute o seguinte comando dentro do diretório de cada projeto:

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

Se um projeto existente também utilizar a integração XUnit para testes de unidades, poderá utilizar um comando semelhante para atualizar também esse pacote:
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

Dependendo da versão do XUnit que o projeto de teste utiliza, talvez também tenha de atualizar o XUnit para a versão 2.3.1:
```
dotnet add package xunit -v "2.3.1" 
```

Após a atualização, confirme que remove todos os ficheiros temporários gerados pela versão anterior. Para tal, faça o seguinte:
```
dotnet clean 
```

### <a name="known-issues"></a>Problemas Conhecidos

Nenhum problema conhecido adicional a comunicar.


## <a name="version-0218022202"></a>Versão 0.2.1802.2202

*Data da versão: 26 de fevereiro de 2018*

Esta versão oferece suporte para desenvolvimento em mais plataformas, interoperabilidade da linguagem e melhorias de desempenho. Mais concretamente:

- Suporte para desenvolvimento baseado no macOS e no Linux. 
- Compatibilidade com .NET Core, incluindo suporte para o Visual Studio Code nas várias plataformas.
- Uma licença de Open Source completa para as Bibliotecas do Quantum Development Kit.
- Melhoria do desempenho do simulador em projetos que exigem 20 ou mais qubits.
- Interoperabilidade com a linguagem Python (versão de pré-visualização disponível no Windows).

### <a name="net-editions"></a>Edições .NET

A plataforma .NET está disponível através de duas edições diferentes, o .NET Framework fornecido com o Windows e o .NET Core open-source que está disponível no Windows, no macOS e no Linux.
Com esta versão, a maioria das partes do Quantum Development Kit são fornecidas como bibliotecas para o .NET Standard, o conjunto de classes comum ao Framework e ao Core.
Portanto, estas bibliotecas são compatíveis com as versões recentes do .NET Framework e do .NET Core.

Assim, para ajudar a garantir que os projetos escritos com o Quantum Development Kit são o mais portáteis possíveis, recomendamos que os projetos da biblioteca escritos com o Quantum Development Kit tenham como destino o .NET Standard, enquanto as aplicações de consola tenham como destino o .NET Core.
Uma vez que as versões anteriores do Quantum Development Kit suportavam apenas o .NET Framework, talvez seja necessário migrar os projetos existentes; veja as informações abaixo para saber como fazer isso.

### <a name="project-migration"></a>Migração de Projetos

Os projetos criados com versões anteriores do Quantum Development Kit vão continuar a funcionar, desde que não atualize os pacotes do NuGet utilizados nos mesmos. Para migrar código existente para a nova versão, execute os seguintes passos:
1. Crie um novo projeto .NET Core utilizando o tipo certo de modelo de Q# projeto (Aplicação, Biblioteca ou Projeto de Teste).
2. Copie os ficheiros .qs e .cs/.fs existentes do projeto antigo para o novo projeto (através de Adicionar > Item Existente). Não copie o ficheiro AssemblyInfo.cs.
3. Crie e execute o novo projeto.

Note que a operação RandomWalkPhaseEstimation do espaço de nomes Microsoft.Quantum.Canon foi movida para o espaço de nomes Microsoft.Research.Quantum.RandomWalkPhaseEstimation no repositório [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc).

### <a name="known-issues"></a>Problemas Conhecidos

- A `--filter` opção de `dotnet test` não funcionar corretamente para os testes escritos em Q# .
  Como resultado, os testes individuais por unidade não podem ser executados no Código do Estúdio Visual; recomendamos a utilização `dotnet test` na solicitação de comando para reecatar todos os testes.

## <a name="version-0118011707"></a>Versão 0.1.1801.1707

*Data da versão: 18 de janeiro de 2018*

Esta versão corrige alguns problemas denunciados pela comunidade. Nomeadamente:

- O simulador agora funciona com CPUs que não estavam inicialmente ativadas para AVX.
- As definições decimais regionais não farão com que o Q# parser falhe.
- A operação primitiva `SignD` devolve agora `Int` em vez de `Double`.


## <a name="version-011712901"></a>Versão 0.1.1712.901

*Data da versão: 11 de dezembro de 2017*

### <a name="known-issues"></a>Problemas Conhecidos

#### <a name="hardware-and-software-requirements"></a>Requisitos de Hardware e Software

- O simulador incluído no Quantum Development Kit requer uma instalação de 64 bits do Microsoft Windows para poder ser executado.
- O simulador quântico da Microsoft, instalado com o Quantum development kit, utiliza Extensões de Vetor Avançadas (AVX) e requer uma CPU compatível com AVX. Os processadores Intel fornecidos no Q1 2011 (Sandy Bridge) ou posterior suportam AVX. Estamos a avaliar o suporte para CPUs anteriores e poderemos anunciar mais pormenores mais tarde.

#### <a name="project-creation"></a>Criação de Projetos

- Ao criar uma solução (.sln) que irá Q# utilizar, a solução deve ser um diretório superior a cada projeto (.csproj) na solução. Ao criar uma nova solução, poderá conseguir isso ao garantir que a caixa de verificação “Criar diretório da solução” está marcada na caixa de diálogo “Novo Projeto”. Se não o fizer, os pacotes NuGet do Quantum Development Kit terão de ser instalados manualmente.

#### Q#

- O Intellisense não apresenta erros adequados para Q# o código. Certifique-se de que está a apresentar erros de construção na Lista de Erros do Estúdio Visual para ver Q# erros corretos. Note também que Q# os erros só aparecerão depois de ter feito uma construção.
- Utilizar uma matriz mutável numa aplicação parcial pode levar a um comportamento inesperado.
- Vincular uma matriz imutável a uma matriz mutável (por exemplo, a = b, em que b é uma matriz mutável) pode levar a um comportamento inesperado.
- A perfis, a cobertura de código e outros plugins VS podem nem sempre contar Q# linhas e blocos com precisão.
- O Q# compilador não valida as cordas interpoladas. É possível criar erros de compilação C# ortografia de nomes variáveis ou usando expressões em Q# cordas interpoladas.

#### <a name="simulation"></a>Simulação

- O QuantumSimulator utiliza OpenMP para paralelizar a álgebra linear necessária. Por predefinição, o OpenMP utiliza todos os threads de hardware disponíveis, o que significa que os programas com pequenos números de qubits serão normalmente executados lentamente, pois a coordenação necessária diminuirá o trabalho real. Esse erro pode ser corrigido ao definir a variável de ambiente OMP_NUM_THREADS para um número pequeno. Como regra geral muito superficial, um thread é bom para um máximo de quatro qubits e, em seguida, um thread adicional por qubit é bom, embora isto seja altamente dependente do algoritmo.

#### <a name="debugging"></a>Depurar

- F11 (passo a passo) não funciona em Q# código.
- O código realçando em Q# código num ponto de rutura ou uma pausa de um único passo é por vezes impreciso. A linha correta será realçada, mas às vezes o realce começa e termina em colunas incorretas na linha.

#### <a name="testing"></a>Testar

- Os testes devem ser efetuados em modo de 64 bits. Se os testes estiverem a falhar com um BadImageFormatException, aceda ao menu Teste e selecione Definições de Teste > (Arquitetura do Processador Predefinida) > x64.
- Alguns testes demoram muito tempo (possivelmente até cinco minutos, dependendo do computador) a ser executados. Tal é normal, pois alguns utilizam mais de 20 qubits; o nosso maior teste atualmente é executado em 23 qubits.

#### <a name="samples"></a>Amostras

- Em certos computadores, alguns exemplos pequenos poderão ser executados lentamente exceto se a variável de ambiente OMP_NUM_THREADS estiver definida como “1”. Veja também a nota de versão em “Simulação”.

#### <a name="libraries"></a>Bibliotecas

- Existe uma pressuposição implícita de que os qubits que passaram para uma operação em argumentos diferentes são todos distintos. Por exemplo, todas as operações da biblioteca (e todos os simuladores) pressupõem que os dois qubits passaram para um NOT controlado são qubits diferentes. Desrespeitar esta pressuposição pode levar a algo inesperado imprevisível. É possível testar isso com o simulador de rastreio do computador quântico.
- A função Microsoft.Quantum.Bind pode não funcionar conforme o esperado em todos os casos.
- No espaço de nomes Microsoft.Quantum.Extensions.Math, a função SignD devolve um Double, em vez de um Int, embora a função System.Math.Sign subjacente devolva sempre um número inteiro. É seguro comparar o resultado com 1.0, -1.0 e 0.0, uma vez que estes doubles têm todos representações binárias exatas.
