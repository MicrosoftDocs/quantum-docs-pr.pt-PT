---
title: Instalar o Microsoft Quantum Development Kit (QDK)
description: Como instalar o Microsoft Quantum Development Kit para diferentes ambientes.
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 378970dc911ea5a794590f8336ffc6d3f9673285
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867578"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Instalar o Microsoft Quantum Development Kit (QDK)

Saiba como instalar o Microsoft Quantum Development Kit (QDK), para que possa começar a utilizar a programação quântica. O QDK consiste em:

- Linguagem de programação Q#
- Um conjunto de bibliotecas para abstração da funcionalidade complexa em Q#
- APIs para as linguagens Python e .NET (C#, F# e VB.NET) para executar programas quânticos escritos em Q#
- Ferramentas para facilitar a programação

Os programas Q# podem ser executados como aplicações autónomas com o Visual Studio Code ou através de Blocos de Notas do Jupyter com o kernel IQ# Jupyter.
Também podem ser emparelhados com um programa anfitrião escrito numa linguagem .NET (tipicamente C# ) ou Python, o que permite chamar operações quânticas de dentro de um programa clássico.

Os fluxos de trabalho de cada uma destas configurações são descritos e comparados em [Formas de executar um programa Q#](xref:microsoft.quantum.guide.host-programs).

Para prosseguir com a instalação do QDK e criar projetos Q#, selecione a sua configuração preferida:

[Desenvolver com aplicações de linha de comandos do Q#](xref:microsoft.quantum.install.standalone) - Escolha esta abordagem para trabalhar com o Q# a partir da linha de comandos. Não requer um controlador ou um programa anfitrião como acontece com as opções abaixo.

[Desenvolver com o Jupyter Notebook em Q#](xref:microsoft.quantum.install.jupyter) - Selecione este ambiente para executar código Q# em células que tenham texto incorporado ou para criar tutoriais interativos de computação quântica. 

[Desenvolver com Q# e Python](xref:microsoft.quantum.install.python) - Permite-lhe combinar o Python e o Q# para criar um programa anfitrião em Python que chame operações do Q#.

[Desenvolver com Q# e .NET](xref:microsoft.quantum.install.cs) - Combine C#, F# ou VB.NET com o Q# para criar um programa anfitrião em .NET que chame operações do Q#.
