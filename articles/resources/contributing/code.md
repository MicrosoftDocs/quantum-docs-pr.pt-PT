---
title: Código contribuindo para o Microsoft QDK
description: Saiba como contribuir com o código de amostra e biblioteca para o Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: edc52dc4434e91258bece28812fd76b66329c6f9
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275483"
---
# <a name="contributing-code"></a>Contribuir no Código

Além de relatar problemas e melhorar a documentação, contribuir com o código para o Kit de Desenvolvimento Quântico pode ser uma forma muito direta de ajudar os seus pares na comunidade de programação quântica.
Ao contribuir com o código, pode ajudar a corrigir problemas, fornecer novos exemplos, facilitar a utilização das bibliotecas existentes ou até adicionar funcionalidades inteiramente novas.

Neste guia, vamos detalhar um pouco do que procuramos quando analisarmos os pedidos de retirada para ajudar a sua contribuição a fazer o melhor.

## <a name="what-we-look-for"></a>O que procuramos

Uma contribuição de código ideal baseia-se no trabalho existente num repositório do Kit de Desenvolvimento Quântico para corrigir problemas, expandir as funcionalidades existentes ou adicionar novas funcionalidades que estão no âmbito de um repositório.
Quando aceitamos uma contribuição de código, torna-se parte do próprio Kit de Desenvolvimento Quântico, de tal forma que novas funcionalidades serão lançadas, mantidas e desenvolvidas da mesma forma que o resto do Kit de Desenvolvimento Quântico.
Assim, é útil quando a funcionalidade adicionada por uma contribuição é bem testada e é documentada.

### <a name="unit-tests"></a>Testes de Unidade

As funções Q#, operações e tipos definidos pelo utilizador que compõem bibliotecas como o cânone são automaticamente testados como parte do desenvolvimento no repositório [**Microsoft/QuantumLibraries.**](https://github.com/Microsoft/QuantumLibraries/)
Quando um novo pedido de puxar é aberto, por exemplo, a nossa configuração [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) verificará se as alterações no pedido de puxar não quebram qualquer funcionalidade existente de que a comunidade de programação quântica dependa.

Com a versão Q# mais recente, o teste de unidade é definido usando o `@Test("QuantumSimulator")` atributo. O argumento pode ser "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", ou qualquer nome totalmente qualificado especificando o alvo de execução. Vários atributos que definem diferentes alvos de execução podem ser ligados à mesma chamada. Alguns dos nossos testes ainda usam o pacote deprecado [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) que expõe todas as funções e operações Q# que terminam no `Test` quadro [xUnit.](https://xunit.github.io/) Este pacote já não é necessário para definir os testes unitários. 

A função seguinte é utilizada para garantir que <xref:microsoft.quantum.canon.fst> as e <xref:microsoft.quantum.canon.snd> as funções retornam as saídas certas num exemplo representativo.
Se a saída de `Fst` ou `Snd` estiver incorreta, a declaração é utilizada `fail` para fazer com que o teste falhe.

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

Condições mais complicadas podem ser verificadas utilizando as técnicas na secção de [testes](xref:microsoft.quantum.libraries.diagnostics) do guia de bibliotecas padrão.
Por exemplo, os seguintes testes verificam `H(q); X(q); H(q);` que, tal como chamado <xref:microsoft.quantum.canon.applywith> por, faz o mesmo que `Z(q)` .

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

Ao adicionar novas funcionalidades, é uma boa ideia adicionar também novos testes para garantir que a sua contribuição faz o que é suposto.
Isto ajuda o resto da comunidade a manter e desenvolver a sua funcionalidade, e em particular ajuda outros desenvolvedores a saberem que podem confiar na sua funcionalidade.

> [!NOTE]
> Isto também funciona ao contrário!
> Se houver uma característica existente que está a faltar a alguns testes, ajudar-nos a adicionar cobertura de teste daria uma grande contribuição para a comunidade.

Localmente, os testes de unidade podem ser executados usando o Visual Studio Test Explorer ou o `dotnet test` comando, para que possa verificar a sua contribuição antes de abrir um pedido de puxar.

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->


## <a name="when-well-reject-a-pull-request"></a>Quando rejeitarmos um pedido de retirada

Às vezes, rejeitamos o pedido de ajuda.
Se isto te acontecer, não significa que seja mau, pois há uma série de razões pelas quais podemos não aceitar uma contribuição em particular.
Talvez mais comummente, uma contribuição para a comunidade de programação quântica é realmente boa, mas os repositórios do Kit de Desenvolvimento Quântico não são o lugar certo para desenvolvê-lo.
Nestes casos, encorajamo-lo a fazer o seu próprio repositório --- parte da força do Kit de Desenvolvimento Quântico é que é fácil fazer e distribuir as suas próprias bibliotecas usando o GitHub e NuGet.org, da mesma forma que hoje distribuímos as bibliotecas cânones e químicas.

Noutras alturas, podemos rejeitar uma boa contribuição simplesmente porque ainda não estamos prontos para mantê-la e desenvolvê-la.
Pode ser difícil fazer tudo, por isso planeamos quais as características em que melhor podemos trabalhar como um roteiro.
Este pode ser outro caso em que a libertação de uma funcionalidade como biblioteca de terceiros pode fazer muito sentido.
Em alternativa, podemos pedir a sua ajuda para modificar uma funcionalidade que se encaixe melhor no nosso roteiro para que possamos fazer o melhor trabalho possível com ele.

Também pediremos alterações a um pedido de puxar se necessitar de mais documentação ou testes de unidade para nos ajudar a utilizá-lo, ou se diferir o suficiente em estilo do resto das bibliotecas Q# que dificultará aos utilizadores encontrar a sua funcionalidade.
Nestes casos, tentaremos oferecer alguns conselhos em análises de código sobre o que pode ser adicionado ou alterado para facilitar a sua contribuição para nós.

Finalmente, não podemos aceitar contribuições que causem danos à comunidade de computação quântica, tal como delineado no [Código de Conduta microsoft Open Source](https://opensource.microsoft.com/codeofconduct/).
Queremos assegurar que as contribuições sirvam toda a comunidade da computação quântica, tanto na sua maravilhosa diversidade atual, como no futuro, à medida que se torna ainda mais inclusiva.
Agradecemos a sua ajuda na concretização deste objetivo.

## <a name="next-steps"></a>Passos seguintes

Obrigado por ajudar a fazer do Kit de Desenvolvimento Quântico um grande recurso para toda a comunidade de programação quântica!
Para saber mais, continue com o seguinte guia sobre o estilo Q#.

> [!div class="nextstepaction"]
> [Saiba mais sobre as diretrizes de estilo Q#](xref:microsoft.quantum.contributing.style)

Dependendo do tipo de código que está a contribuir, pode haver coisas adicionais a ter em mente que podem ajudá-lo a fazer a sua contribuição fazer o melhor possível para a comunidade.

> [!div class="nextstepaction"]
> [Saiba mais sobre amostras contribuíndo](xref:microsoft.quantum.contributing.samples)
