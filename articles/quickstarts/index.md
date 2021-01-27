---
title: Configurar o Microsoft Quantum Development Kit (QDK)
description: Saiba como configurar o Microsoft Quantum Development Kit para diferentes ambientes.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: quickstart
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 15067f1762f4468345beee38c98e1b943081fc1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859032"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a>Configurar o Microsoft Quantum Development Kit (QDK)

Saiba como configurar o Microsoft Quantum Development Kit (QDK) para o seu ambiente, para que possa começar a utilizar a programação quântica. O QDK consiste em:

- Linguagem de programação Q#
- Um conjunto de bibliotecas para abstração da funcionalidade complexa em Q#
- APIs para as linguagens Python e .NET (C#, F# e VB.NET) para executar programas quânticos escritos em Q#
- Ferramentas para facilitar a programação

Os programas Q# podem ser executados como aplicações autónomas com o Visual Studio Code ou o Visual Studio, através do Jupyter Notebook com o kernel IQ# Jupyter ou emparelhado com um programa anfitrião escrito em Python ou numa linguagem .NET (C#, F#). Também pode executar programas Q# online com o [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) ou [Docker](#use-the-qdk-with-docker). 

## <a name="options-for-setting-up-the-qdk"></a>Opções de configuração do QDK

Pode utilizar o QDK de três maneiras:

- [Instalar o QDK localmente](#install-the-qdk-locally)
- [Utilizar o QDK online](#use-the-qdk-online)
- [Utilizar uma imagem do Docker para o QDK](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a>Instalar o QDK localmente

Pode desenvolver código Q# na maior parte dos seus IDEs favoritos, tal como pode integrar o Q# noutras linguagens, como Python e .NET (C#, F#).

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><b>Código VS<br>(2019 ou posterior)</b></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><b>Visual Studio<br>(2019 ou posterior)</b></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><b>Jupyter Notebooks</b></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><b>Linha de comandos</b></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><b>Suporte de SO:</b></td>
        <td align="center">Windows, macOS, Linux</td>
        <td align="center">Apenas no Windows</td>
        <td align="center">Windows, macOS, Linux</td>
        <td align="center">Windows, macOS, Linux</td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><b>Q# autónomo</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Instalar</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Instalar</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.jupyter">Instalar</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Instalar</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><b>Q# e Python</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Instalar</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Instalar</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Instalar</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Instalar</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><b>Q# e .NET (C#, F#)</b></td> 
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Instalar</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Instalar</a></td>
        <td align="center">&#10006;</td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Instalar</a></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a>Utilizar o QDK Online

Também pode desenvolver código Q# sem instalar nada localmente com estas opções:

|Recurso|Vantagens|Limitações|
|---|---|---|
|[**Visual Studio Codespaces**](xref:microsoft.quantum.install.standalone)|Um ambiente de desenvolvimento online avançado  |Requer um plano e subscrição do Azure |
|[**Binder**](xref:microsoft.quantum.install.binder) | Experiência de bloco de notas online gratuita |Sem persistência |

## <a name="use-the-qdk-with-docker"></a>Utilizar o QDK com o Docker

Pode utilizar a nossa imagem do Docker para o QDK na sua instalação local do Docker ou na cloud através de qualquer serviço que suporte imagens do Docker, como o ACI.

Pode transferir a imagem do Docker IQ# a partir de https://github.com/microsoft/iqsharp/#using-iq-as-a-container. 

Também pode utilizar o Docker com um Contentor de Desenvolvimento Remoto do Visual Studio Code para definir rapidamente ambientes de desenvolvimento. Para obter mais informações sobre Contentores de Desenvolvimento do VS Code, veja https://github.com/microsoft/Quantum/tree/master/.devcontainer.

## <a name="next-steps"></a>Passos seguintes

Os fluxos de trabalho de cada uma destas configurações são descritos e comparados em [Formas de executar um programa Q#](xref:microsoft.quantum.guide.host-programs).
