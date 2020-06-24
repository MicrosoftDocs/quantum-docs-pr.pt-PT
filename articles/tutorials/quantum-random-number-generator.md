---
title: Criar um Gerador de Números Aleatórios Quântico
description: Crie um projeto Q# que demonstre conceitos quânticos básicos, como a sobreposição, ao criar um gerador de números aleatórios quântico.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 18e8975e513a87c0a67a6dbb5586cc7dab5a93fb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275284"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>Tutorial: Implementar um Gerador de Números Aleatórios Quântico em Q\#

Um exemplo simples de um algoritmo quântico escrito em Q# é um gerador de números aleatórios quântico. Este algoritmo tira partido da natureza da mecânica quântica para produzir um número aleatório.

## <a name="prerequisites"></a>Pré-requisitos

- O Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Crie um projeto em Q# para poder [utilizar o Q# a partir da linha de comandos](xref:microsoft.quantum.install.standalone) ou com um [programa anfitrião em Python](xref:microsoft.quantum.install.python) ou com um [programa anfitrião em C#](xref:microsoft.quantum.install.cs).

## <a name="write-a-q-operation"></a>Escrever uma operação Q#

### <a name="q-operation-code"></a>Código de operação Q#

1. Substitua o conteúdo do ficheiro Program.qs pelo seguinte código:

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

Conforme mencionado no nosso artigo [Compreender a computação quântica](xref:microsoft.quantum.overview.understanding), um qubit é uma unidade de informações quânticas que pode estar em sobreposição. Quando medido, um qubit só pode ser 0 ou 1. No entanto, durante a execução, o estado do qubit representa a probabilidade de ler um 0 ou um 1 com uma medição. Este estado de probabilidade é conhecido como sobreposição. Podemos utilizar esta probabilidade para gerar números aleatórios.

Na nossa operação de Q#, apresentamos o tipo de dados `Qubit`, nativo do Q#. Apenas podemos alocar um `Qubit` com uma instrução `using`. Depois de alocados, os qubits estão sempre no estado `Zero`. 

Com a operação `H`, podemos colocar o `Qubit` em sobreposição. Para medir um qubit e ler o seu valor, pode utilizar a operação intrínseca `M`.

Ao colocar o `Qubit` em sobreposição e ao medi-lo, o resultado será um valor diferente sempre que o código for invocado.

Quando um `Qubit` negócio é estabelecido deve ser explicitamente retorcido para o `Zero` estado, caso contrário o simulador reportará um erro de tempo de execução. Uma forma fácil de conseguir isto é ao invocar `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Visualizar o código com a Esfera de Bloch

Na Esfera de Bloch, o polo norte representa o valor clássico **0** e o polo sul representa o valor clássico **1**. Qualquer sobreposição pode ser representada por um ponto na esfera (representada por uma seta). Quanto mais próximo estiver o fim da seta de um polo, maior a probabilidade de o qubit ser incluído no valor clássico atribuído a esse polo quando medido. Por exemplo, o estado do qubit representado pela seta vermelha abaixo tem uma probabilidade mais alta de originar o valor **0** se for medido.

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

Podemos utilizar esta representação para visualizar o que o código está a fazer:

* Primeiro, começamos com um qubit inicializado no estado **0** e aplicamos `H` para criar uma sobreposição em que as probabilidades de **0** e **1** são iguais.

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* Em seguida, medimos o qubit e guardamos a saída:

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

Como o resultado da medição é completamente aleatório, obtivemos um bit aleatório. Podemos chamar esta operação várias vezes para criar números inteiros. Por exemplo, se chamarmos a operação três vezes para obter três bits aleatórios, poderemos criar números aleatórios de 3 bits (ou seja, um número aleatório entre 0 e 7).


## <a name="creating-a-complete-random-number-generator"></a>Criar um gerador de números aleatórios completo

Agora que temos uma operação Q# que gera bits aleatórios, podemos utilizá-la para compilar um gerador de números aleatórios quânticos completo. Podemos utilizar as aplicações de linha de comandos Q# ou um programa anfitrião.



### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[Aplicações de linha de comandos Q# com o Visual Studio ou o Visual Studio Code](#tab/tabid-qsharp)

Para criar a aplicação completa de linha de comandos Q#, adicione o seguinte ponto de entrada ao programa Q#: 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

O executável executará a operação ou função marcada com o atributo `@EntryPoint()` num simulador ou estimador de recursos, consoante a configuração do projeto e as opções da linha de comandos.

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

No Visual Studio, basta premir Ctrl + F5 para executar o script.

No VS Code, crie o ficheiro Program.qs pela primeira vez ao escrever o seguinte no terminal:

```dotnetcli
dotnet build
```

Para as execuções subsequentes, não há necessidade de o criar novamente. Para o executar, escreva o seguinte comando e prima Enter:

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python com o Visual Studio Code ou a Linha de Comandos](#tab/tabid-python)

Para executar o novo programa Q# no Python, guarde o seguinte código como `host.py`:

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

Em seguida, pode executar o programa anfitrião do Python na linha de comandos:

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[C# com o Visual Studio Code ou o Visual Studio](#tab/tabid-csharp)

Para executar o novo programa Q# em C#, modifique `Driver.cs` para incluir o seguinte código C#:

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

Em seguida, pode executar o programa anfitrião de C# na linha de comandos (no Visual Studio, deve premir F5):

```bash
$ dotnet run
The random number generated is 42
```

***
