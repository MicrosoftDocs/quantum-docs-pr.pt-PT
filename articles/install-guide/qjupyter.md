---
title: Desenvolver com cadernos Q# Jupyter
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b7276f9b273f601f30e4938018398353b6a9102d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831074"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Desenvolver com cadernos Q# Jupyter

Instale o QDK para desenvolver operações q# em Cadernos Q# Jupyter.

Os Cadernos Jupyter permitem a execução do código no local juntamente com instruções, notas e outros conteúdos. Este ambiente é ideal para escrever código Q# com explicações incorporadas ou tutoriais interativos de computação quântica. Eis o que tem de fazer para começar a criar os seus próprios blocos de notas em Q#.

IQ# (pronunciado i-q-sharp) é uma extensão principalmente utilizada pelo Jupyter e Python para o SDK de .NET Core que fornece a funcionalidade principal que permite compilar e simular operações Q#.

> [!NOTE]
> * Em Q# Jupyter Notebooks só pode executar o código Q# e as operações não C# podem ser chamadas de programas de acolhimento externos (por exemplo, Python ou ficheiros). Este ambiente não é apropriado se o seu objetivo é combinar um programa de anfitriões clássico seleto externo com o programa quântico.

1. Pré-requisitos

    - [Python](https://www.python.org/downloads/) 3.6 ou posterior
    - [Bloco de Notas do Jupyter](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1 ou posterior](https://www.microsoft.com/net/download)

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


    - Numa nova célula, execute a operação que acabou de criar (num simulador) utilizando o comando `%simulate`:

        ![Célula do Jupyter Notebook com o magic %simulate](~/media/install-guide-jupyter-simulate.png)

        Deve ver a mensagem impressa no ecrã juntamente com o resultado da operação que invocou (aqui, vemos a `()` vazia porque a nossa operação simplesmente devolve um tipo `Unit`).

## <a name="whats-next"></a>O que se segue?

Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.write-program).
