---
title: Programar com Q# + C#
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 5bcb036b0b32e64d43f90e9a068d9dcc237890ba
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680169"
---
# <a name="using-q-with-c-and-f"></a>Usando Q#\# com C e F\#

Q# é construído para jogar bem com .NET línguas como C# e F#.
Neste guia, vamos demonstrar como usar o Q# com um programa de anfitriões escrito numa linguagem .NET.

## <a name="prerequisites"></a>Pré-requisitos

- Instale o Kit de Desenvolvimento Quântico [para utilização com projetos de linha de comando Q#](xref:microsoft.quantum.install.standalone).

## <a name="creating-a-q-library-and-a-net-host"></a>Criar uma biblioteca Q# e um hospedeiro .NET

O primeiro passo é criar projetos para a sua biblioteca Q# e para o anfitrião .NET que irá chamar para as operações e funções definidas na sua biblioteca Q#.

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Criar uma nova biblioteca Q#
  - Ir para **Arquivar** -> **Novo** -> **Projeto**
  - Digite "Q#" na caixa de pesquisa
  - Selecione **Biblioteca Q#**
  - Selecione **Next**
  - Escolha um nome e localização para a sua biblioteca
  - Certifique-se de que "colocar projeto e solução no mesmo diretório" não é **verificado**
  - Selecione **Criar**
- Crie um novo programa de anfitriões C# ou F#
  - Ir a **Arquivo** → **Novo** **Projeto** →
  - Selecione "Console App (.NET Core")" para C# ou F #
  - Selecione **Next**
  - Sob *solução*, selecione "adicionar à solução"
  - Escolha um nome para o seu programa de anfitriões
  - Selecione **Criar**

### <a name="visual-studio-code-or-command-line"></a>[Código de estúdio visual ou linha de comando](#tab/tabid-cmdline)

- Criar uma nova biblioteca Q#

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Criar um novo projeto de consola C# ou F#

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Adicione a sua biblioteca Q# como referência do seu programa de anfitriões

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

***

## <a name="calling-into-q-from-net"></a>Chamando para Q# de .NET

Assim que tiver os seus projetos configurados seguindo as instruções acima, pode ligar para Q# a partir da sua aplicação de consola .NET.
O compilador Q# criará classes .NET para cada operação e função Q# que lhe permitem executar os seus programas quânticos num simulador.

Por exemplo, a [amostra de interoperabilidade .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) inclui o seguinte exemplo de uma operação Q#:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Para chamar esta operação de .NET num simulador `Run` quântico, `RunAlgorithm` pode utilizar o método da classe .NET gerado pelo compilador Q#:

### <a name="c"></a>[C #](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a>Passos seguintes?

Agora que tem o Quantum Development Kit configurado para ambos os programas de linha de comando Q# e para interoperabilidade com .NET, pode escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.write-program).
