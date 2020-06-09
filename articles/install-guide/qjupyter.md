---
title: Programar com Q# Jupyter Notebooks
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 9117794d6cf6f05fa34e05c21fad8977d0e76505
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84577825"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Programar com Q# Jupyter Notebooks

Instale o QDK para desenvolver operações Q# em Cadernos Q# Jupyter.

Os Cadernos Jupyter permitem a execução do código no local juntamente com instruções, notas e outros conteúdos. Este ambiente é ideal para escrever código Q# com explicações incorporadas ou tutoriais interativos de computação quântica. Eis o que tem de fazer para começar a criar os seus próprios blocos de notas em Q#.

IQ# (pronunciado i-q-sharp) é uma extensão principalmente utilizada pelo Jupyter e Python para o SDK de .NET Core que fornece a funcionalidade principal que permite compilar e simular operações Q#.

> [!NOTE]
> * Em Q# Jupyter Notebooks só é possível executar o código Q# e as operações não podem ser chamadas a partir de programas de anfitriões externos (por exemplo, ficheiros Python ou C#). Este ambiente não é apropriado se o seu objetivo é combinar um programa de anfitrião clássico externo com o programa quântico.

1. Pré-requisitos

    - [Python](https://www.python.org/downloads/) 3.6 ou posterior
    - [Caderno Jupyter](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Instalar o pacote `iqsharp`

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Verificar a instalação ao criar uma aplicação `Hello World`

    - Execute o comando seguinte para iniciar o servidor de blocos de notas:

        ```
        jupyter notebook
        ```

    - Para abrir o Bloco de Notas Jupyter, copie e cole o URL fornecido pela linha de comando no seu navegador.

    - Crie um Caderno Jupyter com um kernel Q# e adicione o seguinte código à primeira célula do portátil:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Execute esta célula do bloco de notas:

        ![Célula de caderno Jupyter com código Q#](~/media/install-guide-jupyter.png)

        Deverá ver `SayHello` na saída da célula. Ao correr no Jupyter Notebook, o código Q# é compilado e o portátil produz o nome da(s) operação(s) que encontra.


    - Numa nova célula, execute a operação que acabou de criar (num simulador) utilizando o `%simulate` comando:

        ![Célula de Caderno Jupyter com %simular magia](~/media/install-guide-jupyter-simulate.png)

        Deve ver a mensagem impressa no ecrã juntamente com o resultado da operação que invocou (aqui, vemos o tuple vazio porque a `()` nossa operação simplesmente devolve um `Unit` tipo).

## <a name="next-steps"></a>Próximos passos

Agora que instalou o QDK para Q# Jupyter Notebooks, pode escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng) escrevendo o seu código Q# diretamente dentro do ambiente do Caderno Jupyter.

Para mais exemplos do que pode fazer com os Cadernos Q# Jupyter, por favor dê uma olhada:
- [Introdução a Q# e Caderno Jupyter](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Lá você encontrará um Q# Jupyter Notebook que mostra como usar Q# neste ambiente.
- [Quantum Katas](xref:microsoft.quantum.overview.katas), uma coleção aberta de tutoriais auto-pacatos e conjuntos de exercícios de programação sob a forma de Q# Jupyter Notebooks. Os [cadernos tutoriais Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) são um bom ponto de partida. As Katas Quânticas destinam-se a ensinar-lhe elementos de computação quântica e programação Q# ao mesmo tempo. São um excelente exemplo do tipo de conteúdo que se pode criar com os Cadernos Q# Jupyter.
