---
title: Documentação contributante para o Microsoft QDK
description: Saiba como contribuir com conteúdo conceptual ou API para o conjunto de documentação Quantum da Microsoft.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
ms.openlocfilehash: ed5ab5df9de5d71ccd922cd430cf15779806dd6a
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/10/2020
ms.locfileid: "79022639"
---
# <a name="improving-documentation"></a><span data-ttu-id="24bf6-103">Melhorar a Documentação</span><span class="sxs-lookup"><span data-stu-id="24bf6-103">Improving Documentation</span></span>

<span data-ttu-id="24bf6-104">A documentação para o Kit de Desenvolvimento Quântico assume várias formas diferentes, de tal forma que a informação está prontamente disponível para os desenvolvedores quânticos.</span><span class="sxs-lookup"><span data-stu-id="24bf6-104">The documentation for the Quantum Development Kit takes on several different forms, such that information is readily available to quantum developers.</span></span>

<span data-ttu-id="24bf6-105">Seguindo os princípios do [Docs como Código,](https://www.writethedocs.org/guide/docs-as-code/)toda a documentação do Kit de Desenvolvimento Quântico é formatada como código e é gerida usando Git da mesma forma que o código fonte que é usado para construir o Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="24bf6-105">Following the principles of [Docs as Code](https://www.writethedocs.org/guide/docs-as-code/), all Quantum Development Kit documentation is formatted as code and is managed using Git in the same way as the source code that is used to build the Quantum Development Kit.</span></span>
<span data-ttu-id="24bf6-106">Na maior parte das vezes, a documentação de apoio ao código consiste em várias formas de [Markdown,](https://daringfireball.net/projects/markdown/)uma linguagem para escrever texto ricamente formatado num formato de texto simples que é fácil de usar na linha de comando, em IDEs, e com controlo de fonte.</span><span class="sxs-lookup"><span data-stu-id="24bf6-106">For the most part, the code backing documentation consists of various forms of [Markdown](https://daringfireball.net/projects/markdown/), a language for writing out richly formatted text in a plain text format that's easy to use at the command line, in IDEs, and with source control.</span></span>
<span data-ttu-id="24bf6-107">Adotamos igualmente a biblioteca [MathJax](https://www.mathjax.org/) para permitir a formatação de matemática em documentação utilizando a língua LaTeX, conforme detalhado mais abaixo.</span><span class="sxs-lookup"><span data-stu-id="24bf6-107">We similarly adopt the [MathJax](https://www.mathjax.org/) library to allow for formatting mathematics in documentation using the LaTeX language, as detailed further below.</span></span>


<span data-ttu-id="24bf6-108">Dito isto, cada forma de documentação varia um pouco nos detalhes:</span><span class="sxs-lookup"><span data-stu-id="24bf6-108">That said, each form of documentation does vary somewhat in the details:</span></span>

- <span data-ttu-id="24bf6-109">A **documentação conceptual** consiste num conjunto de artigos que são publicados para https://docs.microsoft.com/quantum, e que descrevem tudo, desde os fundamentos da computação quântica até às especificações técnicas para os formatos de intercâmbio.</span><span class="sxs-lookup"><span data-stu-id="24bf6-109">The **conceptual documentation** consists of a set of articles that are published to https://docs.microsoft.com/quantum, and that describe everything from the basics of quantum computing to the technical specifications for interchange formats.</span></span> <span data-ttu-id="24bf6-110">Estes artigos estão escritos em [Markdown (DFM) com sabor do DocFX,](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)uma variante de Markdown usada para criar conjuntos de documentação ricos.</span><span class="sxs-lookup"><span data-stu-id="24bf6-110">These articles are written in [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a Markdown variant used for creating rich documentation sets.</span></span>
- <span data-ttu-id="24bf6-111">A **referência API** é um conjunto de páginas para cada função, operação e tipo definido pelo utilizador, publicados para https://docs.microsoft.com/qsharp/api/.</span><span class="sxs-lookup"><span data-stu-id="24bf6-111">The **API reference** is a set of pages for each Q# function, operation, and user-defined type, published to https://docs.microsoft.com/qsharp/api/.</span></span> <span data-ttu-id="24bf6-112">Estas páginas documentam as inputs e operações para cada chamada, juntamente com exemplos e links para mais informações.</span><span class="sxs-lookup"><span data-stu-id="24bf6-112">These pages document the inputs and operations to each callable, along with examples and links to more information.</span></span> <span data-ttu-id="24bf6-113">A referência API é extraída automaticamente de pequenos documentos DFM no código fonte Q# como parte de cada lançamento.</span><span class="sxs-lookup"><span data-stu-id="24bf6-113">The API reference is automatically extracted from small DFM documents in Q# source code as a part of each release.</span></span>
- <span data-ttu-id="24bf6-114">Os ficheiros **README<!---->.md** incluídos em cada amostra e kata descrevem como usar essa amostra ou kata é usada, o que cobre, e como se relaciona com o resto do Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="24bf6-114">The **README<!---->.md** files included with each sample and kata describe how to use that sample or kata is used, what it covers, and how it relates to the rest of the Quantum Development Kit.</span></span> <span data-ttu-id="24bf6-115">Estes ficheiros são escritos usando [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), uma alternativa mais leve ao DFM que é popular para anexar documentação diretamente aos repositórios de código.</span><span class="sxs-lookup"><span data-stu-id="24bf6-115">These files are written using [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), a more lightweight alternative to DFM that's popular for attaching documentation directly to code repositories.</span></span>

## <a name="contributing-to-the-conceptual-documentation"></a><span data-ttu-id="24bf6-116">Contribuir para a Documentação Conceptual</span><span class="sxs-lookup"><span data-stu-id="24bf6-116">Contributing to the Conceptual Documentation</span></span>

<span data-ttu-id="24bf6-117">Para contribuir com uma melhoria da documentação conceptual ou README, então, começa com um pedido de pull para [**MicrosoftDocs/quantum-docs-pr,** ](https://github.com/MicrosoftDocs/quantum-docs-pr/
) [**Microsoft/Quantum,** ](https://github.com/Microsoft/Quantum)ou [**Microsoft/QuantumKatas,** ](https://github.com/Microsoft/QuantumKatas)como é apropriado.</span><span class="sxs-lookup"><span data-stu-id="24bf6-117">To contribute an improvement to the conceptual or README documentation, then, starts with a pull request onto either [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum), or [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), as is appropriate.</span></span>
<span data-ttu-id="24bf6-118">Descreveremos mais sobre pedidos de puxão abaixo, mas por enquanto há algumas coisas que são boas a ter em mente à medida que melhora a documentação:</span><span class="sxs-lookup"><span data-stu-id="24bf6-118">We'll describe more about pull requests below, but for now there's a few things that are good to keep in mind as you improve documentation:</span></span>

- <span data-ttu-id="24bf6-119">Os leitores chegam à documentação do Quantum Development Kit a partir de uma ampla gama de fundos.</span><span class="sxs-lookup"><span data-stu-id="24bf6-119">Readers come to the Quantum Development Kit documentation from a very wide range of backgrounds.</span></span> <span data-ttu-id="24bf6-120">Todos, desde estudantes do secundário que procuram aprender algo novo e excitante até ao corpo docente que realiza pesquisas de computação quântica, devem conseguir algo com a leitura da documentação.</span><span class="sxs-lookup"><span data-stu-id="24bf6-120">Everyone from high school students looking to learn something new and exciting through to tenured faculty performing quantum computing research should be able to get something out of reading the documentation.</span></span> <span data-ttu-id="24bf6-121">Na medida do possível, por favor, não assuma um conhecimento extensivo por parte dos seus leitores, pois eles podem estar apenas a começar. É mais útil se você pode fornecer descrições claras e acessíveis, ou pode fornecer links para outros recursos para mais informações.</span><span class="sxs-lookup"><span data-stu-id="24bf6-121">To the extent that's possible, please don't assume extensive knowledge on the part of your readers, as they may just be starting out. It's most helpful if you can provide clear and accessible descriptions, or can provide links to other resources for more information.</span></span>
- <span data-ttu-id="24bf6-122">Os conjuntos de documentação não são definidos como livros ou papéis, na medida em que os leitores chegarão no que pode parecer o "meio".</span><span class="sxs-lookup"><span data-stu-id="24bf6-122">Documentation sets aren't laid out like books or papers, in that readers will arrive in what might seem like the "middle."</span></span> <span data-ttu-id="24bf6-123">Por exemplo, os motores de busca podem não sugerir o índice, ou podem ter sido enviados um link por um amigo que tenta ajudá-los. Tente ajudar o leitor fornecendo sempre um contexto claro, juntamente com links sempre que apropriado.</span><span class="sxs-lookup"><span data-stu-id="24bf6-123">For example, search engines might not suggest the index, or they might have been sent a link by a friend trying to help them out. Try to help your reader by always providing a clear context, along with links where appropriate.</span></span>
- <span data-ttu-id="24bf6-124">Alguns leitores acharão as declarações e definições abstratas mais úteis, enquanto outros leitores trabalham melhor extrapolando de exemplos concretos.</span><span class="sxs-lookup"><span data-stu-id="24bf6-124">Some readers will find abstract statements and definitions most helpful, while other readers work best by extrapolating from concrete examples.</span></span> <span data-ttu-id="24bf6-125">Fornecer tanto o caso geral como exemplos específicos pode ajudar ambos os leitores a tirar o máximo partido da programação quântica.</span><span class="sxs-lookup"><span data-stu-id="24bf6-125">Providing both the general case and specific examples can help both readers get the most out of quantum programming.</span></span>
- <span data-ttu-id="24bf6-126">Especialmente se também escreveu o código a ser documentado, as coisas podem ser óbvias para si que não são de todo óbvias para o seu leitor.</span><span class="sxs-lookup"><span data-stu-id="24bf6-126">Especially if you also wrote the code being documented, things may be obvious to you that are not at all obvious to your reader.</span></span> <span data-ttu-id="24bf6-127">Não há uma única maneira de programar, por isso, por mais inteligente ou experiente que seja um leitor, não conseguem adivinhar quais os padrões de design que achou mais úteis para expressar as suas ideias em código.</span><span class="sxs-lookup"><span data-stu-id="24bf6-127">There's no one unique best way to program, so no matter how clever or experienced a reader might be, they can't guess at what design patterns you found the most helpful to express your ideas in code.</span></span> <span data-ttu-id="24bf6-128">Ser claro sobre como um leitor pode esperar fazer uso do seu código pode ajudar a fornecer esse contexto.</span><span class="sxs-lookup"><span data-stu-id="24bf6-128">Being clear about how a reader can expect to make use of your code can help provide that context.</span></span>
- <span data-ttu-id="24bf6-129">Muitos membros da comunidade de programação quântica são investigadores académicos, e são reconhecidos principalmente através de citações pelas suas contribuições para a comunidade.</span><span class="sxs-lookup"><span data-stu-id="24bf6-129">Many members of the quantum programming community are academic researchers, and are recognized mainly through citations for their contributions to the community.</span></span> <span data-ttu-id="24bf6-130">Além de ajudar os leitores a encontrar materiais adicionais, garantir que cite corretamente os resultados académicos, como jornais, palestras, posts de blogs e ferramentas de software, pode ajudar os colaboradores académicos a continuarem a fazer o seu melhor trabalho para melhorar a comunidade.</span><span class="sxs-lookup"><span data-stu-id="24bf6-130">In addition to helping readers find additional materials, making sure to properly cite academic outputs such as papers, talks, blog posts, and software tools can help academic contributors to keep doing their best work to improve the community.</span></span>
- <span data-ttu-id="24bf6-131">A comunidade de programação quântica é uma comunidade ampla e maravilhosamente diversificada.</span><span class="sxs-lookup"><span data-stu-id="24bf6-131">The quantum programming community is a broad and wonderfully diverse community.</span></span> <span data-ttu-id="24bf6-132">O uso de pronomes de género em exemplos de terceira pessoa (por exemplo: "se um utilizador..., ele ...") pode trabalhar para excluir em vez de incluir.</span><span class="sxs-lookup"><span data-stu-id="24bf6-132">The use of gendered pronouns in third-person examples (e.g.: "if a user ..., he will ...") can work to exclude rather than include.</span></span> <span data-ttu-id="24bf6-133">Ser consciente dos nomes das pessoas em citações e links, e da correta inclusão de personagens não-ASCII pode servir a diversidade da comunidade mostrando respeito aos seus membros.</span><span class="sxs-lookup"><span data-stu-id="24bf6-133">Being cognizant of people's names in citations and links, and of the correct inclusion of non-ASCII characters can serve the diversity of the community by showing respect to its members.</span></span> <span data-ttu-id="24bf6-134">Da mesma forma, muitas palavras na língua inglesa são frequentemente usadas de forma odiosa, de modo que a sua utilização em documentação técnica pode causar danos tanto aos leitores individuais como à comunidade em geral.</span><span class="sxs-lookup"><span data-stu-id="24bf6-134">Similarly, many words in the English language are often used in a hateful manner, such that their use in technical documentation can cause harm both to individual readers and to the community at large.</span></span>

### <a name="referencing-sample-code-from-conceptual-articles"></a><span data-ttu-id="24bf6-135">Referenciação do Código da Amostra de Artigos Conceituais</span><span class="sxs-lookup"><span data-stu-id="24bf6-135">Referencing Sample Code from Conceptual Articles</span></span>

<span data-ttu-id="24bf6-136">Se quiser incluir código do [repositório de amostras,](https://github.com/Microsoft/Quantum)pode fazê-lo usando um comando especial de Markdown com sabor do DocFX:</span><span class="sxs-lookup"><span data-stu-id="24bf6-136">If you want to include code from the [samples repository](https://github.com/Microsoft/Quantum), you can do so using a special DocFX-Flavored Markdown command:</span></span>

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

<span data-ttu-id="24bf6-137">Este comando importará as linhas 4 a 8 do [ficheiro`Game.qs` a partir da amostra `chsh-game`,](https://github.com/microsoft/Quantum/blob/master/samples/algorithms/chsh-game/Game.qs)marcando-as como código Q# para efeitos de realce de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="24bf6-137">This command will import lines 4 to 8 of the [`Game.qs` file from the `chsh-game` sample](https://github.com/microsoft/Quantum/blob/master/samples/algorithms/chsh-game/Game.qs), marking them as Q# code for the purpose of syntax highlighting.</span></span>
<span data-ttu-id="24bf6-138">Utilizando este comando, pode evitar duplicar o código entre artigos conceptuais e o repositório de amostras, de modo que o código da amostra na documentação está sempre o mais atualizado possível.</span><span class="sxs-lookup"><span data-stu-id="24bf6-138">Using this command, you can avoid duplicating code between conceptual articles and the samples repository, so that sample code in documentation is always as up to date as possible.</span></span>

## <a name="contributing-to-the-api-references"></a><span data-ttu-id="24bf6-139">Contribuir para as Referências Da API</span><span class="sxs-lookup"><span data-stu-id="24bf6-139">Contributing to the API References</span></span>

<span data-ttu-id="24bf6-140">Para contribuir com uma melhoria das referências da API, é mais útil abrir um pedido de pull diretamente sobre o código que está a ser documentado.</span><span class="sxs-lookup"><span data-stu-id="24bf6-140">To contribute an improvement to the API references, it's most helpful to open a pull request directly on the code being documented.</span></span>
<span data-ttu-id="24bf6-141">Cada função, operação ou tipo definido pelo utilizador suporta um comentário de documentação (denotado com `///` em vez de `//`).</span><span class="sxs-lookup"><span data-stu-id="24bf6-141">Each function, operation, or user-defined type supports a documentation comment (denoted with `///` instead of `//`).</span></span>
<span data-ttu-id="24bf6-142">Quando compilamos cada lançamento do Kit de Desenvolvimento Quântico, estes comentários são usados para gerar a referência DaPI em https://docs.microsoft.com/qsharp/api/, incluindo detalhes sobre as inputs e saídas de cada callable, os pressupostos que cada callable faz, e exemplos de como usá-los.</span><span class="sxs-lookup"><span data-stu-id="24bf6-142">When we compile each release of the Quantum Development Kit, these comments are used to generate the API reference at https://docs.microsoft.com/qsharp/api/, including details about the inputs to and outputs from each callable, the assumptions each callable makes, and examples of how to use them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24bf6-143">Certifique-se de não editar manualmente a documentação da API gerada, uma vez que estes ficheiros são substituídos a cada nova versão.</span><span class="sxs-lookup"><span data-stu-id="24bf6-143">Please make sure to not manually edit the generated API documentation, as these files are overwritten with each new release.</span></span>
> <span data-ttu-id="24bf6-144">Valorizamos a sua contribuição para a comunidade e queremos garantir que as suas alterações continuam a ajudar os utilizadores a libertarem-se após o lançamento.</span><span class="sxs-lookup"><span data-stu-id="24bf6-144">We value your contribution to the community, and want to make sure that your changes continue to help users release after release.</span></span>

<span data-ttu-id="24bf6-145">Por exemplo, considere a função `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="24bf6-145">For example, consider the function `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="24bf6-146">Um comentário de documentação deve ajudar um utilizador a aprender a interpretar `bits` e `oracle` e para que é a função.</span><span class="sxs-lookup"><span data-stu-id="24bf6-146">A documentation comment should help a user learn how to interpret `bits` and `oracle` and what the function is for.</span></span>
<span data-ttu-id="24bf6-147">Cada uma destas diferentes informações pode ser fornecida ao compilador Q# por uma secção de Markdown especialmente chamada no comentário de documentação.</span><span class="sxs-lookup"><span data-stu-id="24bf6-147">Each of these different pieces of information can be provided to the Q# compiler by a specially named Markdown section in the documentation comment.</span></span>
<span data-ttu-id="24bf6-148">Para o exemplo de `ControlledOnBitString`, podemos escrever algo como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="24bf6-148">For the example of `ControlledOnBitString`, we might write something like the following:</span></span>

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

<span data-ttu-id="24bf6-149">Pode ver a versão renderizada do código acima na [documentação da API para a função `ControlledOnBitString`](xref:microsoft.quantum.canon.controlledonbitstring).</span><span class="sxs-lookup"><span data-stu-id="24bf6-149">You can see the rendered version of the code above in the [API documentation for the `ControlledOnBitString` function](xref:microsoft.quantum.canon.controlledonbitstring).</span></span>

<span data-ttu-id="24bf6-150">Para além da prática geral da escrita de documentação, por escrito a documentação da API comenta que ajuda a ter algumas coisas em mente:</span><span class="sxs-lookup"><span data-stu-id="24bf6-150">In addition to the general practice of documentation writing, in writing API documentation comments it helps to keep a few things in mind:</span></span>

- <span data-ttu-id="24bf6-151">O formato de cada comentário de documentação tem de corresponder ao que o compilador Q# espera que a sua documentação apareça corretamente.</span><span class="sxs-lookup"><span data-stu-id="24bf6-151">The format of each documentation comment has to match what the Q# compiler expects for your documentation to appear correctly.</span></span> <span data-ttu-id="24bf6-152">Algumas secções, como `/// # Remarks` permitem o conteúdo gratuito, enquanto secções como `/// # See Also` secção são mais restritivas.</span><span class="sxs-lookup"><span data-stu-id="24bf6-152">Some sections, such as `/// # Remarks` allow for freeform content, while sections such as `/// # See Also` section are more restrictive.</span></span>
- <span data-ttu-id="24bf6-153">O leitor pode ler a sua documentação da API no site principal de referência da API, no resumo de cada espaço de nome, ou mesmo dentro do seu IDE através da utilização de informações sobre o hover.</span><span class="sxs-lookup"><span data-stu-id="24bf6-153">A reader may read your API documentation on the main API reference site, on the summary for each namespace, or even from within their IDE through the use of hover information.</span></span> <span data-ttu-id="24bf6-154">Certificar-se de que `/// # Summary` não é mais longo do que uma frase ajuda o seu leitor a resolver rapidamente se precisa de ler mais ou procurar em outro lugar, e pode ajudar a digitalizar rapidamente os resumos do espaço de nome.</span><span class="sxs-lookup"><span data-stu-id="24bf6-154">Making sure that `/// # Summary` isn't longer than about a sentence helps your reader quickly sort out whether they need to read further or look elsewhere, and can help in quickly scanning through namespace summaries.</span></span>
- <span data-ttu-id="24bf6-155">A sua documentação pode muito bem acabar por ser muito mais longa do que o código em si, mas tudo bem!</span><span class="sxs-lookup"><span data-stu-id="24bf6-155">Your documentation may well wind up being much longer than the code itself, but that's OK!</span></span> <span data-ttu-id="24bf6-156">Mesmo um pequeno pedaço de código pode ter efeitos inesperados para os utilizadores que não sabem o contexto em que esse código existe.</span><span class="sxs-lookup"><span data-stu-id="24bf6-156">Even a small piece of code can have unexpected effects to users that don't know the context in which that code exists.</span></span> <span data-ttu-id="24bf6-157">Ao fornecer exemplos concretos e explicações claras, pode ajudar os utilizadores a fazer o melhor uso do código que está disponível para eles.</span><span class="sxs-lookup"><span data-stu-id="24bf6-157">By providing concrete examples and clear explanations, you can help users make the best use of the code that's available to them.</span></span>

<!-- ## LaTeX Formatting ##

**TODO** -->
