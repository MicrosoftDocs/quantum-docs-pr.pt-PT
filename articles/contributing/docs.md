---
title: Documentação contributante para o Microsoft QDK
description: Saiba como contribuir com conteúdo conceptual ou API para o conjunto de documentação Quantum da Microsoft.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
ms.openlocfilehash: d244a7841b4093031d6225230a6cbefb22cc6a39
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904898"
---
# <a name="improving-documentation"></a>Melhorar a Documentação #

A documentação para o Kit de Desenvolvimento Quântico assume várias formas diferentes, de tal forma que a informação está prontamente disponível para os desenvolvedores quânticos.

Seguindo os princípios do [Docs como Código,](https://www.writethedocs.org/guide/docs-as-code/)toda a documentação do Kit de Desenvolvimento Quântico é formatada como código e é gerida usando Git da mesma forma que o código fonte que é usado para construir o Kit de Desenvolvimento Quântico.
Na maior parte das vezes, a documentação de apoio ao código consiste em várias formas de [Markdown,](https://daringfireball.net/projects/markdown/)uma linguagem para escrever texto ricamente formatado num formato de texto simples que é fácil de usar na linha de comando, em IDEs, e com controlo de fonte.
Adotamos igualmente a biblioteca [MathJax](https://www.mathjax.org/) para permitir a formatação de matemática em documentação utilizando a língua LaTeX, conforme detalhado mais abaixo.


Dito isto, cada forma de documentação varia um pouco nos detalhes:

- A **documentação conceptual** consiste num conjunto de artigos que são publicados para https://docs.microsoft.com/quantum, e que descrevem tudo, desde os fundamentos da computação quântica até às especificações técnicas para os formatos de intercâmbio. Estes artigos estão escritos em [Markdown (DFM) com sabor do DocFX,](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)uma variante de Markdown usada para criar conjuntos de documentação ricos.
- A **referência API** é um conjunto de páginas para cada função, operação e tipo definido pelo utilizador, publicados para https://docs.microsoft.com/qsharp/api/. Estas páginas documentam as inputs e operações para cada chamada, juntamente com exemplos e links para mais informações. A referência API é extraída automaticamente de pequenos documentos DFM no código fonte Q# como parte de cada lançamento.
- Os ficheiros **README<!---->.md** incluídos em cada amostra e kata descrevem como usar essa amostra ou kata é usada, o que cobre, e como se relaciona com o resto do Kit de Desenvolvimento Quântico. Estes ficheiros são escritos usando [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), uma alternativa mais leve ao DFM que é popular para anexar documentação diretamente aos repositórios de código.

## <a name="contributing-to-the-conceptual-documentation"></a>Contribuir para a Documentação Conceptual ##

Para contribuir com uma melhoria da documentação conceptual ou README, então, começa com um pedido de pull para [**MicrosoftDocs/quantum-docs-pr,** ](https://github.com/MicrosoftDocs/quantum-docs-pr/
) [**Microsoft/Quantum,** ](https://github.com/Microsoft/Quantum)ou [**Microsoft/QuantumKatas,** ](https://github.com/Microsoft/QuantumKatas)como é apropriado.
Descreveremos mais sobre pedidos de puxão abaixo, mas por enquanto há algumas coisas que são boas a ter em mente à medida que melhora a documentação:

- Os leitores chegam à documentação do Quantum Development Kit a partir de uma ampla gama de fundos. Todos, desde estudantes do secundário que procuram aprender algo novo e excitante até ao corpo docente que realiza pesquisas de computação quântica, devem conseguir algo com a leitura da documentação. Na medida do possível, por favor, não assuma um conhecimento extensivo por parte dos seus leitores, pois eles podem estar apenas a começar. É mais útil se você pode fornecer descrições claras e acessíveis, ou pode fornecer links para outros recursos para mais informações.
- Os conjuntos de documentação não são definidos como livros ou papéis, na medida em que os leitores chegarão no que pode parecer o "meio". Por exemplo, os motores de busca podem não sugerir o índice, ou podem ter sido enviados um link por um amigo que tenta ajudá-los. Tente ajudar o leitor fornecendo sempre um contexto claro, juntamente com links sempre que apropriado.
- Alguns leitores acharão as declarações e definições abstratas mais úteis, enquanto outros leitores trabalham melhor extrapolando de exemplos concretos. Fornecer tanto o caso geral como exemplos específicos pode ajudar ambos os leitores a tirar o máximo partido da programação quântica.
- Especialmente se também escreveu o código a ser documentado, as coisas podem ser óbvias para si que não são de todo óbvias para o seu leitor. Não há uma única maneira de programar, por isso, por mais inteligente ou experiente que seja um leitor, não conseguem adivinhar quais os padrões de design que achou mais úteis para expressar as suas ideias em código. Ser claro sobre como um leitor pode esperar fazer uso do seu código pode ajudar a fornecer esse contexto.
- Muitos membros da comunidade de programação quântica são investigadores académicos, e são reconhecidos principalmente através de citações pelas suas contribuições para a comunidade. Além de ajudar os leitores a encontrar materiais adicionais, garantir que cite corretamente os resultados académicos, como jornais, palestras, posts de blogs e ferramentas de software, pode ajudar os colaboradores académicos a continuarem a fazer o seu melhor trabalho para melhorar a comunidade.
- A comunidade de programação quântica é uma comunidade ampla e maravilhosamente diversificada. O uso de pronomes de género em exemplos de terceira pessoa (por exemplo: "se um utilizador..., ele ...") pode trabalhar para excluir em vez de incluir. Ser consciente dos nomes das pessoas em citações e links, e da correta inclusão de personagens não-ASCII pode servir a diversidade da comunidade mostrando respeito aos seus membros. Da mesma forma, muitas palavras na língua inglesa são frequentemente usadas de forma odiosa, de modo que a sua utilização em documentação técnica pode causar danos tanto aos leitores individuais como à comunidade em geral.

## <a name="contributing-to-the-api-references"></a>Contribuir para as Referências Da API ##

Para contribuir com uma melhoria das referências da API, é mais útil abrir um pedido de pull diretamente sobre o código que está a ser documentado.
Cada função, operação ou tipo definido pelo utilizador suporta um comentário de documentação (denotado com `///` em vez de `//`).
Quando compilamos cada lançamento do Kit de Desenvolvimento Quântico, estes comentários são usados para gerar a referência DaPI em https://docs.microsoft.com/qsharp/api/, incluindo detalhes sobre as inputs e saídas de cada callable, os pressupostos que cada callable faz, e exemplos de como usá-los.

> [!IMPORTANT]
> Certifique-se de não editar manualmente a documentação da API gerada, uma vez que estes ficheiros são substituídos a cada nova versão.
> Valorizamos a sua contribuição para a comunidade e queremos garantir que as suas alterações continuam a ajudar os utilizadores a libertarem-se após o lançamento.

Por exemplo, considere a função `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)`.
Um comentário de documentação deve ajudar um utilizador a aprender a interpretar `bits` e `oracle` e para que é a função.
Cada uma destas diferentes informações pode ser fornecida ao compilador Q# por uma secção de Markdown especialmente chamada no comentário de documentação.
Para o exemplo de `ControlledOnBitString`, podemos escrever algo como o seguinte:

```qsharp
 /// # Summary
 /// Returns a unitary operation that applies an oracle on the target register if the 
 /// control register state corresponds to a specified bit mask.
 ///
 /// # Description
 /// The output of this function is an operation that can be represented by a
 /// unitary transformation $U$ such that
 /// \begin{align}
 ///     U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes
 ///     \begin{cases}
 ///         V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\
 ///         \ket{\psi} & \textrm{otherwise}
 ///     \end{cases},
 /// \end{align}
 /// where $V$ is a unitary transformation that represents the action of the
 /// `oracle` operation.
 ///
 /// # Input
 /// ## bits
 /// The bit string to control the given unitary operation on.
 /// ## oracle
 /// The unitary operation to be applied on the target register.
 ///
 /// # Output
 /// A unitary operation that applies `oracle` on the target register if the control 
 /// register state corresponds to the bit mask `bits`.
 ///
 /// # Remarks
 /// The length of `bits` and `controlRegister` must be equal.
 ///
 /// Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function
 /// is an operation that performs the following steps:
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits`;
 /// * apply `Controlled oracle` to the control and target registers;
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits` again to return the control register to the original state.
 ///
 /// The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.
 ///
 /// # Example
 /// The following code snippets are equivalent:
 /// ```qsharp
 /// (ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
 /// ```
 /// and
 /// ```qsharp
 /// within {
 ///     ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
 /// } apply {
 ///     Controlled oracle(controlRegister, targetRegister);
 /// }
 /// ```
 ///
 /// The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:
 /// ```qsharp
 /// using (register = Qubit[2]) {
 ///     ApplyToEach(H, register);
 ///     (ControlledOnBitString([false], Z))(register[0..0], register[1]);
 /// }
 /// ```
 function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
 {
     return ControlledOnBitStringImpl(bits, oracle, _, _);
 }
```
Pode ver a versão renderizada do código acima na [documentação da API para a função `ControlledOnBitString`](xref:microsoft.quantum.canon.controlledonbitstring).

Para além da prática geral da escrita de documentação, por escrito a documentação da API comenta que ajuda a ter algumas coisas em mente:

- O formato de cada comentário de documentação tem de corresponder ao que o compilador Q# espera que a sua documentação apareça corretamente. Algumas secções, como `/// # Remarks` permitem o conteúdo gratuito, enquanto secções como `/// # See Also` secção são mais restritivas.
- O leitor pode ler a sua documentação da API no site principal de referência da API, no resumo de cada espaço de nome, ou mesmo dentro do seu IDE através da utilização de informações sobre o hover. Certificar-se de que `/// # Summary` não é mais longo do que uma frase ajuda o seu leitor a resolver rapidamente se precisa de ler mais ou procurar em outro lugar, e pode ajudar a digitalizar rapidamente os resumos do espaço de nome.
- A sua documentação pode muito bem acabar por ser muito mais longa do que o código em si, mas tudo bem! Mesmo um pequeno pedaço de código pode ter efeitos inesperados para os utilizadores que não sabem o contexto em que esse código existe. Ao fornecer exemplos concretos e explicações claras, pode ajudar os utilizadores a fazer o melhor uso do código que está disponível para eles.

<!-- ## LaTeX Formatting ##

**TODO** -->
