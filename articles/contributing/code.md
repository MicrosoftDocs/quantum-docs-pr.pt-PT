---
title: Código contributante / Microsoft Docs
description: Código contributante
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: f9e0f0d9540102331aea64a1245cbaa4833e1e02
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819965"
---
# <a name="contributing-code"></a><span data-ttu-id="71bcf-103">Contribuir no Código</span><span class="sxs-lookup"><span data-stu-id="71bcf-103">Contributing Code</span></span> #

<span data-ttu-id="71bcf-104">Além de reportar problemas e melhorar a documentação, contribuir com o código para o Kit de Desenvolvimento Quântico pode ser uma forma muito direta de ajudar os seus pares na comunidade de programação quântica.</span><span class="sxs-lookup"><span data-stu-id="71bcf-104">In addition to reporting issues and improving documentation, contributing code to the Quantum Development Kit can be a very direct way to help your peers in the quantum programming community.</span></span>
<span data-ttu-id="71bcf-105">Ao contribuir com código, pode ajudar a corrigir problemas, fornecer novos exemplos, tornar as bibliotecas existentes mais fáceis de usar, ou até adicionar funcionalidades inteiramente novas.</span><span class="sxs-lookup"><span data-stu-id="71bcf-105">By contributing code, you can help to fix issues, provide new examples, make existing libraries easier to use, or even add entirely new features.</span></span>

<span data-ttu-id="71bcf-106">Neste guia, vamos detalhar um pouco do que procuramos quando revermos os pedidos de pull para ajudar a sua contribuição a fazer o melhor.</span><span class="sxs-lookup"><span data-stu-id="71bcf-106">In this guide, we'll detail a bit of what we look for when we review pull requests to help your contribution do the most good.</span></span>

## <a name="what-we-look-for"></a><span data-ttu-id="71bcf-107">O que procuramos</span><span class="sxs-lookup"><span data-stu-id="71bcf-107">What We Look For</span></span> ##

<span data-ttu-id="71bcf-108">Uma contribuição de código ideal baseia-se no trabalho existente num repositório do Kit de Desenvolvimento Quântico para corrigir problemas, expandir as funcionalidades existentes ou adicionar novas funcionalidades que estão no âmbito de um repositório.</span><span class="sxs-lookup"><span data-stu-id="71bcf-108">An ideal code contribution builds on the existing work in a Quantum Development Kit repository to fix issues, expand existing features, or to add new features that are within the scope of a repository.</span></span>
<span data-ttu-id="71bcf-109">Quando aceitamos uma contribuição de código, torna-se parte do próprio Kit de Desenvolvimento Quântico, de modo a que novas funcionalidades sejam lançadas, mantidas e desenvolvidas da mesma forma que o resto do Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="71bcf-109">When we accept a code contribution, it becomes a part of the Quantum Development Kit itself, such that new features will be released, maintained, and developed in the same way as the rest of the Quantum Development Kit.</span></span>
<span data-ttu-id="71bcf-110">Assim, é útil quando a funcionalidade adicionada por uma contribuição é bem testada e está documentada.</span><span class="sxs-lookup"><span data-stu-id="71bcf-110">Thus, it is helpful when functionality added by a contribution is well-tested and is documented.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="71bcf-111">Testes unitários</span><span class="sxs-lookup"><span data-stu-id="71bcf-111">Unit Tests</span></span> ###

