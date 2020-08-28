---
title: Utilização de bibliotecas adicionais Q#
description: Saiba como adicionar bibliotecas adicionais Q# às suas aplicações quânticas.
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: 39bf7dc52f4670a6e4536efc437d001c96f9584a
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992144"
---
# <a name="using-additional-no-locq-libraries"></a>Utilização de Q# bibliotecas adicionais

O Kit de Desenvolvimento Quântico fornece uma funcionalidade adicional específica do domínio através de _pacotes NuGet_ que podem ser adicionados aos seus Q# projetos.

| Q# Biblioteca  | Pacote NuGet | Notas |
|---------|---------|--------|
| [Q# biblioteca padrão](xref:microsoft.quantum.libraries.standard.intro) | [**Microsoft.Quantum.Standard**](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | Incluído por padrão |
| [Biblioteca de química quântica](xref:microsoft.quantum.chemistry.concepts.intro) | [**Microsoft.Quantum.Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [Biblioteca numérica quântica](xref:microsoft.quantum.numerics.intro) | [**Microsoft.Quantum.Nummerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [Biblioteca de machine learning quântica](xref:microsoft.quantum.libraries.machine-learning.intro) | [**Microsoft.Quantum.MachineLearning**](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

Uma vez instalado o Kit de Desenvolvimento Quântico para utilização com o seu ambiente preferido e linguagem de acolhimento, pode facilmente adicionar bibliotecas a projetos individuais Q# sem qualquer instalação adicional.

> [!NOTE]
> Algumas Q# bibliotecas podem funcionar bem com ferramentas adicionais que funcionam ao lado dos seus Q# programas, ou que se integram com as suas aplicações de anfitrião.
> Por exemplo, as [instruções de instalação](xref:microsoft.quantum.chemistry.concepts.installation) da biblioteca de química descrevem como usar o pacote [ **Microsoft.Quantum.Chemistry** ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) juntamente com a plataforma de química computacional NWChem e como instalar as `qdk-chem` ferramentas da linha de comando para trabalhar com dados de química quântica.

## <a name="no-locq-applications-or-net-interopability"></a>[Q# aplicações ou interoabilidade .NET](#tab/tabid-csproj)

**Pedido de comando ou Código do Estúdio Visual:** Utilizando o pedido de comando por si só ou a partir do Código do Estúdio Visual, pode utilizar o `dotnet` comando para adicionar uma referência de pacote NuGet ao seu projeto.
Por exemplo, para adicionar o pacote [**Microsoft.Quantum.Nummerics,**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) executar o seguinte comando:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

**Estúdio Visual:** Se estiver a utilizar o Visual Studio 2019 ou mais tarde, pode adicionar pacotes adicionais Q# utilizando o NuGet Package Manager.
Para carregar um pacote: 
1. Com um projeto aberto no Visual Studio, **selecione Manage NuGet Packages...** a partir do menu **Projeto.**

2. Clique **em Procurar,** **selecione Inclua pré-relançar** e procure o nome do pacote "Microsoft.Quantum.Nummerics". Isto listará os pacotes disponíveis para download.

3. Passe por cima **da Microsoft.Quantum.Nummerics** e clique na seta de ponta para baixo à direita do número da versão para instalar o pacote numérico.

Para mais detalhes, consulte o [guia uI do Gestor de Pacotes.](https://docs.microsoft.com/nuget/tools/package-manager-ui)

Em alternativa, pode utilizar a Consola Gestor de Pacotes para adicionar a biblioteca numérica ao seu projeto através da interface da linha de comando.

![Utilize a consola do gestor de pacotes a partir da solicitação de comando](~/media/vs2017-nuget-console-menu.png)

A partir da consola gestor de pacotes, execute o seguinte:

```
Install-Package Microsoft.Quantum.Numerics
```

Para mais detalhes, consulte o guia da [consola do Gestor de Pacotes.](https://docs.microsoft.com/nuget/tools/package-manager-console)

## <a name="ino-locq-notebooks"></a>[I Q# Cadernos](#tab/tabid-notebook)

Pode disponibilizar pacotes adicionais para uso num Bloco de Notas I Q# utilizando o [ `%package` comando mágico.](xref:microsoft.quantum.iqsharp.magic-ref.package)
Por exemplo, para adicionar o pacote [**Microsoft.Quantum.Nummerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) para utilização num Bloco de Q# Notas I, executar o seguinte comando numa célula de portátil:

```
%package Microsoft.Quantum.Numerics
```

Seguindo este comando, o pacote está disponível para quaisquer células dentro do caderno.
Para disponibilizar o pacote a partir do Q# código no espaço de trabalho atual, recarregue o espaço de trabalho após a adição do seu pacote:

```
%workspace reload
```

## <a name="python-interoperability"></a>[Interoperabilidade da python](#tab/tabid-python)


Você pode disponibilizar pacotes adicionais para uso em um programa de anfitrião Python usando o [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages) método.
Por exemplo, para adicionar o pacote [**Microsoft.Quantum.Nummerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) para utilização num Q# bloco de notas I, execute o seguinte código Python:

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

Seguindo este comando, o pacote será disponibilizado a qualquer Q# código compilado utilizando `qsharp.compile` .
Para disponibilizar o pacote a partir do Q# código no espaço de trabalho atual, recarregue o espaço de trabalho após a adição do seu pacote:

```python
qsharp.reload()
```

***
