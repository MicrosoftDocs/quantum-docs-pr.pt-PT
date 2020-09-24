---
title: Configurar o Microsoft Quantum Development Kit (QDK)
description: Saiba como configurar o Microsoft Quantum Development Kit para diferentes ambientes.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834487"
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

|&nbsp; | **VS Code<br>(2019 ou posterior)**| **Visual Studio<br>(2019 ou posterior)** | **Jupyter Notebooks** | **Linha de comandos**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|**SO** |Windows, macOS, Linux |Apenas no Windows |Windows, macOS, Linux |Windows, macOS, Linux |
|<br>**Q# autónomo** |<br>[Instalar](xref:microsoft.quantum.install.standalone) |<br> [Instalar](xref:microsoft.quantum.install.standalone)  |<br> [Instalar](xref:microsoft.quantum.install.jupyter) |<br>[Instalar](xref:microsoft.quantum.install.standalone)|
|**Q#  e Python** |[Instalar](xref:microsoft.quantum.install.python) |[Instalar](xref:microsoft.quantum.install.python) |[Instalar](xref:microsoft.quantum.install.jupyter) |[Instalar](xref:microsoft.quantum.install.python) |
|**Q# e .NET (C#, F#)**|[Instalar](xref:microsoft.quantum.install.cs) |[Instalar](xref:microsoft.quantum.install.cs)|&#10006; |[Instalar](xref:microsoft.quantum.install.cs) |

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