<span data-ttu-id="71bcf-112">As funções, operações e tipos definidos pelo utilizador que compõem bibliotecas como o cânone são automaticamente testados como parte do desenvolvimento do repositório [**Microsoft/QuantumLibraries.** ](https://github.com/Microsoft/QuantumLibraries/)</span><span class="sxs-lookup"><span data-stu-id="71bcf-112">The Q# functions, operations, and user-defined types that make up libraries such as the canon are automatically tested as a part of development on the [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) repository.</span></span>
<span data-ttu-id="71bcf-113">Quando um novo pedido de pull é aberto, por exemplo, a nossa configuração [de Pipelines Azure](https://azure.microsoft.com/services/devops/pipelines/) verificará se as alterações no pedido de pull não quebram qualquer funcionalidade existente de que a comunidade de programação quântica dependa.</span><span class="sxs-lookup"><span data-stu-id="71bcf-113">When a new pull request is opened, for instance, our [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) configuration will check that the changes in the pull request do not break any existing functionality that the quantum programming community depends on.</span></span>

<span data-ttu-id="71bcf-114">Com a versão Q# mais recente, o teste de unidade é definido usando o atributo `@Test("QuantumSimulator")`.</span><span class="sxs-lookup"><span data-stu-id="71bcf-114">With the latest Q# version, unit test are defined using the `@Test("QuantumSimulator")` attribute.</span></span> <span data-ttu-id="71bcf-115">O argumento pode ser "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", ou qualquer nome totalmente qualificado que especifique o alvo de execução.</span><span class="sxs-lookup"><span data-stu-id="71bcf-115">The argument may be either "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", or any fully qualified name specifying the execution target.</span></span> <span data-ttu-id="71bcf-116">Vários atributos que definem diferentes alvos de execução podem ser anexados ao mesmo callable.</span><span class="sxs-lookup"><span data-stu-id="71bcf-116">Several attributes defining different execution targets may be attached to the same callable.</span></span> <span data-ttu-id="71bcf-117">Alguns dos nossos testes ainda utilizam o pacote [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) depreciado que expõe todas as funções e operações Q# terminando em `Test` à estrutura [xUnit.](https://xunit.github.io/)</span><span class="sxs-lookup"><span data-stu-id="71bcf-117">Some of our tests still use the deprecated [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) package that exposes all Q# functions and operations ending in `Test` to the [xUnit](https://xunit.github.io/) framework.</span></span> <span data-ttu-id="71bcf-118">Este pacote já não é necessário para definir os testes unitários.</span><span class="sxs-lookup"><span data-stu-id="71bcf-118">This package is no longer needed for defining unit tests.</span></span> 

<span data-ttu-id="71bcf-119">A função seguinte é utilizada para garantir que as funções <xref:microsoft.quantum.canon.fst> e <xref:microsoft.quantum.canon.snd> devolvam as saídas certas num exemplo representativo.</span><span class="sxs-lookup"><span data-stu-id="71bcf-119">The following function is used to ensure that the <xref:microsoft.quantum.canon.fst> and <xref:microsoft.quantum.canon.snd> functions both return the right outputs in a representative example.</span></span>
<span data-ttu-id="71bcf-120">Se a saída de `Fst` ou `Snd` estiver incorreta, a declaração de `fail` é utilizada para fazer com que o teste falhe.</span><span class="sxs-lookup"><span data-stu-id="71bcf-120">If the output of `Fst` or `Snd` is incorrect, the `fail` statement is used to cause the test to fail.</span></span>

```qsharp
@Test("QuantumSimulator")
function PairTest () : Unit {
    let pair = (12, PauliZ);

    if (Fst(pair) != 12) {
        let actual = Fst(pair);
        fail $"Expected 12, actual {actual}.";
    }

    if (Snd(pair) != PauliZ) {
        let actual = Snd(pair);
        fail $"Expected PauliZ, actual {actual}.";
    }
}
```

<span data-ttu-id="71bcf-121">Condições mais complicadas podem ser verificadas utilizando as técnicas na secção de [ensaio](xref:microsoft.quantum.libraries.diagnostics) do guia de bibliotecas padrão.</span><span class="sxs-lookup"><span data-stu-id="71bcf-121">More complicated conditions can be checked using the techniques in the [testing section](xref:microsoft.quantum.libraries.diagnostics) of the standard libraries guide.</span></span>
<span data-ttu-id="71bcf-122">Por exemplo, os seguintes controlos de teste que `H(q); X(q); H(q);` como chamado por <xref:microsoft.quantum.canon.applywith> faz o mesmo que `Z(q)`.</span><span class="sxs-lookup"><span data-stu-id="71bcf-122">For instance, the following test checks that `H(q); X(q); H(q);` as called by <xref:microsoft.quantum.canon.applywith> does the same thing as `Z(q)`.</span></span>

```qsharp
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

<span data-ttu-id="71bcf-123">Ao adicionar novas funcionalidades, é uma boa ideia adicionar também novos testes para garantir que a sua contribuição faz o que é suposto.</span><span class="sxs-lookup"><span data-stu-id="71bcf-123">When adding new features, it's a good idea to also add new tests to make sure that your contribution does what it's supposed to.</span></span>
<span data-ttu-id="71bcf-124">Isto ajuda o resto da comunidade a manter e desenvolver a sua funcionalidade, e em particular ajuda outros desenvolvedores a saberem que podem confiar na sua funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="71bcf-124">This helps the rest of the community to maintain and develop your feature, and in particular helps other developers know that they can rely on your feature.</span></span>

> [!NOTE]
> <span data-ttu-id="71bcf-125">Isto também funciona ao contrário!</span><span class="sxs-lookup"><span data-stu-id="71bcf-125">This works the other way around, too!</span></span>
> <span data-ttu-id="71bcf-126">Se houver uma característica existente que está a faltar a alguns testes, ajudar-nos a adicionar cobertura de teste daria uma grande contribuição para a comunidade.</span><span class="sxs-lookup"><span data-stu-id="71bcf-126">If there's an existing feature that's missing some tests, helping us add test coverage would make a great contribution to the community.</span></span>

<span data-ttu-id="71bcf-127">Localmente, os testes de unidade podem ser executados utilizando o Visual Studio Test Explorer ou o comando `dotnet test`, para que possa verificar a sua contribuição antes de abrir um pedido de pull.</span><span class="sxs-lookup"><span data-stu-id="71bcf-127">Locally, unit tests can be run using the Visual Studio Test Explorer or the `dotnet test` command, so that you can check your contribution before opening up a pull request.</span></span>

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="when-well-reject-a-pull-request"></a><span data-ttu-id="71bcf-128">Quando rejeitaremos um pedido de retirada</span><span class="sxs-lookup"><span data-stu-id="71bcf-128">When We'll Reject a Pull Request</span></span> ##

<span data-ttu-id="71bcf-129">Às vezes, rejeitamos o pedido de uma contribuição.</span><span class="sxs-lookup"><span data-stu-id="71bcf-129">Sometimes, we'll reject the pull request for a contribution.</span></span>
<span data-ttu-id="71bcf-130">Se isto te acontecer, não significa que seja mau, já que há uma série de razões pelas quais podemos não aceitar uma contribuição em particular.</span><span class="sxs-lookup"><span data-stu-id="71bcf-130">If this happens to you, it doesn't mean that it's bad, as there's a number of reasons why we might not be able to accept a particular contribution.</span></span>
<span data-ttu-id="71bcf-131">Talvez mais comumente, uma contribuição para a comunidade de programação quântica é realmente boa, mas os repositórios do Kit de Desenvolvimento Quântico não são o lugar certo para desenvolvê-lo.</span><span class="sxs-lookup"><span data-stu-id="71bcf-131">Perhaps most commonly, a contribution to the quantum programming community is a really good one, but the Quantum Development Kit repositories aren't the right place to develop it.</span></span>
<span data-ttu-id="71bcf-132">Nesses casos, encorajamo-lo a fazer o seu próprio repositório --- parte da força do Kit de Desenvolvimento Quântico é que é fácil fazer e distribuir as suas próprias bibliotecas usando gitHub e NuGet.org, da mesma forma que distribuímos o cânone e a química bibliotecas hoje.</span><span class="sxs-lookup"><span data-stu-id="71bcf-132">In such cases, we strongly encourage you to make your own repository --- part of the strength of the Quantum Development Kit is that it's easy to make and distribute your own libraries using GitHub and NuGet.org, the same way that we distribute the canon and chemistry libraries today.</span></span>

<span data-ttu-id="71bcf-133">Noutras alturas, podemos rejeitar uma boa contribuição simplesmente porque ainda não estamos prontos para a manter e desenvolver.</span><span class="sxs-lookup"><span data-stu-id="71bcf-133">At other times, we may reject a good contribution simply because we aren't yet ready to maintain and develop it.</span></span>
<span data-ttu-id="71bcf-134">Pode ser difícil fazer tudo, por isso planeamos quais as características em que melhor podemos trabalhar como um roteiro.</span><span class="sxs-lookup"><span data-stu-id="71bcf-134">It can be difficult to do everything, so we plan out what features we're best able to work on as a roadmap.</span></span>
<span data-ttu-id="71bcf-135">Este pode ser outro caso em que lançar uma funcionalidade como biblioteca de terceiros pode fazer muito sentido.</span><span class="sxs-lookup"><span data-stu-id="71bcf-135">This can be another case where releasing a feature as a third-party library can make a lot of sense.</span></span>
<span data-ttu-id="71bcf-136">Em alternativa, podemos pedir a sua ajuda para modificar uma funcionalidade para melhor encaixar no nosso roteiro para que possamos fazer o melhor trabalho possível com ele.</span><span class="sxs-lookup"><span data-stu-id="71bcf-136">Alternatively, we may ask for your help in modifying a feature to better fit into our roadmap so that we can do the best work we can with it.</span></span>

<span data-ttu-id="71bcf-137">Também pediremos alterações a um pedido de pull se necessitar de mais documentação ou testes unitários para nos ajudar a usá-lo, ou se difere o suficiente em estilo das restantes bibliotecas Q# que dificultará aos utilizadores encontrar a sua funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="71bcf-137">We'll also ask for changes to a pull request if it requires more documentation or unit tests to help us make use of it, or if it differs enough in style from the rest of the Q# libraries that it will make it harder for users to find your feature.</span></span>
<span data-ttu-id="71bcf-138">Nestes casos, tentaremos oferecer alguns conselhos em revisões de códigosobre o que pode ser adicionado ou alterado para facilitar a sua contribuição para nós incluirmos.</span><span class="sxs-lookup"><span data-stu-id="71bcf-138">In these cases, we'll try to offer some advice in code reviews about what can be added or changed to make your contribution easier for us to include.</span></span>

<span data-ttu-id="71bcf-139">Por último, não podemos aceitar contribuições que causem danos à comunidade de computação quântica, tal como delineado no [Código de Conduta da Microsoft Open Source](https://opensource.microsoft.com/codeofconduct/).</span><span class="sxs-lookup"><span data-stu-id="71bcf-139">Finally, we cannot accept contributions that cause harm the quantum computing community, as outlined in the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="71bcf-140">Queremos assegurar que as contribuições sirvam toda a comunidade de computação quântica, tanto na sua atual diversidade maravilhosa, como no futuro à medida que cresce para se tornar ainda mais inclusiva.</span><span class="sxs-lookup"><span data-stu-id="71bcf-140">We want to ensure that contributions serve the entire quantum computing community, both in its current wonderful diversity, and in the future as it grows to become still more inclusive.</span></span>
<span data-ttu-id="71bcf-141">Agradecemos a sua ajuda na concretização deste objetivo.</span><span class="sxs-lookup"><span data-stu-id="71bcf-141">We appreciate your help in realizing this goal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="71bcf-142">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="71bcf-142">Next steps</span></span> ##

<span data-ttu-id="71bcf-143">Obrigado por ajudar a fazer do Kit de Desenvolvimento Quântico um grande recurso para toda a comunidade de programação quântica!</span><span class="sxs-lookup"><span data-stu-id="71bcf-143">Thanks for helping to make the Quantum Development Kit a great resource for the entire quantum programming community!</span></span>
<span data-ttu-id="71bcf-144">Para saber mais, por favor continue com o seguinte guia no estilo Q#.</span><span class="sxs-lookup"><span data-stu-id="71bcf-144">To learn more, please continue with the following guide on Q# style.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="71bcf-145">Conheça as diretrizes do estilo Q#</span><span class="sxs-lookup"><span data-stu-id="71bcf-145">Learn about Q# style guidelines</span></span>](xref:microsoft.quantum.contributing.style)
