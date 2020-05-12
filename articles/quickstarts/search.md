---
title: Executar o algoritmo de pesquisa de Grover em Q# – Quantum Development Kit
description: Crie um projeto Q# que demonstre o algoritmo de Grover, um dos algoritmos quânticos canónicos.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: c67ccd16957ceef694552bdd9c073ba5a35d8aaf
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82686835"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a>Início Rápido: implementar o algoritmo de pesquisa de Grover em Q\#

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

1. Adicione o seguinte código ao ficheiro `Program.qs` no novo projeto:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. Para definir a lista que estamos a pesquisar, crie um novo ficheiro `Reflections.qs` e cole no seguinte código:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    A operação `ReflectAboutMarked` define a entrada marcada que está a pesquisar: a cadeia de zeros e uns alternados. Esta amostra codifica a entrada marcada e pode ser expandida para pesquisar entradas diferentes ou generalizadas para qualquer entrada.

1. Em seguida, execute o novo programa Q# para encontrar o item marcado pela operação `ReflectAboutMarked`.

### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>Aplicações de linha de comandos Q# com o Visual Studio ou o Visual Studio Code

O executável executará a operação ou função marcada com o atributo `@EntryPoint()` num simulador ou estimador de recursos, consoante a configuração do projeto e as opções da linha de comandos.

No Visual Studio, basta premir Ctrl + F5 para executar o script.

No VS Code, crie o ficheiro `Program.qs` pela primeira vez ao escrever o seguinte no terminal:

```Command line
dotnet build
```

Para as execuções subsequentes, não há necessidade de o criar novamente. Para o executar, escreva o seguinte comando e prima Enter:

```Command line
dotnet run --no-build
```

Deverá ser apresentada a seguinte mensagem no terminal:

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

Isto acontece porque não especificou o número de qubits que queria utilizar, pelo que o terminal indica os comandos disponíveis para o executável. Se quisermos utilizar 5 qubits, devemos escrever:

```Command line
dotnet run --n-qubits 5
```

Deverá ver o resultado seguinte quando premir Enter:

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a>Passos seguintes

Se gostou deste e início rápido, veja alguns dos recursos abaixo para saber mais sobre como pode utilizar a Q# para escrever as suas próprias aplicações quânticas:

- [Voltar à Introdução com o guia do QDK](xref:microsoft.quantum.welcome)
- Experimente uma [amostra](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) do algoritmo de pesquisa de Grover mais geral
- [Saiba mais sobre a pesquisa de Grover com os Quantum Katas](xref:microsoft.quantum.overview.katas)
- Leia mais sobre [Amplificação de amplitude][amplitude-amplification], a técnica de computação quântica em que se baseia o algoritmo de pesquisa de Grover
- [Conceitos de computação quântica](xref:microsoft.quantum.concepts.intro)
- [Amostras do Quantum Development Kit](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
