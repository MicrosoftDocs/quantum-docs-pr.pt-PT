---
title: Executar o algoritmo de pesquisa de Grover em Q# – Quantum Development Kit
description: Crie um projeto Q# que demonstre o algoritmo de Grover, um dos algoritmos quânticos canónicos.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 0e64fcd56929fa33397c45bf1b2e99bf687eca6f
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906955"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a>Início Rápido: Implementar o algoritmo de pesquisa de Grover em Q#

Neste guia de Início Rápido, pode aprender a compilar e executar a pesquisa de Grover para acelerar a pesquisa de dados não estruturados.  A pesquisa de Grover é um dos mais populares algoritmos de computação quântica e esta implementação de Q# relativamente pequena permite-lhe ter uma noção de algumas das vantagens da programação de soluções quânticas com uma linguagem de programação quântica Q# de alto nível para expressar algoritmos quânticos.  No final do guia, verá o resultado da simulação que demonstra como encontrar com êxito uma cadeia específica numa lista de entradas desordenadas numa fração do tempo que levaria a pesquisar toda a lista num computador clássico.

O algoritmo de Grover procura itens específicos numa lista de dados não estruturados. Por exemplo, pode responder à pergunta: Esta carta tirada de um baralho de cartas é um ás de copas? A identificação do item específico é chamada _entrada marcada_.

Com o algoritmo de pesquisa de Grover, é garantido que um computador quântico executa esta pesquisa em menos passos do que o número de itens contidos na lista onde está a efetuar a pesquisa — algo que nenhum algoritmo clássico consegue fazer. A maior velocidade no caso de um baralho de cartas é insignificante; no entanto, em listas que contenham milhões ou milhares de milhões de itens, torna-se significativa.

Pode criar o algoritmo de pesquisa de Grover com apenas algumas linhas de código.

## <a name="prerequisites"></a>Pré-requisitos

- O Microsoft [Quantum Development Kit][install].

## <a name="what-does-grovers-search-algorithm-do"></a>O que é que algoritmo de pesquisa de Grover faz?

O algoritmo de Grover pergunta se um item contido na lista é aquele de que estamos à procura. O algoritmo faz isto ao construir uma sobreposição quântica dos índices da lista com cada coeficiente ou amplitude de probabilidade, de forma a representar a probabilidade desse índice específico ser aquele de que está à procura.

No centro do algoritmo existem dois passos que aumentam incrementalmente o coeficiente do índice de que estamos à procura, até que a amplitude de probabilidade desse coeficiente se aproxime de um.

O número de aumentos incrementais é inferior ao número de itens contidos na lista. É por isso que o algoritmo de pesquisa de Grover executa a pesquisa em menos passos do que qualquer algoritmo clássico.

![Diagrama funcional do algoritmo de pesquisa de Grover](~/media/grover.png)

## <a name="write-the-code"></a>Escrever o código

1. Através do Quantum Development Kit, [crie um novo projeto Q#](xref:microsoft.quantum.howto.createproject) chamado `Grover`, no ambiente de desenvolvimento de eleição.

1. Adicione o seguinte código ao ficheiro `Operations.qs` no novo projeto:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-40":::

1. Para definir a lista que estamos a pesquisar, crie um novo ficheiro `Reflections.qs` e cole no seguinte código:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    A operação `ReflectAboutMarked` define a entrada marcada que está a pesquisar: a cadeia de zeros e uns alternados. Esta amostra codifica a entrada marcada e pode ser expandida para pesquisar entradas diferentes ou generalizadas para qualquer entrada.

1. Em seguida, execute o novo programa Q# para encontrar o item marcado pela operação `ReflectAboutMarked`.

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python com o Visual Studio Code ou a Linha de Comandos](#tab/tabid-python)

    Para executar o novo programa Q# no Python, guarde o seguinte código como `host.py`:

    :::code language="python" source="~/quantum/samples/algorithms/simple-grover/host.py" range="9-14":::

    Em seguida, pode executar o programa anfitrião do Python na linha de comandos:

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# com o Visual Studio Code ou a Linha de Comandos](#tab/tabid-csharp)

    Para executar o novo programa Q# em C#, modifique `Driver.cs` para incluir o seguinte código C#:

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    Em seguida, pode executar o programa anfitrião de C# na linha de comandos:

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019"></a>[C# com o Visual Studio 2019](#tab/tabid-vs2019)

    Para executar o novo programa Q# em C# no Visual Studio, modifique `Driver.cs` para incluir o seguinte código C#:

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    Em seguida, prima F5, o programa iniciará a execução e será apresentada uma nova janela com os seguintes resultados: 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    A operação `ReflectAboutMarked` é chamada apenas quatro vezes, mas o programa Q# conseguiu encontrar a entrada “01010” entre $2^{5} = 32$ entradas possíveis!

## <a name="next-steps"></a>Passos seguintes

Se gostou deste e início rápido, veja alguns dos recursos abaixo para saber mais sobre como pode utilizar a Q# para escrever as suas próprias aplicações quânticas:

- [Voltar à Introdução com o guia do QDK](xref:microsoft.quantum.welcome)
- Experimente uma [amostra](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) do algoritmo de pesquisa de Grover mais geral
- [Saiba mais sobre a pesquisa de Grover com os Quantum Katas](xref:microsoft.quantum.overview.katas)
- Leia mais sobre [Amplificação de amplitude](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), a técnica de computação quântica em que se baseia o algoritmo de pesquisa de Grover
- [Conceitos de computação quântica](xref:microsoft.quantum.concepts.intro)
- [Amostras do Quantum Development Kit](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
