---
title: Criar um Gerador de Números Aleatórios Quântico
description: Construir um Q# projeto que demonstre conceitos quânticos fundamentais como a superposição criando um gerador de números aleatórios quânticos.
author: bromeg
ms.author: megbrow
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: a0e8933e6a77d017db914e4bb969ea05f760a443
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834045"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>Tutorial: Implementar um Gerador de Números Aleatórios Quântico em Q\#

Um exemplo simples de um algoritmo quântico escrito Q# é um gerador de números aleatórios quânticos. Este algoritmo tira partido da natureza da mecânica quântica para produzir um número aleatório.

## <a name="prerequisites"></a>Pré-requisitos

- O Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Crie um Q# projeto para uma [ Q# aplicação,](xref:microsoft.quantum.install.standalone)com um [programa de anfitrião Python,](xref:microsoft.quantum.install.python)ou um [programa de anfitrião C#](xref:microsoft.quantum.install.cs).

## <a name="write-a-no-locq-operation"></a>Escrever uma Q# operação

### <a name="no-locq-operation-code"></a>Q# código de operação

1. Substitua o conteúdo do ficheiro Program.qs pelo seguinte código:

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

Conforme mencionado no nosso artigo [Compreender a computação quântica](xref:microsoft.quantum.overview.understanding), um qubit é uma unidade de informações quânticas que pode estar em sobreposição. Quando medido, um qubit só pode ser 0 ou 1. No entanto, quando uma operação está em funcionamento, o estado do qubit representa a probabilidade de ler um 0 ou um 1 com uma medição. Este estado de probabilidade é conhecido como sobreposição. Podemos utilizar esta probabilidade para gerar números aleatórios.

Na nossa Q# operação, introduzimos o `Qubit` tipo de dados, nativo Q# de. Apenas podemos alocar um `Qubit` com uma instrução `using`. Depois de alocados, os qubits estão sempre no estado `Zero`. 

Com a operação `H`, podemos colocar o `Qubit` em sobreposição. Para medir um qubit e ler o seu valor, pode utilizar a operação intrínseca `M`.

Ao colocar o `Qubit` em sobreposição e ao medi-lo, o resultado será um valor diferente sempre que o código for invocado.

Quando um `Qubit` é desalocado, tem de ser definido explicitamente de volta para o estado `Zero`. Caso contrário, o simulador reportará um erro de runtime. Uma forma fácil de conseguir isto é ao invocar `Reset`.

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

Agora que temos uma Q# operação que gera bits aleatórios, podemos usá-lo para construir um gerador de números quânticos aleatórios. Podemos usar uma Q# aplicação ou usar um programa de anfitrião.



### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a>[Q# aplicações com Visual Studio ou Visual Studio Code](#tab/tabid-qsharp)

Para criar a Q# aplicação completa, adicione o seguinte ponto de entrada ao seu Q# programa: 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

O programa executará a operação ou função marcada com o `@EntryPoint()` atributo num simulador ou estimador de recursos, dependendo da configuração do projeto e das opções de linha de comando.

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

### <a name="python-with-visual-studio-code-or-the-command-prompt"></a>[Python com Código de Estúdio Visual ou o pedido de comando](#tab/tabid-python)

Para executar o seu novo Q# programa a partir de Python, guarde o seguinte código `host.py` como:

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

Em seguida, pode executar o seu programa de anfitrião Python a partir da solicitação de comando:

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[C# com o Visual Studio Code ou o Visual Studio](#tab/tabid-csharp)

Para executar o seu novo Q# programa a partir de C#, modifique para incluir o seguinte código `Driver.cs` C# :

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

Em seguida, pode executar o seu programa de anfitrião C# a partir da indicação de comando (no Estúdio Visual deve premir F5):

```bash
$ dotnet run
The random number generated is 42
```

***
