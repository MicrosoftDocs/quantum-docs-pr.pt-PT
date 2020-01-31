---
title: Desenvolver com Q# + Python
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1e40c2dddeaf4fad41693c976493f10fffffa139
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831006"
---
# <a name="develop-with-q--python"></a>Desenvolver com Q# + Python

Instale o QDK para desenvolver programas de anfitriões Python para ligar para as operações Q#.

1. Pré-requisitos

    - [Python](https://www.python.org/downloads/) 3.6 ou posterior
    - O gestor de pacotes Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [.NET Core SDK 3.1 ou posterior](https://www.microsoft.com/net/download)


1. Instale o pacote `qsharp`, um pacote Python que permite o interop entre Q# e Python.

    ```bash
    pip install qsharp
    ```

1. Instale `iqsharp`, um núcleo utilizado pela Jupyter e python que fornece a funcionalidade principal para a compilação e execução de operações Q#.

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

## <a name="whats-next"></a>O que se segue?

Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.write-program).
