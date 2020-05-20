---
title: Programar com Q# Jupyter Notebooks
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 0c4dc856c94b0a694fb99607eda64cec4d5c221d
ms.sourcegitcommit: 328f45a0b64cb6b325fa9d3b3ddb74a6a7a97ee9
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83660766"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Programar com Q# Jupyter Notebooks

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

    - Para abrir o Caderno Jupyter, copie e cole o URL fornecido pela linha de comando no seu navegador.

    - Crie um Caderno Jupyter com um núcleo Q# e adicione o seguinte código à primeira célula de caderno:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Execute esta célula do bloco de notas:

        ![Célula de caderno jupyter com código Q#](~/media/install-guide-jupyter.png)

        Deverá ver `SayHello` na saída da célula. Ao ser recorrido no Caderno Jupyter, o código Q# é compilado e o caderno produz o nome da operação(s) que encontra.


    - Numa nova célula, execute a operação que acabou de criar (num simulador) utilizando o `%simulate` comando:

        ![Célula de caderno jupyter com %simulamagia](~/media/install-guide-jupyter-simulate.png)

        Deve ver a mensagem impressa no ecrã juntamente com o resultado da operação que invocou (aqui, vemos a tuple vazia porque a `()` nossa operação simplesmente devolve um `Unit` tipo).

## <a name="next-steps"></a>Passos seguintes

Agora que instalou o QDK para Os Cadernos Q# Jupyter, pode escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng) escrevendo o seu código Q# diretamente dentro do ambiente jupyter Notebook.

Para mais exemplos do que pode fazer com os Cadernos Q# Jupyter, por favor dê uma olhada em:
- [Introdução a Q# e Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Lá você encontrará um Caderno Q# Jupyter que mostra como usar Q# neste ambiente.
- [Quantum Katas](xref:microsoft.quantum.overview.katas), uma coleção de tutoriais auto-pacatos e conjuntos de exercícios de programação sob a forma de Cadernos Q# Jupyter. Os [cadernos tutoriais Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) são um bom ponto de partida. Os Quantum Katas destinam-se a ensinar-lhe elementos de computação quântica e programação Q# ao mesmo tempo. São um excelente exemplo do tipo de conteúdo que se pode criar com os Cadernos Q# Jupyter.
