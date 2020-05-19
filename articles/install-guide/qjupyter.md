---
title: Desenvolver com cadernos Q# Jupyter
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 3302a9bd0652b2dea86b844058bf8303ee7a4a7f
ms.sourcegitcommit: c85c1b439807ac576d3a11aadca307d57b059673
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/18/2020
ms.locfileid: "83551044"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Desenvolver com cadernos Q# Jupyter

Instale o QDK para desenvolver operações q# em Cadernos Q# Jupyter.

Os Cadernos Jupyter permitem a execução do código no local juntamente com instruções, notas e outros conteúdos. Este ambiente é ideal para escrever código Q# com explicações incorporadas ou tutoriais interativos de computação quântica. Eis o que tem de fazer para começar a criar os seus próprios blocos de notas em Q#.

IQ# (pronunciado i-q-sharp) é uma extensão principalmente utilizada pelo Jupyter e Python para o SDK de .NET Core que fornece a funcionalidade principal que permite compilar e simular operações Q#.

> [!NOTE]
> * Em Q# Jupyter Notebooks só pode executar código Q# e as operações não podem ser chamadas a partir de programas de acolhimento externos (por exemplo, ficheiros Python ou C#). Este ambiente não é apropriado se o seu objetivo é combinar um programa de anfitriões clássico seleto externo com o programa quântico.

1. Pré-requisitos

    - [Python](https://www.python.org/downloads/) 3.6 ou posterior
    - [Caderno jupyter](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Instalar o pacote `iqsharp`

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Verificar a instalação ao criar uma aplicação `Hello World`

    - Execute o comando seguinte para iniciar o servidor de blocos de notas:

        ```bash
        jupyter notebook
        ```

    - Para abrir a cópia do portátil jupyter e colar o URL fornecido pela linha de comando no seu navegador.

    - Crie um Jupyter Notebook com um kernel Q# e adicione o seguinte código à primeira célula do bloco de notas:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Execute esta célula do bloco de notas:

        ![Célula do Jupyter Notebook com código Q#](~/media/install-guide-jupyter.png)

        Deverá ver `SayHello` na saída da célula. Ao executar em Jupyter Notebooks, o código Q# é compilado e o bloco de notas produz o nome das operações que encontra.


    - Numa nova célula, execute a operação que acabou de criar (num simulador) utilizando o `%simulate` comando:

        ![Célula do Jupyter Notebook com o magic %simulate](~/media/install-guide-jupyter-simulate.png)

        Deve ver a mensagem impressa no ecrã juntamente com o resultado da operação que invocou (aqui, vemos a tuple vazia porque a `()` nossa operação simplesmente devolve um `Unit` tipo).

## <a name="next-steps"></a>Passos seguintes

Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).
