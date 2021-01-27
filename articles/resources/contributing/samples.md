---
title: Amostras contribuindo para o Microsoft QDK
description: Saiba como contribuir com o código de amostra para o Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.samples
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0c940a4cf228c694a899988f469158b1bb6e2425
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847589"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a>Amostras contribuindo para o Kit de Desenvolvimento Quântico

Se está interessado em contribuir com o código para o [repositório de amostras,](https://github.com/Microsoft/Quantum)obrigado por fazer da comunidade de desenvolvimento quântico um lugar melhor!

## <a name="the-quantum-development-kit-samples-repository"></a>O Kit de Desenvolvimento Quântico mostra repositório

Para ajudá-lo a preparar a sua contribuição para ajudar o máximo possível, é útil dar uma olhada rápida na forma como o repositório de amostras está definido:

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

Ou seja, as [amostras do repositório microsoft/Quantum](https://github.com/microsoft/Quantum) são divididas por área temática em diferentes pastas, tais como `algorithms/` , ou `arithmetic/` `characterization/` .
Dentro da pasta para cada área de assunto, cada amostra é constituída por uma única pasta que recolhe tudo o que um utilizador precisa para explorar e fazer uso dessa amostra.

## <a name="how-samples-are-structured"></a>Como as amostras são estruturadas

Olhando para os ficheiros que compõem cada pasta, vamos mergulhar na [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/chsh-game) amostra.

| Ficheiro              | Descrição                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | Q# projeto usado para construir a amostra com o .NET Core SDK |
| `Game.qs`         | Q# operações e funções para a amostra                 |
| `Host.cs`         | C# programa de anfitrião usado para executar a amostra                     |
| `host.py`         | Programa de anfitrião python usado para executar a amostra                 |
| `README.md`       | Documentação sobre o que a amostra faz e como usá-la    |

Nem todas as amostras terão exatamente o mesmo conjunto de ficheiros (por exemplo: algumas amostras podem ser C#-only, outras podem não ter um hospedeiro Python, ou algumas amostras podem exigir que os ficheiros de dados auxillary funcionem).

## <a name="anatomy-of-a-helpful-readme-file"></a>Anatomia de um Arquivo README Útil

Um ficheiro especialmente importante, no entanto, é o `README.md` ficheiro, já que é isso que os utilizadores precisam para começar com a sua amostra!

Cada um `README.md` deve começar com alguns metadados que ajudam docs.microsoft.com/samples encontrar a sua contribuição.

> [!div class="nextstepaction"]
> [Veja como a amostra do chsh-game é renderizada](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

Estes metadados são fornecidos como um [cabeçalho YAML](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) que indica quais as línguas que a sua amostra cobre (normalmente, isto será `qsharp` , e ) e quais os produtos que a sua amostra cobre `csharp` `python` (normalmente, `qdk` apenas).

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> A `page_type: sample` chave no cabeçalho é necessária para que a sua amostra apareça em docs.microsoft.com/samples.
> Da mesma forma, as `product` chaves e as chaves são `language` fundamentais para ajudar os utilizadores a encontrar e executar a sua amostra.

Depois disso, é útil dar uma pequena introdução que diga o que a sua nova amostra faz:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

Os utilizadores da sua amostra também apreciarão saber o que precisam para executá-lo (por exemplo: os utilizadores só precisam do próprio Kit de Desenvolvimento Quântico, ou precisam de software adicional, como node.js?):

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

Com tudo isso no lugar, pode dizer aos utilizadores como executar a sua amostra:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

Finalmente, é útil dizer aos utilizadores o que cada ficheiro da sua amostra faz, e onde podem ir para mais informações:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> Certifique-se de que utiliza URLs absolutos aqui, uma vez que a sua amostra aparecerá num URL diferente quando renderizado em docs.microsoft.com/samples!
