---
title: Documentação contribuindo para o Microsoft QDK
description: Saiba como contribuir com conteúdo conceptual ou API para o conjunto de documentação quântica da Microsoft.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.docs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8602705d2dd071e822e2ff58a9a44cd0684f77f1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857365"
---
# <a name="improving-documentation"></a>Melhorar a documentação

A documentação para o Kit de Desenvolvimento Quântico assume várias formas diferentes, de modo a que a informação esteja prontamente disponível para desenvolvedores quânticos.

Seguindo os princípios de [Docs como Código,](https://www.writethedocs.org/guide/docs-as-code/)toda a documentação do Kit de Desenvolvimento Quântico é formatada como código e é gerida usando o Git da mesma forma que o código fonte que é usado para construir o Kit de Desenvolvimento Quântico.
Na maior parte das vezes, a documentação de suporte de código consiste em várias formas de [Markdown,](https://daringfireball.net/projects/markdown/)um idioma para escrever texto ricamente formatado num formato de texto simples que é fácil de usar na linha de comando, em IDEs, e com controlo de origem.
Também adotamos a biblioteca [MathJax](https://www.mathjax.org/) para permitir a formatação matemática em documentação usando a língua LaTeX, como detalhado mais abaixo.


Dito isto, cada forma de documentação varia um pouco nos detalhes:

- A **documentação conceptual** consiste num conjunto de artigos que são publicados para https://docs.microsoft.com/quantum , e que descrevem tudo, desde os fundamentos da computação quântica até às especificações técnicas para formatos de intercâmbio. Estes artigos são escritos em [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), uma variante de Markdown usada para criar conjuntos de documentação ricos.
- A **referência API** é um conjunto de páginas para cada Q# função, operação e tipo definido pelo utilizador, publicado para https://docs.microsoft.com/qsharp/api/ . Estas páginas documentam as entradas e operações a cada chamada, juntamente com exemplos e links para mais informações. A referência API é extraída automaticamente a partir de pequenos documentos DFM em Q# código fonte como parte de cada libertação.
- Os ficheiros **README <!----> .md** incluídos em cada amostra e kata descrevem como usar essa amostra ou kata é usado, o que cobre e como se relaciona com o resto do Kit de Desenvolvimento Quântico. Estes ficheiros são escritos usando [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), uma alternativa mais leve ao DFM que é popular para anexar documentação diretamente aos repositórios de código.

## <a name="contributing-to-the-conceptual-documentation"></a>Contribuindo para a Documentação Conceptual

Para contribuir com uma melhoria da documentação conceptual ou README, começa então com um pedido de puxar para [**o MicrosoftDocs/quantum-docs-pr,**](https://github.com/MicrosoftDocs/quantum-docs-pr/
) [**Microsoft/Quantum,**](https://github.com/Microsoft/Quantum)ou [**Microsoft/QuantumKatas,**](https://github.com/Microsoft/QuantumKatas)conforme apropriado.
Descreveremos mais sobre pedidos de puxar abaixo, mas por enquanto há algumas coisas que são boas a ter em mente à medida que melhora a documentação:

- Os leitores vêm à documentação do Kit de Desenvolvimento Quântico de uma vasta gama de origens. Todos os alunos do ensino secundário que procuram aprender algo novo e excitante até aos docentes que realizam pesquisas de computação quântica devem ser capazes de obter algo fora da leitura da documentação. Na medida do possível, por favor, não assuma um vasto conhecimento por parte dos seus leitores, pois podem estar apenas a começar. É muito útil se você pode fornecer descrições claras e acessíveis, ou pode fornecer links para outros recursos para mais informações.
- Os conjuntos de documentação não são definidos como livros ou papéis, na medida em que os leitores chegarão no que pode parecer o "meio". Por exemplo, os motores de busca podem não sugerir o índice, ou podem ter sido enviados um link por um amigo tentando ajudá-los. Tente ajudar o seu leitor fornecendo sempre um contexto claro, juntamente com links sempre que apropriado.
- Alguns leitores acharão as declarações e definições abstratas mais úteis, enquanto outros leitores trabalham melhor extrapolando a partir de exemplos concretos. Fornecer tanto o caso geral como exemplos específicos pode ajudar ambos os leitores a tirar o máximo partido da programação quântica.
- Especialmente se também escreveu o código que está a ser documentado, as coisas podem ser óbvias para si que não são de todo óbvias para o seu leitor. Não há uma única maneira única de programar, por isso, por mais inteligente ou experiente que um leitor possa ser, eles não conseguem adivinhar quais os padrões de design que achou mais úteis para expressar as suas ideias em código. Ser claro sobre como um leitor pode esperar fazer uso do seu código pode ajudar a fornecer esse contexto.
- Muitos membros da comunidade de programação quântica são investigadores académicos, e são reconhecidos principalmente através de citações pelas suas contribuições para a comunidade. Além de ajudar os leitores a encontrar materiais adicionais, certificar-se de citar corretamente saídas académicas como jornais, palestras, posts de blog e ferramentas de software pode ajudar os colaboradores académicos a continuarem a fazer o seu melhor trabalho para melhorar a comunidade.
- A comunidade de programação quântica é uma comunidade ampla e maravilhosamente diversificada. A utilização de pronomes de género em exemplos de terceira pessoa (por exemplo: "se um utilizador..., eles trabalharão...") pode trabalhar para excluir em vez de incluir. Ser consciente dos nomes das pessoas em citações e ligações, e da correta inclusão de caracteres não ASCII pode servir a diversidade da comunidade mostrando respeito aos seus membros. Da mesma forma, muitas palavras na língua inglesa são frequentemente usadas de forma odiosa, de modo que a sua utilização em documentação técnica pode causar danos tanto aos leitores individuais como à comunidade em geral.

### <a name="referencing-sample-code-from-conceptual-articles"></a>Referência do Código da Amostra a partir de artigos conceptuais

Se pretender incluir o código do [repositório de amostras,](https://github.com/Microsoft/Quantum)pode fazê-lo utilizando um comando especial DocFX-Flavored Markdown:

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

Este comando importará as linhas 4 a 8 [ `Game.qs` do ficheiro da `chsh-game` amostra,](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs)marcando-as como Q# código para efeitos de prostaxe.
Utilizando este comando, pode evitar duplicar o código entre os artigos conceptuais e o repositório de amostras, de modo que o código de amostra na documentação esteja sempre o mais atualizado possível.

### <a name="contributing-image-files"></a>Processos de imagem que contribuem

**IMPORTANTE**: Para que as imagens se tornem corretamente em modo escuro, deve evitar transparências.

- Para .jpg ficheiros. não precisa de fazer nada, uma vez que o formato .jpg não suporta elementos transparentes.
- Para .png ficheiros, deve adicionar um fundo branco ou alterar o valor do canal alfa para **100**. A forma mais fácil de o fazer no Windows é abrir o ficheiro em **Paint** e guardá-lo, sobrepondo o ficheiro original.
- Para .svg ficheiros, deve adicionar um retângulo branco na camada mais baixa. Pode fazê-lo com **o Inkscape:**
  1. Abra o ficheiro .svg.
  1. Selecione a ferramenta de máquina de fazer quadrados e desenhe um retângulo branco em cima da figura original.
  1. Selecione a ferramenta **Selecione e transforme os objetos** clicando na seta escura ou pressionando **F1**.
  1. Enquanto seleciona o retângulo, clique no elemento barra de **ferramentas Seleção inferior a baixo (Final)**.
  1. Ajuste o retângulo com o rato ou as teclas de seta.

## <a name="contributing-to-the-api-references"></a>Contribuindo para as Referências da API

Para contribuir com uma melhoria das referências da API, é mais útil abrir um pedido de puxar diretamente sobre o código que está a ser documentado.
Cada função, operação ou tipo definido pelo utilizador suporta um comentário de documentação (denotado `///` em vez de `//` ).
Quando compilamos cada lançamento do Kit de Desenvolvimento Quântico, estes comentários são usados para gerar a referência API em https://docs.microsoft.com/qsharp/api/ , incluindo detalhes sobre as entradas e saídas de cada chamada, os pressupostos que cada chamada faz, e exemplos de como usá-los.

> [!IMPORTANT]
> Certifique-se de que não edita manualmente a documentação da API gerada, uma vez que estes ficheiros são substituídos a cada nova versão.
> Valorizamos a sua contribuição para a comunidade e queremos garantir que as suas alterações continuem a ajudar os utilizadores a lançar após o lançamento.

Por exemplo, considere a função `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` .
Um comentário de documentação deve ajudar um utilizador a aprender a interpretar `bits` e a qual é a `oracle` função.
Cada uma destas diferentes informações pode ser fornecida ao Q# compilador por uma secção especialmente denominada Markdown no comentário da documentação.
Para o exemplo `ControlledOnBitString` de, podemos escrever algo como:

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

Pode ver a versão renderizada do código acima na documentação da [API para a `ControlledOnBitString` função](xref:Microsoft.Quantum.Canon.ControlledOnBitString).

Para além da prática geral da escrita de documentação, por escrito a documentação da API comenta que ajuda a ter algumas coisas em mente:

- O formato de cada comentário de documentação tem de corresponder ao que o Q# compilador espera que a sua documentação apareça corretamente. Algumas secções, tais como `/// # Remarks` permitir o conteúdo da forma livre, enquanto secções como a secção são mais `/// # See Also` restritivas.
- Um leitor pode ler a sua documentação da API no site de referência da API principal, no resumo de cada espaço de nome, ou mesmo dentro do seu IDE através da utilização de informações sobre hover. Certificar-se de que `/// # Summary` não é mais do que uma frase ajuda o leitor a resolver rapidamente se precisa de ler mais ou procurar em outro lugar, e pode ajudar a digitalizar rapidamente através de resumos de espaço de nome.
- A sua documentação pode muito bem acabar por ser muito mais longa do que o código em si, mas tudo bem! Mesmo um pequeno pedaço de código pode ter efeitos inesperados para os utilizadores que não sabem o contexto em que esse código existe. Ao fornecer exemplos concretos e explicações claras, pode ajudar os utilizadores a fazer o melhor uso do código que está disponível para eles.

<!-- ## LaTeX Formatting ##

**TODO** -->
