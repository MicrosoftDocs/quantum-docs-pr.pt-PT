---
title: Usando bibliotecas Q# adicionais
description: Saiba como adicionar bibliotecas Q# adicionais às suas aplicações quânticas.
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
ms.openlocfilehash: b82113b925870d07c8a28aecd50176e009826062
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86872639"
---
# <a name="using-additional-q-libraries"></a>Utilização de bibliotecas Q# adicionais

O Kit de Desenvolvimento Quântico fornece uma funcionalidade adicional específica do domínio através de _pacotes NuGet_ que podem ser adicionados aos seus projetos Q#.

| Biblioteca Q#  | Pacote NuGet | Notas |
|---------|---------|--------|
| [Biblioteca padrão Q#](xref:microsoft.quantum.libraries.standard.intro) | [**Microsoft.Quantum.Standard**](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | Incluído por padrão |
| [Biblioteca de química quântica](xref:microsoft.quantum.chemistry.concepts.intro) | [**Microsoft.Quantum.Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [Biblioteca numérica quântica](xref:microsoft.quantum.numerics.intro) | [**Microsoft.Quantum.Nummerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [Biblioteca de machine learning quântica](xref:microsoft.quantum.libraries.machine-learning.intro) | [**Microsoft.Quantum.MachineLearning**](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

Uma vez instalado o Kit de Desenvolvimento Quântico para utilização com o seu ambiente preferido e linguagem de anfitrião, pode facilmente adicionar bibliotecas a projetos Q# individuais sem qualquer instalação adicional.

> [!NOTE]
> Algumas bibliotecas Q# podem funcionar bem com ferramentas adicionais que funcionam ao lado dos seus programas Q# ou que se integram com as suas aplicações de anfitrião.
> Por exemplo, as [instruções de instalação](xref:microsoft.quantum.chemistry.concepts.installation) da biblioteca de química descrevem como usar o pacote [ **Microsoft.Quantum.Chemistry** ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) juntamente com a plataforma de química computacional NWChem e como instalar as `qdk-chem` ferramentas da linha de comando para trabalhar com dados de química quântica.

## <a name="q-command-line-applications-or-net-interopability"></a>[Q# aplicações de linha de comando ou .NET interopability](#tab/tabid-csproj)

**Linha de comando ou Código do Estúdio Visual:** Utilizando a linha de comando por si só ou a partir do Código do Estúdio Visual, pode utilizar o `dotnet` comando para adicionar uma referência de pacote NuGet ao seu projeto.
Por exemplo, para adicionar o pacote [**Microsoft.Quantum.Nummerics,**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) executar o seguinte comando:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

**Estúdio Visual:** Se estiver a utilizar o Visual Studio 2019 ou mais tarde, pode adicionar pacotes Q# adicionais utilizando o NuGet Package Manager.
Para carregar um pacote: 
1. Com um projeto aberto no Visual Studio, **selecione Manage NuGet Packages...** a partir do menu **Projeto.**

2. Clique **em Procurar,** **selecione Inclua pré-relançar** e procure o nome do pacote "Microsoft.Quantum.Nummerics". Isto listará os pacotes disponíveis para download.

3. Passe por cima **da Microsoft.Quantum.Nummerics** e clique na seta de ponta para baixo à direita do número da versão para instalar o pacote numérico.

Para mais detalhes, consulte o [guia uI do Gestor de Pacotes.](https://docs.microsoft.com/nuget/tools/package-manager-ui)

Em alternativa, pode utilizar a Consola Gestor de Pacotes para adicionar a biblioteca numérica ao seu projeto através da interface da linha de comando.

![Utilize a consola do gestor de pacotes a partir da linha de comando](~/media/vs2017-nuget-console-menu.png)

A partir da consola gestor de pacotes, execute o seguinte:

```
Install-Package Microsoft.Quantum.Numerics
```

Para mais detalhes, consulte o guia da [consola do Gestor de Pacotes.](https://docs.microsoft.com/nuget/tools/package-manager-console)

## <a name="iq-notebooks"></a>[IQ# Cadernos](#tab/tabid-notebook)

Pode disponibilizar pacotes adicionais para utilização num Bloco de Notas IQ# utilizando o [ `%package` comando mágico](xref:microsoft.quantum.iqsharp.magic-ref.package).
Por exemplo, para adicionar o pacote [**Microsoft.Quantum.Nummerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) para utilização num bloco de notas IQ#, executar o seguinte comando numa célula de portátil:

```
%package Microsoft.Quantum.Numerics
```

Seguindo este comando, o pacote está disponível para quaisquer células dentro do caderno.
Para disponibilizar o pacote a partir do código Q# no espaço de trabalho atual, recarregue o espaço de trabalho após a adição do seu pacote:

```
%workspace reload
```

## <a name="python-interoperability"></a>[Interoperabilidade da python](#tab/tabid-python)


Você pode disponibilizar pacotes adicionais para uso em um programa de anfitrião Python usando o [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) método.
Por exemplo, para adicionar o pacote [**Microsoft.Quantum.Nummerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) para utilização num bloco de notas IQ#, execute o seguinte código Python:

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

Seguindo este comando, o pacote será disponibilizado a qualquer código Q# compilado utilizando `qsharp.compile` .
Para disponibilizar o pacote a partir do código Q# no espaço de trabalho atual, recarregue o espaço de trabalho após a adição do seu pacote:

```python
qsharp.reload()
```

***
