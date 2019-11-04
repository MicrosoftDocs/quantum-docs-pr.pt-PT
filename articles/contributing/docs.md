---
title: Documentação colaborador | Microsoft Docs
description: Documentação colaboradora
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
ms.openlocfilehash: 1e24dd859c0b75a161f4f3c7151e2eec227075a2
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183680"
---
# <a name="improving-documentation"></a>Melhorando a documentação #

A documentação do kit de desenvolvimento Quantum assume várias formas diferentes, de modo que essas informações estão prontamente disponíveis para os desenvolvedores da Quantum.

Seguindo os princípios de [docs como código](https://www.writethedocs.org/guide/docs-as-code/), toda a documentação do kit de desenvolvimento Quantum é formatada como código e é gerenciada usando o Git da mesma forma que o código-fonte usado para criar o kit de desenvolvimento Quantum.
Na maioria das vezes, a documentação de suporte de código consiste em várias formas de [redução](https://daringfireball.net/projects/markdown/), uma linguagem para escrever texto formatado de forma sofisticada em um formato de texto sem formatação que é fácil de usar na linha de comando, em ides e com controle do código-fonte.
De forma semelhante, adotamos a biblioteca [MathJax](https://www.mathjax.org/) para permitir a formatação de matemática na documentação usando a linguagem LaTeX, conforme detalhado abaixo.


Dito isso, cada formulário de documentação varia um pouco nos detalhes:

- A **documentação conceitual** consiste em um conjunto de artigos que são publicados no https://docs.microsoft.com/quantum e que descrevem tudo, desde os conceitos básicos da computação Quantum até as especificações técnicas para formatos de intercâmbio. Esses artigos são escritos em [DFM (redução DocFX)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), uma variante de redução usada para criar conjuntos de documentação avançados.
- A **referência de API** é um conjunto de páginas para cada função Q #, operação e tipo definido pelo usuário, publicado em https://docs.microsoft.com/qsharp/api/. Essas páginas documentam as entradas e operações em cada callable, juntamente com exemplos e links para obter mais informações. A referência de API é extraída automaticamente de pequenos documentos do DFM no código-fonte de Q # como parte de cada versão.
- Os arquivos **. md<!---->Leiame** incluídos em cada exemplo e Kata descrevem como usar esse exemplo ou Kata é usado, o que ele abrange e como ele se relaciona com o restante do kit de desenvolvimento Quantum. Esses arquivos são escritos usando a [GFM (redução de tipo de GitHub)](https://github.github.com/gfm/), uma alternativa mais leve ao DFM que é popular para anexar documentação diretamente a repositórios de código.

## <a name="contributing-to-the-conceptual-documentation"></a>Contribuindo com a documentação conceitual ##

Para contribuir com uma melhoria na documentação conceitual ou LEIAme, o começa com uma solicitação de pull em [**MicrosoftDocs/Quantum-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)ou [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), como é apropriado.
Descreveremos mais sobre as solicitações pull abaixo, mas, por enquanto, há algumas coisas que são boas para se ter em mente ao melhorar a documentação:

- Os leitores vêm à documentação do kit de desenvolvimento do quantum de uma grande variedade de planos de fundo. Todas as pessoas de estudantes de ensino médio que buscam aprender algo novo e empolgante até o corpo docente que realiza a pesquisa de computação Quantum devem ser capazes de obter algo sem ler a documentação. Na medida que for possível, não assuma conhecimento extensivo sobre a parte de seus leitores, pois eles podem apenas começar. É mais útil se você puder fornecer descrições claras e acessíveis, ou pode fornecer links para outros recursos para obter mais informações.
- Os conjuntos de documentação não são dispostos como livros ou documentos, pois os leitores chegarão ao que pode parecer o "meio". Por exemplo, os mecanismos de pesquisa podem não sugerir o índice ou podem ter recebido um link por um amigo tentando ajudá-lo. Tente ajudar seu leitor, sempre fornecendo um contexto claro, juntamente com links quando apropriado.
- Alguns leitores encontrarão instruções e definições abstratas mais úteis, enquanto outros leitores funcionam melhor, extrapolando-se de exemplos concretos. Fornecer os exemplos de caso geral e específicos pode ajudar os leitores a obter o máximo da programação Quantum.
- Especialmente se você também escreveu o código que está sendo documentado, as coisas podem ser óbvias para você que não são óbvias para seu leitor. Não existe uma melhor maneira de programar, portanto, independentemente de quão inteligente ou experiente um leitor possa ser, eles não podem adivinhar em quais padrões de design você encontrou o mais útil para expressar suas ideias no código. Estar claro sobre como um leitor pode esperar fazer uso do seu código pode ajudar a fornecer esse contexto.
- Muitos membros da comunidade de programação Quantum são pesquisadores acadêmicos e são reconhecidos principalmente por meio de citações para suas contribuições para a Comunidade. Além de ajudar os leitores a encontrar materiais adicionais, certificar-se de que as saídas acadêmicas, como artigos, palestras, Postagens de blog e ferramentas de software, possam ajudar os colaboradores acadêmicos a continuar a fazer o melhor trabalho para melhorar a Comunidade.
- A comunidade de programação Quantum é uma comunidade ampla e maravilhosamente diversificada. O uso de prostantivos sexos em exemplos de terceiros (por exemplo: "se um usuário..., ele vai...") pode funcionar para excluir em vez de incluir. Ser Cognizant de nomes de pessoas em citações e links, e a inclusão correta de caracteres não-ASCII pode servir a diversidade da Comunidade, mostrando respeito a seus membros. Da mesma forma, muitas palavras no idioma Inglês são frequentemente usadas de forma Hateful, de modo que seu uso na documentação técnica pode causar danos tanto aos leitores individuais quanto à Comunidade em geral.

## <a name="contributing-to-the-api-references"></a>Contribuindo para as referências de API ##

Para contribuir com uma melhoria nas referências de API, é mais útil abrir uma solicitação de pull diretamente no código que está sendo documentado.
Cada função, operação ou tipo definido pelo usuário dá suporte a um comentário de documentação (indicado com `///` em vez de `//`).
Quando compilamos cada versão do kit de desenvolvimento Quantum, esses comentários são usados para gerar a referência de API em https://docs.microsoft.com/qsharp/api/ , incluindo detalhes sobre as entradas e saídas de cada callable, as suposições que cada callable faz e exemplos de como usá-los.

> [!IMPORTANT]
> Certifique-se de não editar manualmente a documentação da API gerada, pois esses arquivos são substituídos por cada nova versão.
> Estamos informando sua contribuição para a Comunidade e queremos garantir que suas alterações continuem a ajudar os usuários a liberar após o lançamento.

Por exemplo, considere uma operação `PrepareTrialState(angles : Double[], register : Qubit[]) : Unit`.
Um comentário de documentação deve ajudar um usuário a aprender a interpretar `angles`, o que a operação assume sobre o estado inicial de `register`, qual é o efeito no `register` e assim por diante.
Cada uma dessas diferentes partes de informações pode ser fornecida ao compilador Q # por uma seção de redução especialmente nomeada no comentário da documentação.
Para obter o exemplo de `PrepareTrialState`, poderemos escrever algo semelhante ao seguinte:

```qsharp
/// # Summary
/// Given a register of qubits, prepares them in a trial state by rotating each
/// independently.
///
/// # Description
/// This operation prepares the input register by performing a
/// $Y$ rotation on each qubit by an angle given in `angles`.
///
/// # Input
/// ## angles
/// An array of parameters
/// ## register
/// A register of qubits initially in the $\ket{00\cdots0}$ state.
///
/// # Example
/// To prepare an equal superposition $\ket{++\cdots+}$ over all input qubits:
/// ```qsharp
/// PrepareTrialState(ConstantArray(Length(register), PI() / 2.0), register);
/// ```
///
/// # Remarks
/// This operation is generally useful in the inner loop of an optimization
/// algorithm.
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.Ry
operation PrepareTrialState(angles : Double[], register : Qubit[]) : Unit {
    // ...
}
```

Além da prática geral da escrita da documentação, ao escrever comentários sobre a documentação da API, ele ajuda a manter algumas coisas em mente:

- O formato de cada comentário de documentação tem que corresponder ao que o compilador Q # espera para que sua documentação apareça corretamente. Algumas seções, como `/// # Remarks` permitem conteúdo de forma livre, enquanto as seções, como `/// # See Also` seção, são mais restritivas.
- Um leitor pode ler a documentação da API no site de referência da API principal, no Resumo de cada namespace ou mesmo de dentro de seu IDE por meio do uso de informações em foco. Certificar-se de que `/// # Summary` não é maior do que uma frase ajuda seu leitor a classificar rapidamente se precisa ler mais ou procurar em outro lugar e pode ajudar a examinar rapidamente os resumos de namespace.
- Sua documentação pode ser muito mais demorada do que o próprio código, mas tudo bem! Mesmo uma pequena parte do código pode ter efeitos inesperados para os usuários que não conhecem o contexto no qual o código existe. Ao fornecer exemplos concretos e explicações claras, você pode ajudar os usuários a fazer o melhor uso do código que está disponível para eles.

<!-- ## LaTeX Formatting ##

**TODO** -->
