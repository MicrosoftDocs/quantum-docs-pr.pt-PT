---
title: Biblioteca de numéricos Quânticos da Microsoft - Instalação e Validação
description: Saiba como adicionar a biblioteca de numéricos Microsoft Quantum ao seu Visual Studio 2019 ou posterior instalação.
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 60ee91a552fad5becf8eda437406b6e0dfba0eb4
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276127"
---
# <a name="numerics-library-installation-and-validation"></a>Instalação e Validação da Biblioteca Numérica

O Kit de Desenvolvimento Quântico fornece suporte para a funcionalidade numérica através do [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) pacote NuGet.

**>do Estúdio Visual =2019:** Se estiver a utilizar o Visual Studio 2019 ou mais tarde, pode adicionar o pacote numérico utilizando o NuGet Package Manager.
Para tal, selecione "Gerir pacotes NuGet..." do item do menu "Project" no Estúdio Visual.

A partir do separador Browse, procure o nome do pacote "Microsoft.Quantum.Nummerics"

> [!NOTE]
> Certifique-se de marcar "Incluir pré-relançar"

Isto listará os pacotes disponíveis para download.
Pairar sobre "Microsoft.Quantum.Nummerics" revela uma seta virada para baixo para a direita do número da versão.
Clique na seta para instalar o pacote numérico.

Para mais detalhes, consulte o [guia uI do Gestor de Pacotes.](https://docs.microsoft.com/nuget/tools/package-manager-ui)

Em alternativa, pode utilizar a Consola Gestor de Pacotes para adicionar a biblioteca numérica ao seu projeto através da interface da linha de comando.

![Utilize a consola do gestor de pacotes a partir da linha de comando](~/media/vs2017-nuget-console-menu.png)

A partir da consola do gestor de pacotes, execute o seguinte:

```
Install-Package Microsoft.Quantum.Numerics
```

Para mais detalhes, consulte o guia da [consola do Gestor de Pacotes.](https://docs.microsoft.com/nuget/tools/package-manager-console)

**Linha de comando ou Código do Estúdio Visual:** Utilizando a linha de comando por si só ou a partir do Código do Estúdio Visual, pode utilizar o `dotnet` comando para adicionar referência ao pacote NuGet ao seu projeto:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>Verificação da sua instalação

Como o resto do Kit de Desenvolvimento Quântico, a biblioteca numérica vem com amostras que ajudam a começar o mais rápido possível.
Para testar a sua instalação utilizando estas amostras, clone o [repositório principal](https://github.com/Microsoft/Quantum) de amostras e, em seguida, execute uma das amostras.

Para executar a [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) amostra:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
