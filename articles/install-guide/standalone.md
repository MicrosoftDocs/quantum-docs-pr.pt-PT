---
title: Desenvolver com aplicações de linha de comando Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e829862521951c50cb42eebf261c803071a95275
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426425"
---
# <a name="develop-with-q-command-line-applications"></a>Desenvolver com aplicações de linha de comando Q#

Os programas Q# podem ser executados por conta própria, sem um condutor numa língua anfitriã como C#, F#, ou Python.

## <a name="pre-requisites"></a>Pré-requisitos

- [.NET Core SDK 3.1 ou posterior](https://www.microsoft.com/net/download)

## <a name="installation"></a>Instalação

Embora possa construir aplicações de linha de comando Q# em qualquer IDE, recomendamos a utilização de Código de Estúdio Visual (Código VS) ou Estúdio Visual IDE para as suas aplicações Q#. O desenvolvimento destas ferramentas proporciona acesso a funcionalidades ricas.

Para configurar o Código VS:

1. Descarregue e instale [o Código VS](https://code.visualstudio.com/download) (Windows, Linux e Mac).
2. Instale o [Microsoft QDK para o Código VS](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Para configurar o Estúdio Visual:

1. Descarregue e instale o [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 ou superior, com a carga de trabalho de desenvolvimento de plataformas cruzadas .NET Core ativada.
2. Descarregue e instale o [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).


## <a name="develop-with-q-using-vs-code"></a>Desenvolver com Q# usando o Código VS

Instale os modelos do projeto Q#:

1. Código VS aberto.
2. Clique em **ver**paleta de  ->  **comando**.
3. Selecione **Q#: Instale modelos de projeto**.

Quando os modelos do **Projeto instalados com sucesso** são apresentados, o QDK está pronto a ser utilizado com as suas próprias aplicações e bibliotecas.

Para criar um novo projeto:

1. Clique em **Ver**Paleta de  ->  **Comando** e selecione **Q#: Criar novo projeto**.
2. Clique na **aplicação**de consola autónoma .
3. Navegue até ao local para salvar o projeto e clique em **Criar Projeto**.
4. Quando o projeto for criado com sucesso, clique em **Abrir novo projeto...** na direita inferior.
        
Inspecione o projeto. Deve ver um ficheiro de origem chamado `Program.qs` , que é um programa Q# que define uma simples operação para imprimir uma mensagem para a consola.

Para executar a aplicação:
1. Clique no **terminal**  ->  **novo terminal**.
2. No aviso de terminal, entre `dotnet run` .
3. Deverá ver o seguinte texto na janela de saída `Hello quantum world!`


> [!NOTE]
> Os espaços de trabalho com várias pastas de raiz não são atualmente suportados pela extensão VS Code Q# . Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.

## <a name="develop-with-q-using-visual-studio"></a>Desenvolver com Q# usando o Estúdio Visual

Verifique a instalação do Seu Estúdio Visual criando uma `Hello World` aplicação Q#.

Para criar uma nova aplicação Q#:
1. Abra o Estúdio Visual e clique em **File**  ->  **New**  ->  **Project**.
2. Digite na caixa de `Q#` pesquisa, selecione **Q# Application** e clique **em Next**.
3. Insira um nome e localização para a sua aplicação e clique em **Criar**.


Inspecione o projeto. Deve ver um ficheiro de origem chamado `Program.qs` , que é um programa Q# que define uma simples operação para imprimir uma mensagem para a consola.

Para executar a aplicação:
1. Selecione **Debug**  ->  **Start Sem Depuração**.
2. Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.

> [!NOTE]
> Se tiver vários projetos dentro de uma solução de Estúdio Visual, todos os projetos contidos na solução têm de estar na mesma pasta que a solução, ou numa das suas subpastas.  


## <a name="next-steps"></a>Passos seguintes

Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).
