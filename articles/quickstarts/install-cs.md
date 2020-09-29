---
title: Desenvolver com Q# e .NET
description: Saiba como criar uma aplicação Q# com linguagens .NET.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: e8733918daa02afaea0fc1994d5f0851d4be9b93
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834334"
---
# <a name="develop-with-no-locq-and-net"></a>Desenvolver com Q# e .NET

O Q# foi criado para funcionar bem com linguagens .NET, como C# e F#.
Neste guia, vamos demonstrar como utilizar o Q# com um programa anfitrião escrito numa linguagem .NET.

Primeiro, vamos criar a aplicação Q# e o anfitrião .NET e, em seguida, demonstrar como chamar para Q# a partir do anfitrião.

## <a name="prerequisites"></a>Pré-requisitos

- Instale o Quantum Development Kit [para utilização com projetosQ#](xref:microsoft.quantum.install.standalone).

## <a name="creating-a-no-locq-library-and-a-net-host"></a>Criar uma biblioteca Q# e um anfitrião .NET

O primeiro passo é criar projetos para a biblioteca Q# e para o anfitrião .NET que vai chamar as operações e as funções definidas na biblioteca Q#.

Siga as instruções no separador correspondente ao seu ambiente de desenvolvimento.
Se estiver a utilizar um editor que não seja o Visual Studio ou o VS Code, basta seguir os passos da linha de comandos.

### <a name="visual-studio-code-or-command-prompt"></a>[Visual Studio Code ou linha de comandos](#tab/tabid-cmdline)

- Criar uma nova biblioteca Q#

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Criar um projeto de consola C# ou F# novo

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Adicionar a biblioteca Q# como referência a partir do programa anfitrião

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- [Opcional] Criar uma solução para ambos os projetos

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Criar uma nova biblioteca Q#
  - Aceda a **Ficheiro** -> **Novo** -> **Projeto**
  - Escreva "Q#" na caixa de pesquisa
  - Selecione **Biblioteca Q#**
  - Selecione **Seguinte**
  - Escolha um nome e uma localização para a biblioteca
  - Confirme que "place project and solution in same directory" ("pôr projeto e solução no mesmo diretório") está **desmarcado**
  - Selecione **Criar**
- Criar um programa anfitrião C# ou F# novo
  - Aceda a **File** (Ficheiro) → **New** (Novo) → **Project** (Projeto)
  - Selecione "Console App (.NET Core")" ("Aplicação de Consola (.NET Core")" para C# ou F#
  - Selecione **Seguinte**
  - Em *solution* (solução), selecione "add to solution" ("adicionar à solução")
  - Escolha um nome para o programa anfitrião
  - Selecione **Criar**

***

## <a name="calling-into-no-locq-from-net"></a>Chamar o Q# a partir de .NET

Quando os projetos estiverem configurados de acordo com as instruções acima, pode chamar o Q# a partir da aplicação de consola .NET.
O compilador Q# vai criar classes .NET para cada operação e função Q# que lhe permitem executar os seus programas quânticos num simulador.

Por exemplo, a [amostra de interoperabilidade .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) inclui o seguinte exemplo de uma operação Q#:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Para chamar esta operação a partir de .NET num simulador quântico, pode utilizar o método `Run` da classe `RunAlgorithm` .NET gerado pelo compilador Q#:

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>Passos seguintes

Agora que o Quantum Development Kit está configurado para aplicações Q# e para interoperabilidade com o .NET, pode escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).
