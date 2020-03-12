---
title: Código contributante para o Microsoft QDK
description: Saiba como contribuir com o código de amostra e biblioteca para o Kit de Desenvolvimento Quântico da Microsoft (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: edc52dc4434e91258bece28812fd76b66329c6f9
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/10/2020
ms.locfileid: "79022461"
---
# <a name="contributing-code"></a>Contribuir no Código

Além de reportar problemas e melhorar a documentação, contribuir com o código para o Kit de Desenvolvimento Quântico pode ser uma forma muito direta de ajudar os seus pares na comunidade de programação quântica.
Ao contribuir com código, pode ajudar a corrigir problemas, fornecer novos exemplos, tornar as bibliotecas existentes mais fáceis de usar, ou até adicionar funcionalidades inteiramente novas.

Neste guia, vamos detalhar um pouco do que procuramos quando revermos os pedidos de pull para ajudar a sua contribuição a fazer o melhor.

## <a name="what-we-look-for"></a>O que procuramos

Uma contribuição de código ideal baseia-se no trabalho existente num repositório do Kit de Desenvolvimento Quântico para corrigir problemas, expandir as funcionalidades existentes ou adicionar novas funcionalidades que estão no âmbito de um repositório.
Quando aceitamos uma contribuição de código, torna-se parte do próprio Kit de Desenvolvimento Quântico, de modo a que novas funcionalidades sejam lançadas, mantidas e desenvolvidas da mesma forma que o resto do Kit de Desenvolvimento Quântico.
Assim, é útil quando a funcionalidade adicionada por uma contribuição é bem testada e está documentada.

### <a name="unit-tests"></a>Testes unitários

As funções, operações e tipos definidos pelo utilizador que compõem bibliotecas como o cânone são automaticamente testados como parte do desenvolvimento do repositório [**Microsoft/QuantumLibraries.** ](https://github.com/Microsoft/QuantumLibraries/)
Quando um novo pedido de pull é aberto, por exemplo, a nossa configuração [de Pipelines Azure](https://azure.microsoft.com/services/devops/pipelines/) verificará se as alterações no pedido de pull não quebram qualquer funcionalidade existente de que a comunidade de programação quântica dependa.

Com a versão Q# mais recente, o teste de unidade é definido usando o atributo `@Test("QuantumSimulator")`. O argumento pode ser "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", ou qualquer nome totalmente qualificado que especifique o alvo de execução. Vários atributos que definem diferentes alvos de execução podem ser anexados ao mesmo callable. Alguns dos nossos testes ainda utilizam o pacote [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) depreciado que expõe todas as funções e operações Q# terminando em `Test` à estrutura [xUnit.](https://xunit.github.io/) Este pacote já não é necessário para definir os testes unitários. 

A função seguinte é utilizada para garantir que as funções <xref:microsoft.quantum.canon.fst> e <xref:microsoft.quantum.canon.snd> devolvam as saídas certas num exemplo representativo.
Se a saída de `Fst` ou `Snd` estiver incorreta, a declaração de `fail` é utilizada para fazer com que o teste falhe.

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

Condições mais complicadas podem ser verificadas utilizando as técnicas na secção de [ensaio](xref:microsoft.quantum.libraries.diagnostics) do guia de bibliotecas padrão.
Por exemplo, os seguintes controlos de teste que `H(q); X(q); H(q);` como chamado por <xref:microsoft.quantum.canon.applywith> faz o mesmo que `Z(q)`.

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

Localmente, os testes de unidade podem ser executados utilizando o Visual Studio Test Explorer ou o comando `dotnet test`, para que possa verificar a sua contribuição antes de abrir um pedido de pull.

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->


## <a name="when-well-reject-a-pull-request"></a>Quando rejeitaremos um pedido de retirada

Às vezes, rejeitamos o pedido de uma contribuição.
Se isto te acontecer, não significa que seja mau, já que há uma série de razões pelas quais podemos não aceitar uma contribuição em particular.
Talvez mais comumente, uma contribuição para a comunidade de programação quântica é realmente boa, mas os repositórios do Kit de Desenvolvimento Quântico não são o lugar certo para desenvolvê-lo.
Nesses casos, encorajamo-lo a fazer o seu próprio repositório --- parte da força do Kit de Desenvolvimento Quântico é que é fácil fazer e distribuir as suas próprias bibliotecas usando gitHub e NuGet.org, da mesma forma que distribuímos o cânone e a química bibliotecas hoje.

Noutras alturas, podemos rejeitar uma boa contribuição simplesmente porque ainda não estamos prontos para a manter e desenvolver.
Pode ser difícil fazer tudo, por isso planeamos quais as características em que melhor podemos trabalhar como um roteiro.
Este pode ser outro caso em que lançar uma funcionalidade como biblioteca de terceiros pode fazer muito sentido.
Em alternativa, podemos pedir a sua ajuda para modificar uma funcionalidade para melhor encaixar no nosso roteiro para que possamos fazer o melhor trabalho possível com ele.

Também pediremos alterações a um pedido de pull se necessitar de mais documentação ou testes unitários para nos ajudar a usá-lo, ou se difere o suficiente em estilo das restantes bibliotecas Q# que dificultará aos utilizadores encontrar a sua funcionalidade.
Nestes casos, tentaremos oferecer alguns conselhos em revisões de códigosobre o que pode ser adicionado ou alterado para facilitar a sua contribuição para nós incluirmos.

Por último, não podemos aceitar contribuições que causem danos à comunidade de computação quântica, tal como delineado no [Código de Conduta da Microsoft Open Source](https://opensource.microsoft.com/codeofconduct/).
Queremos assegurar que as contribuições sirvam toda a comunidade de computação quântica, tanto na sua atual diversidade maravilhosa, como no futuro à medida que cresce para se tornar ainda mais inclusiva.
Agradecemos a sua ajuda na concretização deste objetivo.

## <a name="next-steps"></a>Passos seguintes

Obrigado por ajudar a fazer do Kit de Desenvolvimento Quântico um grande recurso para toda a comunidade de programação quântica!
Para saber mais, por favor continue com o seguinte guia no estilo Q#.

> [!div class="nextstepaction"]
> [Conheça as diretrizes do estilo Q#](xref:microsoft.quantum.contributing.style)

Dependendo do tipo de código que está a contribuir, pode haver coisas adicionais a ter em mente que podem ajudá-lo a fazer a sua contribuição fazer o melhor possível para a comunidade.

> [!div class="nextstepaction"]
> [Saiba mais sobre a contribuição de amostras](xref:microsoft.quantum.contributing.samples)
