---
title: Biblioteca de numéricos Quânticos da Microsoft - Instalação e Validação
description: Saiba como adicionar a biblioteca de numéricos Da Microsoft Quantum ao seu Visual Studio 2019 ou posterior instalação.
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: cb0d00a509b3986b605dd7f15f9bccc0661bb894
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906343"
---
# <a name="numerics-library-installation-and-validation"></a>Instalação e Validação da Biblioteca Numérica

O Kit de Desenvolvimento Quântico fornece suporte para a funcionalidade numérica através do pacote [NuGet`Microsoft.Quantum.Numerics`.](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)

**Estúdio Visual >=2019:** Se estiver a utilizar o Visual Studio 2019 ou mais tarde, pode adicionar o pacote numérico utilizando o NuGet Package Manager.
Para isso, selecione "Gerir pacotes NuGet..." do item do menu "Project" no Estúdio Visual.

A partir do separador Browse, procure o nome de pacote "Microsoft.Quantum.Numerics"

> [!NOTE]
> Certifique-se de marcar "Incluir pré-lançamento"

Isto listará os pacotes disponíveis para download.
Pairando sobre "Microsoft.Quantum.Numerics" revela uma seta virada para baixo para a direita do número da versão.
Clique na seta para instalar o pacote numérico.

Para mais detalhes, consulte o [guia UI do Gestor](https://docs.microsoft.com/nuget/tools/package-manager-ui)de Pacotes.

Em alternativa, pode utilizar a Consola gestora de pacotes para adicionar a biblioteca numérica ao seu projeto através da interface da linha de comando.

![Utilize a consola gestora de pacotes a partir da linha de comando](../../media/vs2017-nuget-console-menu.png)

A partir da consola gestora de pacotes, execute o seguinte:

```
Install-Package Microsoft.Quantum.Numerics
```

Para mais detalhes, consulte o guia de [consolas do Gestor](https://docs.microsoft.com/nuget/tools/package-manager-console)de Pacotes .

**Linha de comando ou Código** de Estúdio Visual: Utilizando a linha de comando por si só ou dentro do Código visual do Estúdio, pode utilizar o comando `dotnet` para adicionar referência ao pacote NuGet ao seu projeto:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>Verificar a sua instalação

Como o resto do Kit de Desenvolvimento Quântico, a biblioteca numérica vem com amostras que o ajudam a começar o mais rápido possível.
Para testar a sua instalação utilizando estas amostras, clone o [repositório de amostras principais](https://github.com/Microsoft/Quantum) e, em seguida, executar uma das amostras.

Para executar a amostra [`CustomModAdd`:](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd)

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
