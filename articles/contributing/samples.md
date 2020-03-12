---
title: Contribuindo com amostras para o Microsoft QDK
description: Saiba como contribuir com o código da amostra para o Kit de Desenvolvimento Quântico da Microsoft (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
ms.openlocfilehash: 3bd0de04a448c74eea6c3e8e3a15dcbb19f9d705
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024156"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a>Contribuindo com amostras para o Kit de Desenvolvimento Quântico

Se está interessado em contribuir com código para o [repositório de amostras,](https://github.com/Microsoft/Quantum)obrigado por fazer da comunidade de desenvolvimento quântico um lugar melhor!

## <a name="the-quantum-development-kit-samples-repository"></a>O Kit de Desenvolvimento Quântico Amostras Repositório

Para ajudá-lo a preparar a sua contribuição para ajudar o máximo possível, é útil dar uma olhada rápida na forma como o repositório de amostras é estabelecido:

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

Ou seja, as amostras do [repositório Microsoft/Quantum](https://github.com/microsoft/Quantum) são discriminadas por área de assunto em diferentes pastas, tais como `algorithms/`, `arithmetic/`ou `characterization/`.
Dentro da pasta para cada área temática, cada amostra consiste numa única pasta que recolhe tudo o que um utilizador precisa de explorar e fazer uso dessa amostra.

## <a name="how-samples-are-structured"></a>Como as amostras são estruturadas

Olhando para os ficheiros que compõem cada pasta, vamos mergulhar na amostra [`algorithms/chsh-game/`.](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game)

| Ficheiro              | Descrição                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | Projeto Q# usado para construir a amostra com o .NET Core SDK |
| `Game.qs`         | Q# operações e funções para a amostra                 |
| `Host.cs`         | C#programa anfitrião usado para executar a amostra                     |
| `host.py`         | Programa de anfitriões python usado para executar a amostra                 |
| `README.md`       | Documentação sobre o que a amostra faz e como usá-la    |

Nem todas as amostras terão exatamente o mesmo conjunto C#de ficheiros (por exemplo: algumas amostras podem ser - apenas, outras podem não ter um hospedeiro Python, ou algumas amostras podem exigir que os ficheiros de dados auxionares funcionem).

## <a name="anatomy-of-a-helpful-readme-file"></a>Anatomia de um arquivo README útil

Um ficheiro especialmente importante, no entanto, é o ficheiro `README.md`, já que é isso que os utilizadores precisam para começar com a sua amostra!

Cada `README.md` deve começar com alguns metadados que ajudam docs.microsoft.com/samples encontrar a sua contribuição.

> [!div class="nextstepaction"]
> [Veja como a amostra chsh-game é renderizada](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

Estes metadados são fornecidos como um [cabeçalho YAML](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) que indica que idiomas a sua amostra cobre (normalmente, este será `qsharp`, `csharp`e `python`), e quais os produtos que a sua amostra cobre (normalmente, apenas `qdk`).

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> A chave `page_type: sample` no cabeçalho é necessária para que a sua amostra apareça em docs.microsoft.com/samples.
> Da mesma forma, as chaves `product` e `language` são fundamentais para ajudar os utilizadores a encontrar e executar a sua amostra.

Depois disso, é útil dar uma introdução curta que diz o que a sua nova amostra faz:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

Os utilizadores da sua amostra também apreciarão saber o que precisam para executá-la (por exemplo: os utilizadores só precisam do Próprio Kit de Desenvolvimento Quântico, ou precisam de software adicional, como o nó.js?):

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

Com tudo isso no lugar, pode dizer aos utilizadores como executar a sua amostra:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

Finalmente, é útil dizer aos utilizadores o que cada ficheiro na sua amostra faz, e onde podem ir para mais informações:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> Certifique-se de que utiliza URLs absolutos aqui, uma vez que a sua amostra aparecerá num URL diferente quando for renderizada em docs.microsoft.com/samples!
