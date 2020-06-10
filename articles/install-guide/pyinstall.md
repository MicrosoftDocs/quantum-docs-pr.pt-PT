---
title: Desenvolver com Q# e Python
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1ae208e7047cb040fb44945a59c3cc6508a09723
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630292"
---
# <a name="develop-with-q-and-python"></a>Desenvolver com Q# e Python

Instale o QDK para desenvolver programas de anfitrião Python para ligar para as operações Q#.

1. Pré-requisitos

    - [Python](https://www.python.org/downloads/) 3.6 ou posterior
    - O gestor de pacotes Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Instale o `qsharp` pacote, um pacote Python que permite o interop entre Q# e Python.

    ```
    pip install qsharp
    ```

1. Instale o IQ#, um núcleo utilizado pela Jupyter e pela Python que fornece a funcionalidade principal para compilar e executar operações Q#.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Se tiver um erro durante o `dotnet iqsharp install` passo, abra uma nova janela do terminal e tente novamente.
    > Se isto ainda não funcionar, tente localizar a ferramenta instalada `dotnet-iqsharp` (no Windows, `dotnet-iqsharp.exe` ) e em execução:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > onde `/path/to/dotnet-iqsharp` deve ser substituído pelo caminho absoluto para a ferramenta no seu sistema de `dotnet-iqsharp` ficheiros.
    > Normalmente, isto será na `.dotnet/tools` pasta do perfil do utilizador.
  
1. Enquanto pode utilizar Q# com Python em qualquer IDE, recomendamos vivamente a utilização do Código de Estúdio Visual (Código VS) IDE para as suas aplicações Q# + Python. Ao utilizar o Código do Estúdio Visual e a extensão QDK Visual Studio Code, você tem acesso a funcionalidades mais ricas.

    - Instalar [código VS](https://code.visualstudio.com/download) (Windows, Linux e Mac)
    - Instale a [extensão QDK para o Código VS](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

1. Verificar a instalação ao criar uma aplicação `Hello World`

    - Crie uma operação Q# mínima ao criar um ficheiro chamado `Operation.qs` e adicionar ao mesmo o seguinte código:

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - Crie um programa Python chamado `hello_world.py` para chamar a operação Q# `SayHello()`:

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - Execute o programa:

        ```
        python hello_world.py
        ```

    - Verifique o resultado. O programa deverá produzir as seguintes linhas:

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * Você também pode usar os cadernos Python Jupyter para escrever o programa python clássico e chamar as operações Q# das células. O código Python é apenas um programa piton normal.

## <a name="next-steps"></a>Próximos passos

Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).
