---
title: Desenvolver com Q# e Python
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 35499daae0cd0ae329e39b43b0d8dd5a00183871
ms.sourcegitcommit: 328f45a0b64cb6b325fa9d3b3ddb74a6a7a97ee9
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83660723"
---
# <a name="develop-with-q-and-python"></a>Desenvolver com Q# e Python

Instale o QDK para desenvolver programas de anfitriões Python para ligar para as operações Q#.

1. Pré-requisitos

    - [Python](https://www.python.org/downloads/) 3.6 ou posterior
    - O gestor de pacotes Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Instale o `qsharp` pacote, um pacote Python que permite o interop entre Q# e Python.

    ```bash
    pip install qsharp
    ```

1. Instale o IQ#, um núcleo utilizado pela Jupyter e python que fornece a funcionalidade central para a compilação e execução de operações Q#.

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. Embora possa utilizar Q# com Python em qualquer IDE, recomendamos vivamente a utilização do Código do Estúdio Visual (Código VS) IDE para as suas aplicações Q# + Python. Ao utilizar o Visual Studio Code e a extensão qDK Visual Studio Code, você tem acesso a uma funcionalidade mais rica.

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

        ```bash
        python hello_world.py
        ```

    - Verifique o resultado. O programa deverá produzir as seguintes linhas:

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * Você também pode usar os cadernos Python Jupyter para escrever o programa clássico Python e chamar operações Q# a partir das células. O código Python é apenas um programa python normal.

## <a name="next-steps"></a>Passos seguintes

Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).
