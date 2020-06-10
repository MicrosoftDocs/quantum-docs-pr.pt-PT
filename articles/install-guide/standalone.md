---
title: Desenvolver com aplicações de linha de comando Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630267"
---
# <a name="develop-with-q-command-line-applications"></a>Desenvolver com aplicações de linha de comando Q#

Os programas Q# podem ser executados por si mesmos, sem um condutor numa língua hospedeira como C#, F#ou Python.

## <a name="prerequisites"></a>Pré-requisitos

- [.NET Core SDK 3.1 ou mais tarde](https://www.microsoft.com/net/download)

## <a name="installation"></a>Instalação

Enquanto pode construir aplicações de linha de comando Q# em qualquer IDE, recomendamos a utilização do Código de Estúdio Visual (CÓDIGO VS) ou do Visual Studio IDE para as suas aplicações Q#. O desenvolvimento nestas ferramentas proporciona acesso a uma funcionalidade rica.

Para configurar o Código VS:

1. Descarregue e instale [o Código VS](https://code.visualstudio.com/download) (Windows, Linux e Mac).
2. Instale o [Microsoft QDK para o Código VS](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Para configurar o Estúdio Visual:

1. Descarregue e instale [o Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 ou superior, com a carga de trabalho de desenvolvimento de plataformas cruzadas .NET Core ativada.
2. Faça o download e instale o [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).


## <a name="develop-with-q-using-vs-code"></a>Desenvolver com Q# usando o Código VS

Instale os modelos de projeto Q#:

1. Abrir código VS.
2. Clique **na**  ->  **paleta de comando ver.**
3. Selecione **Q#: Instale modelos de projetos**.

Quando **os modelos do Projeto instalados com sucesso** forem apresentados com sucesso, o QDK está pronto a ser utilizado com as suas próprias aplicações e bibliotecas.

Para criar um novo projeto:

1. Clique **em Ver Paleta**de  ->  **Comando** e selecione **Q#: Criar novo projeto**.
2. Clique **na aplicação de consola autónoma**.
3. Navegue até ao local para salvar o projeto e clique em **Criar Projeto.**
4. Quando o projeto for criado com sucesso, clique em **Abrir novo projeto...** no direito inferior.
        
Inspecionar o projeto. Deve ver um ficheiro de origem chamado `Program.qs` , que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.

Para executar a aplicação:
1. Clique **em Terminal**Novo  ->  **Terminal**.
2. Na solicitação do terminal, `dotnet run` entre.
3. Deverá ver o seguinte texto na janela de saída `Hello quantum world!`


> [!NOTE]
> Os espaços de trabalho com várias pastas de raiz não são atualmente suportados pela extensão VS Code Q#. Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.

## <a name="develop-with-q-using-visual-studio"></a>Desenvolver com Q# usando Visual Studio

Verifique a instalação do Visual Studio criando uma `Hello World` aplicação Q#.

Para criar uma nova aplicação Q#:
1. Abra o Estúdio Visual e clique em **File**  ->  **New**  ->  **Project**.
2. Digite `Q#` a caixa de pesquisa, selecione **Q# Aplicação** e clique em **Seguinte**.
3. Introduza um nome e localização para a sua aplicação e clique em **Criar**.


Inspecionar o projeto. Deve ver um ficheiro de origem chamado `Program.qs` , que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.

Para executar a aplicação:
1. Selecione **Debug**  ->  **Start Without Debugging**.
2. Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.

> [!NOTE]
> Se tiver vários projetos dentro de uma solução Visual Studio, todos os projetos contidos na solução precisam estar na mesma pasta que a solução, ou numa das suas sub-pastas.  


## <a name="next-steps"></a>Próximos passos

Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).
