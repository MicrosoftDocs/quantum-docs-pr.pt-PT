---
title: Execute programas Q# sem condutor e uma língua anfitriã
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706806"
---
# <a name="q-command-line-applications"></a>Q# Aplicações da Linha de Comando

Os programas Q# podem ser executados por conta própria, sem um condutor numa língua anfitriã como C#, F#, ou Python.

## <a name="pre-requisites"></a>Pré-requisitos

- [.NET Core SDK 3.1 ou posterior](https://www.microsoft.com/net/download)

## <a name="installation"></a>Instalação

Embora possa construir aplicações de linha de comando Q# em qualquer IDE, recomendamos vivamente a utilização de Código de Estúdio Visual (Código VS) ou Estúdio Visual IDE para as suas aplicações Q#. Ao utilizar o VS Code ou o Visual Studio e a extensão qDK Visual Studio Code, você tem acesso a funcionalidades mais ricas.

- Instalar [código VS](https://code.visualstudio.com/download) (Windows, Linux e Mac)
- Instale a [extensão QDK para o Código VS](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) OU
- [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, com a carga de trabalho de desenvolvimento para várias plataformas .NET Core ativada
- Descarregue e instale a [extensão do Estúdio Visual](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)


## <a name="develop-with-q-using-vs-code"></a>Desenvolver com Q# usando o Código VS

Instalar os modelos de projeto Quantum:

- Ir **ver** -> **paleta** de comando
- Selecione **Q#: Instale modelos de projeto**

Agora, tem o Quantum Development Kit instalado e pronto para utilizar nas aplicações e bibliotecas.
- Crie um novo projeto:
  - Ir **ver** -> **paleta** de comando
  - Selecione **Q#: Criar novo projeto**
  - Selecione **aplicação** de consola autónoma
  - Navegue para a localização no sistema de ficheiros onde quer criar a aplicação
  - Clique no botão **Abrir novo projeto...**, após o projeto ser criado.
        
- Inspecione o projeto
  - Deve ver que um `Program.qs` ficheiro chamado criado, que é um programa Q# que define uma simples operação para imprimir uma mensagem para a consola.

- Execute a aplicação:
  - Ir para **terminal** -> **novo terminal novo**
  - Entrar`dotnet run`
  - Deverá ver o seguinte texto na janela de saída `Hello quantum world!`


> [!NOTE]
> * As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão do Visual Studio Code. Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.

## <a name="develop-with-q-using-visual-studio"></a>Desenvolver com Q# usando o Estúdio Visual

Verificar a instalação ao criar uma aplicação `Hello World`

- Crie uma nova aplicação Q#
  - Ir para **Arquivar** -> **Novo** -> **Projeto**
  - Escreva `Q#` na caixa de pesquisa
  - Selecione **Aplicação Q#**
  - Selecione **Next**
  - Escolha um nome e uma localização para a aplicação
  - Selecione **Criar**

- Inspecione o projeto
  - Deve ver que foi `Program.qs` criado um ficheiro chamado, que é um programa Q# que define uma simples operação para imprimir uma mensagem para a consola.

- Executar a aplicação
  - Selecione **Debug** -> **Start Without Debugging**
  - Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.

> [!NOTE]
> * Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das suas subpastas.  


## <a name="whats-next"></a>Passos seguintes?

Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.write-program).
