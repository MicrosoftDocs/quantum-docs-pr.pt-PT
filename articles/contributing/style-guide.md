---
title: 'Guia de estilo de Q # | Microsoft Docs'
description: 'Guia de estilo de Q #'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 56455e9d5cd452b8620ee794f40563d1d3040193
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183850"
---
# <a name="q-style-guide"></a>Guia de estilo de Q # #
## <a name="general-conventions"></a>Convenções gerais ##

As convenções sugeridas neste guia destinam-se a ajudar a tornar os programas e bibliotecas escritos em Q # mais fáceis de ler e entender.

# <a name="guidancetabguidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Nunca desconsidere uma convenção, a menos que você esteja fazendo isso intencionalmente para fornecer código mais legível e compreensível para seus usuários.

# <a name="examplestabexamples"></a>[Exemplos](#tab/examples)

***

## <a name="naming-conventions"></a>Convenções de nomenclatura ##

Na oferta do kit de desenvolvimento Quantum, nos esforçamos os nomes de função e operação que ajudam os desenvolvedores da Quantum a escrever programas que são fáceis de ler e que minimizam a surpresa.
Uma parte importante disso é que, quando escolhemos nomes para funções, operações e tipos, estamos estabelecendo o *vocabulário* que os programadores usam para expressar conceitos de Quantum; com nossas opções, nós nos ajudamos ou nos atrapalhamos em seus esforços para se comunicar claramente.
Isso faz com que a empresa tenha a certeza de que os nomes que apresentamos oferecem clareza, em vez de obscurecimento.
Nesta seção, detalhamos como atendemos a essa obrigação em termos de diretrizes explícitas que nos ajudam a fazer o melhor da comunidade de desenvolvimento do Q #.

### <a name="operations-and-functions"></a>Operações e funções ###

Uma das primeiras coisas que um nome deve estabelecer é se um determinado símbolo representa uma função ou uma operação.
A diferença entre funções e operações é essencial para entender como um bloco de código se comporta.
Para comunicar a distinção entre funções e operações para os usuários, nós nos deparamos com as operações Quantum de modelos Q # usando efeitos colaterais.
Ou seja, uma operação *faz* algo.

Por outro lado, as funções descrevem as relações matemáticas entre os dados.
A expressão `Sin(PI() / 2.0)` *é* `1.0`da e não implica nada sobre o estado de um programa ou seu qubits.

Resumindo, as operações fazem coisas enquanto as funções são coisas.
Essa distinção sugere que nós nomeamos operações como verbos e funções como substantivos.

> [!NOTE]
> Quando um tipo definido pelo usuário é declarado, uma nova função que constrói instâncias desse tipo é definida implicitamente ao mesmo tempo.
> Dessa perspectiva, os tipos definidos pelo usuário devem ser nomeados como substantivos para que o próprio tipo e a função de Construtor tenham nomes consistentes.

Quando for razoável, certifique-se de que os nomes de operação comecem com verbos que indiquem claramente o efeito assumido pela operação.
Por exemplo:

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

Um caso que merece menção especial é quando uma operação usa outra operação como entrada e a chama.
Nesses casos, a ação tomada pela operação de entrada não é clara quando a operação externa é definida, de modo que o verbo direito não é limpo imediatamente.
Recomendamos o `Apply`de verbo, como em `ApplyIf`, `ApplyToEach`e `ApplyToFirst`.
Outros verbos também podem ser úteis nesse caso, como em `IterateThroughCartesianPower`.

| Verbo | Efeito esperado |
| ---- | ------ |
| Registe-se | Uma operação fornecida como entrada é chamada |
| Declarar | Uma hipótese sobre o resultado de uma possível medição de Quantum é verificada por um simulador |
| Estimativa | Um valor clássico é retornado, representando uma estimativa desenhada de uma ou mais medições |
| Mensura | Uma medida do Quantum é executada e seu resultado é retornado para o usuário |
| Preparar | Um determinado registro de qubits é inicializado em um estado específico |
| Exemplo | Um valor clássico é retornado aleatoriamente de alguma distribuição |

Para funções, sugerimos evitar o uso de verbos em favor de substantivos comuns (consulte as diretrizes sobre os nomes apropriados abaixo) ou adjetivos:

- `ConstantArray`
- `Head`
- `LookupFunction`

Em particular, em quase todos os casos, sugerimos usar participles anteriores, quando apropriado, para indicar que um nome de função está firmemente conectado a uma ação ou efeito colateral em outro lugar em um programa Quantum.
Por exemplo, `ControlledOnInt` usa a forma particípio da parte do verbo "Control" para indicar que a função atua como um adjetivo para modificar seu argumento.
Esse nome tem o benefício adicional de corresponder a semântica do functor interno de `Controlled`, conforme discutido mais adiante.
Da mesma forma, os _substantivos do agente_ podem ser usados para construir nomes de função e UDT a partir de nomes de operação, como no caso do nome `Encoder` para um UDT que esteja fortemente associado a `Encode`.

# <a name="guidancetabguidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Use verbos para nomes de operação.
- Use substantivos ou adjetivos para nomes de função.
- Use substantivos para atributos e tipos definidos pelo usuário.
- Para todos os nomes que podem ser chamados, use `CamelCase` de preferência forte para `pascalCase`, `snake_case`ou `ANGRY_CASE`. Em particular, verifique se os nomes que podem ser chamados começam com letras maiúsculas.
- Para todas as variáveis locais, use `pascalCase` de preferência forte para `CamelCase`, `snake_case`ou `ANGRY_CASE`. Em particular, verifique se as variáveis locais começam com letras minúsculas.
- Evite o uso de sublinhados `_` em nomes de função e de operação; onde são necessários níveis adicionais de hierarquia, use namespaces e aliases de namespace.

# <a name="examplestabexamples"></a>[Exemplos](#tab/examples)

|   | Nome | Descrição |
|---|------|-------------|
| ☑ | `operation ReflectAboutStart` | Limpar o uso de um verbo ("refletir") para indicar o efeito da operação. |
| ☒ | <s>`operation XRotation`</s> | O uso da frase de substantivo sugere a função, em vez da operação. |
| ☒ | <s>`operation search_oracle`</s> | Uso de notação de `snake_case` contravenes Q #. |
| ☒ | <s>`operation Search_Oracle`</s> | Uso de sublinhados internos para o nome da operação contravenes Q # Notation. |
| ☑ | `function StatePreparationOracle` | O uso de frase de substantivo sugere que a função retorna uma operação. |
| ☑ | `function EqualityFact` | Limpe o uso de substantivo ("Fact") para indicar que essa é uma função, enquanto o adjetivo. |
| ☒ | <s>`function GetRotationAngles`</s> | O uso de verbo ("Get") sugere que se trata de uma operação. |
| ☑ | `newtype GeneratorTerm` | O uso de frase de substantivo claramente se refere ao resultado da chamada do Construtor UDT. |
| ☒ | <s>`@Attribute() newtype RunOnce()`</s> | O uso de frase verbal sugere que o Construtor UDT é uma operação. |
| ☑ | `@Attribute() newtype Deprecated(Reason : String)` | O uso de frase de substantivo comunica o uso do atributo. |

***

### <a name="shorthand-and-abbreviations"></a>Abreviação e abreviações ###

O aviso acima não obstante, há muitas formas de abreviação que vêem o uso comum e generalizado na computação Quantum.
Sugerimos usar a abreviação existente e comum onde ela existe, especialmente para operações intrínsecas à operação de um computador de destino.
Por exemplo, escolhemos o nome `X` em vez de `ApplyX`e `Rz` em vez de `RotateAboutZ`.
Ao usar esse formato abreviado, os nomes de operação devem ser letras maiúsculas (por exemplo: `MAJ`).

É necessário ter cuidado ao aplicar essa Convenção no caso de acrônimos comumente usados e inicialismos como "QFT" para "transformação de Fourier do Quantum".
Sugerimos as seguintes convenções gerais do .NET para o uso de acrônimos e inicialismos em nomes completos, que prescrevem que:

- acrônimos de duas letras e inicialismos são nomeados em letras maiúsculas (por exemplo: `BE` para "big-endian"),
- todos os acrônimos mais longos e inicialismos são nomeados em `CamelCase` (por exemplo: `Qft` para "transformação de Fourier do Quantum")

Assim, uma operação que implementa o QFT poderia ser chamada `QFT` como abreviação ou gravada como `ApplyQft`.

Para operações e funções comumente usadas, pode ser desejável fornecer um nome abreviado como um _alias_ para um formulário mais longo:

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidancetabguidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Considere os nomes abreviados comumente aceitos e amplamente usados quando apropriado.
- Use maiúsculas para abreviar.
- Use letras maiúsculas para acrônimos curtos (duas letras) e inicialismos.
- Use `CamelCase` para maiores (três ou mais letras) acrônimos e inicialismos.

# <a name="examplestabexamples"></a>[Exemplos](#tab/examples)

|   | Nome | Descrição |
|---|------|-------------|
| ☑ | `X` | Atalho bem compreendido para "aplicar uma transformação de $X $" |
| ☑ | `CNOT` | Atalho bem compreendido para "controlado-não" |
| ☒ | <s>`Cnot`</s> | A abreviação não deve estar em `CamelCase`. |
| ☑ | `ApplyQft` | O início comum "QFT" aparece como parte de um nome de formato longo. |
| ☑ | `QFT` | O inicial comum "QFT" aparece como parte de um nome abreviado. |



***


### <a name="proper-nouns-in-names"></a>Substantivos próprios em nomes ###

Embora na física seja comum nomear coisas depois da primeira pessoa a publicar sobre elas, a maioria das não physicistss não está familiarizada com os nomes de todos e todo o histórico.
Depender muito muito nas convenções de nomenclatura da física pode, portanto, criar uma barreira substancial para a entrada, pois os usuários de outros planos de fundo devem aprender um grande número de nomes aparentemente opacos para usar operações e conceitos comuns.
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
Portanto, é recomendável que, sempre que for razoável, os substantivos comuns que descrevem um conceito seja adotado em preferência forte a nomes próprios incorretos que descrevem o histórico de publicação de um conceito.
Como um exemplo específico, as operações de troca e duplamente controladas de forma única são chamadas de operações "Fredkin" e "Toffoli" em literatura acadêmica, mas são identificadas em Q # principalmente como `CSWAP` e `CCNOT`.
Em ambos os casos, os comentários de documentação da API fornecem nomes sinônimos com base em substantivos apropriados, juntamente com todas as citações apropriadas.

Essa preferência é especialmente importante, uma vez que algum uso de substantivos apropriados sempre será necessário — Q # segue a tradição definida por muitas linguagens clássicas, por exemplo, e refere-se a tipos de `Bool` em referência à lógica booliana, que é, por sua vez, nomeado em honra de George bool.
Alguns conceitos de Quantum da mesma forma são nomeados de maneira semelhante, incluindo o tipo de `Pauli` interno à linguagem Q #.
Ao minimizar o uso de substantivos apropriados em que esse uso não é essencial, reduzimos o impacto em que os nomes próprios não podem ser evitados de forma razoável.

# <a name="guidancetabguidance"></a>[Orientação](#tab/guidance) 

Sugerimos:

- Evite o uso de substantivos apropriados em nomes.

# <a name="examplestabexamples"></a>[Exemplos](#tab/examples)

***

### <a name="type-conversions"></a>Conversões de tipo ###

Como Q # é uma linguagem fortemente e de tipo estático, um valor de um tipo só pode ser usado como um valor de outro tipo usando uma chamada explícita para uma função de conversão de tipo.
Isso é diferente de linguagens que permitem valores para alterar tipos implicitamente (por exemplo: promoção de tipos) ou por meio de conversão.
Como resultado, as funções de conversão de tipo desempenham um papel importante no desenvolvimento de biblioteca Q # e compõem uma das decisões mais comumente encontradas sobre nomenclatura.
No entanto, observamos que, como as conversões de tipo são sempre _determinísticas_, elas podem ser escritas como funções e, portanto, se enquadram no Conselho acima.
Em particular, sugerimos que as funções de conversão de tipo nunca sejam nomeadas como verbos (por exemplo: `ConvertToX`) ou frases preposicionais Advérbio (`ToX`), mas devem ser nomeadas como frases preposicionais de adjetivo que indiquem os tipos de origem e de destino (`XAsY`).
Ao listar tipos de matriz em nomes de função de conversão de tipo, recomendamos o `Arr`abreviado.
Ao bloquear circunstâncias excepcionais, recomendamos que todas as funções de conversão de tipo sejam nomeadas usando `As` para que possam ser identificadas rapidamente.

# <a name="guidancetabguidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Se uma função converter um valor do tipo `X` em um valor do tipo `Y`, use o nome `AsY` ou `XAsY`.

# <a name="examplestabexamples"></a>[Exemplos](#tab/examples)

|   | Nome | Descrição |
|---|------|-------------|
| ☒ | <s>`ToDouble`</s> | A preposição "to" resulta em uma frase verbal, indicando uma operação e não uma função. |
| ☒ | <s>`AsDouble`</s> | O tipo de entrada não é claro do nome da função. |
| ☒ | <s>`PauliArrFromBoolArr`</s> | Os tipos de entrada e saída aparecem na ordem errada. |
| ☑ | `ResultArrAsBoolArr` | Os tipos de entrada e de saída são claros. |

***

### <a name="private-or-internal-names"></a>Nomes privados ou internos ###

Em muitos casos, um nome destina-se estritamente ao uso interno de uma biblioteca ou projeto e não é uma parte garantida da API oferecida por uma biblioteca.
É útil indicar claramente que esse é o caso ao nomear funções e operações para que dependências acidentais em código somente interno sejam tornadas óbvias.
Se uma operação ou função não for destinada ao uso direto, mas, em vez disso, deve ser usada por um chamado callable que age por aplicativo parcial, considere usar um nome começando com `_` para o callable que é parcialmente aplicado.

# <a name="guidancetabguidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Quando uma função, uma operação ou um tipo definido pelo usuário não faz parte da API pública para uma biblioteca ou programa do Q #, certifique-se de que seu nome comece com um sublinhado à esquerda (`_`).

# <a name="examplestabexamples"></a>[Exemplos](#tab/examples)

|   | Nome | Descrição |
|---|------|-------------|
| ☒ | <s>`ApplyDecomposedOperation_`</s> | O sublinhado `_` não deve aparecer no final do nome. |
| ☑ | `_ApplyDecomposedOperation` | O sublinhado `_` no início claramente indica que esta operação é apenas para uso interno. |

***

### <a name="variants"></a>Variantes ###

Embora essa limitação possa não persistir em versões futuras do Q #, ela é apresentada no momento em que, em geral, haverá grupos de operações ou funções relacionadas que são diferenciadas por quais transmissão functorsm suas entradas de suporte ou pelos tipos concretos de seus argumentos.
Esses grupos podem ser diferenciados usando o mesmo nome de raiz, seguidos por uma ou duas letras que indicam sua variante.

| Sufixo | Significado |
|--------|---------|
| `A` | Entrada esperada para dar suporte a `Adjoint` |
| `C` | Entrada esperada para dar suporte a `Controlled` |
| `CA` | Entrada esperada para dar suporte a `Controlled` e `Adjoint` |
| `I` | Entradas ou entradas são do tipo `Int` |
| `D` | Entradas ou entradas são do tipo `Double` |
| `L` | Entradas ou entradas são do tipo `BigInt` |

# <a name="guidancetabguidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Se uma função ou operação não estiver relacionada a quaisquer funções ou operações semelhantes pelos tipos e suporte functor de suas entradas, não use um sufixo.
- Se uma função ou operação estiver relacionada a quaisquer funções ou operações semelhantes pelos tipos e suporte functor de suas entradas, use sufixos como na tabela acima para distinguir variantes.

# <a name="examplestabexamples"></a>[Exemplos](#tab/examples)

***

### <a name="arguments-and-variables"></a>Argumentos e variáveis ###

Uma meta importante do código Q # para uma função ou operação é que ela seja facilmente lida e compreendida.
Da mesma forma, os nomes de entradas e argumentos de tipo devem comunicar como uma função ou um argumento será usado uma vez fornecido.


# <a name="guidancetabguidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Para todos os nomes de variáveis e de entrada, use `pascalCase` de preferência forte para `CamelCase`, `snake_case`ou `ANGRY_CASE`.
- Os nomes de entrada devem ser descritivos; Evite um ou dois nomes de letra sempre que possível.
- Operações e funções que aceitam exatamente um argumento de tipo devem indicar esse argumento de tipo por `T` quando sua função é óbvia.
- Se uma função ou operação usar vários argumentos de tipo, ou se a função de um argumento de tipo único não for óbvia, considere usar uma palavra em maiúscula curta precedida por `T` (por exemplo: `TOutput`) para cada tipo.
- Não incluir nomes de tipos em nomes de argumentos e variáveis; essas informações podem e devem ser fornecidas pelo seu ambiente de desenvolvimento.
- Denotar tipos escalares por seus nomes literais (`flagQubit`) e tipos de matriz por um plural (`measResults`).
  Para matrizes de qubits em particular, considere a possibilidade de indicar tais tipos por `Register` em que o nome se refere a uma sequência de qubits que estão fortemente relacionadas de alguma forma.
- As variáveis usadas como índices em matrizes devem começar com `idx` e devem ser singulares (por exemplo: `things[idxThing]`).
  Particularmente, evite usar nomes de variáveis de letra única como índices; Considere o uso de `idx` no mínimo.
- As variáveis usadas para manter comprimentos de matrizes devem começar com `n` e devem ser pluraled (por exemplo: `nThings`).

# <a name="examplestabexamples"></a>[Exemplos](#tab/examples)

***

### <a name="user-defined-type-named-items"></a>Tipos de itens nomeados definidos pelo usuário ###

Os itens nomeados em tipos definidos pelo usuário devem ser nomeados como `CamelCase`, mesmo na entrada para construtores UDT.
Isso ajuda a fazer com que os itens nomeados sejam claramente separados de referências a variáveis com escopo local ao usar a notação de acessador (por exemplo: `callable::Apply`) ou a notação de copiar e atualizar (`set arr w/= Data <- newData`).

# <a name="guidancetabguidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Os itens nomeados nos construtores UDT devem ser nomeados como `CamelCase`; ou seja, eles devem começar com uma letra maiúscula inicial.
- Os itens nomeados que são resolvidos para as operações devem ser nomeados como fases de verbo.
- Os itens nomeados que não são resolvidos para as operações devem ser nomeados como frases de substantivo.
- Para UDTs que encapsulam operações, um único item nomeado chamado `Apply` deve ser definido.

# <a name="examplestabexamples"></a>[Exemplos](#tab/examples)

|   | Snippet | Descrição |
|---|---------|-------------|
| ☑ | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | O nome `Apply` é uma frase verbal com formato `CamelCase`, sugerindo que o item nomeado é uma operação. |
| ☒ | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | Itens nomeados devem começar com uma letra maiúscula inicial. |
| ☒ | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | Itens nomeados que resolvem para funções devem ser nomeados como frases de substantivo, não como frases de verbo. |

***

## <a name="input-conventions"></a>Convenções de entrada ##

Quando um desenvolvedor chama uma operação ou função, as várias entradas para essa operação ou função devem ser especificadas em uma determinada ordem, aumentando a carga cognitiva que um desenvolvedor enfrenta para fazer uso de uma biblioteca.
Em particular, a tarefa de memorizar as ordens de entrada é, muitas vezes, uma distração da tarefa em questão: programando uma implementação de um algoritmo Quantum.
Embora o suporte a IDE avançado possa reduzir isso para uma grande extensão, o bom design e a adesão a Convenções comuns também podem ajudar a minimizar a carga cognitiva imposta por uma API.

Sempre que possível, pode ser útil reduzir o número de entradas esperado por uma operação ou função, de modo que a função de cada entrada seja mais óbvia imediatamente para os desenvolvedores que chamam essa operação ou função e para os desenvolvedores que lêem esse código mais tarde.
Especialmente quando não é possível ou razoável reduzir o número de argumentos para uma operação ou função, é importante ter uma ordenação consistente que minimize a surpresa que um usuário enfrenta ao prever a ordem das entradas.

Recomendamos que as convenções de ordenação de entrada derivem amplamente da reflexão do aplicativo parcial como uma generalização de currying f (x, y) ≡ f (x) (y).
Portanto, a aplicação parcial dos primeiros argumentos deve resultar em um callable que seja útil por si só, sempre que for razoável.
Seguindo esse princípio, considere o uso da seguinte ordem de argumentos:

- Argumentos clássicos não chamáveis, como ângulos, vetores de potências, etc.
- Argumentos que podem ser chamados (funções e argumentos).
  Se as funções e as operações forem executadas como argumentos, considere colocar operações após funções.
- As coleções foram acionadas por argumentos que podem ser chamados de uma maneira semelhante para `Map`, `Iter`, `Enumerate`e `Fold`.
- Argumentos qubit usados como controles.
- Argumentos qubit usados como destinos.

Considere uma operação `ApplyPhaseEstimationIteration` para uso na estimativa de fase que usa um ângulo e um Oracle, passa o ângulo para `Rz` modificado por uma matriz de fatores de dimensionamento diferentes e, em seguida, controla os aplicativos da Oracle.
Ordenamos as entradas para `ApplyPhaseEstimationIteration` da seguinte maneira:

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
Como um caso especial de minimizar a surpresa, algumas funções e operações imitam o comportamento do transmissão functors interno `Adjoint` e `Controlled`.
Por exemplo, `ControlledOnInt<'T>` tem `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`de tipo, de modo que `ControlledOnInt<Qubit[]>(5, _)` atua como o `Controlled` functor, mas na condição que o registro de controle representa o estado $ \ket{5} = \ket{101}$.
Portanto, um desenvolvedor espera que as entradas para `ControlledOnInt` coloquem o callable que está sendo transformado por último e que a operação resultante leve como sua entrada `(Qubit[], 'T)`---mesma ordem, conforme seguido pela saída do `Controlled` functor.

# <a name="guidancetabguidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Use ordenações de entrada consistentes com o uso de aplicativo parcial.
- Use ordenações de entrada consistentes com transmissão functors internas.
- Coloque todas as entradas clássicas antes de qualquer entrada de Quantum.

# <a name="examplestabexamples"></a>[Exemplos](#tab/examples)

***

## <a name="documentation-conventions"></a>Convenções de documentação ##

A linguagem Q # permite anexar documentação a operações, funções e tipos definidos pelo usuário por meio do uso de comentários de documentação especialmente formatados.
Indicado por barras triplas (`///`), esses comentários de documentação são documentos [de redução DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) pequeno, que podem ser usados para descrever a finalidade de cada operação, função e tipo definido pelo usuário, quais entradas cada espera e assim por diante.
O compilador fornecido com o kit de desenvolvimento Quantum extrai esses comentários e os utiliza para ajudar a documentar o tipo de documentação semelhante àquela em https://docs.microsoft.com/quantum.
Da mesma forma, o servidor de linguagem fornecido com o kit de desenvolvimento Quantum usa esses comentários para fornecer ajuda aos usuários quando eles passam o mouse sobre símbolos em seu código Q #.
Fazer uso de comentários de documentação pode ajudar os usuários a fazer sentido de código fornecendo uma referência útil para os detalhes que não são facilmente expressos usando as outras convenções deste documento.

<div class="nextstepaction">
    [Referência de sintaxe de comentário da documentação](xref:microsoft.quantum.language.statements#documentation-comments)
</div>

Para usar efetivamente essa funcionalidade para ajudar os usuários, é recomendável manter algumas coisas em mente ao escrever comentários de documentação.

# <a name="guidancetabguidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Cada função pública, operação e tipo definido pelo usuário deve ser imediatamente precedido por um comentário de documentação.
- No mínimo, cada comentário da documentação deve incluir as seguintes seções:
    - Resumo
    - Input
    - Saída (se aplicável)
- Verifique se todos os resumos têm duas frases ou menos. Se for necessário mais espaço, forneça uma seção `# Description` imediatamente após `# Summary` com detalhes completos.
- Quando for razoável, não inclua Math em resumos, pois nem todos os clientes dão suporte à notação TeX em resumos. Observe que, ao escrever documentos da Proseware (por exemplo, TeX ou de redução), pode ser preferível usar comprimentos de linha mais longos.
- Forneça todas as expressões matemáticas relevantes na seção `# Description`.
- Ao descrever as entradas, não repita os tipos de cada entrada, pois elas podem ser inferidas pelo compilador e risco para introduzir inconsistência.
- Forneça exemplos conforme apropriado, cada um em sua própria seção `# Example`.
- Descreva brevemente cada exemplo antes de listar o código.
- Cite todas as publicações acadêmicas relevantes (por exemplo: papéis, procedimentos, Postagens de blog e implementações alternativas) em uma seção `# References` como uma lista com marcadores de links.
- Verifique se, quando possível, todos os links de citação são de identificadores permanentes e imutáveis (DOIs ou números de arXiv com controle de versão).
- Quando uma operação ou função está relacionada a outras operações ou funções por variantes functor, liste outras variantes como marcadores na seção `# See Also`.
- Deixe uma linha de comentário em branco entre as seções de nível 1 (`/// #`), mas não deixe uma linha em branco entre as seções de nível 2 (`/// ##`).

# <a name="examplestabexamples"></a>[Exemplos](#tab/examples)

#### <a name=""></a>☑ ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a>Convenções de formatação ##

Além das sugestões anteriores, é útil ajudar a tornar o código mais legível possível para usar regras de formatação consistentes.
Essas regras de formatação por natureza tendem a ser, de certa forma, arbitrárias e com rigidez de estética pessoais.
No entanto, recomendamos manter um conjunto consistente de convenções de formatação dentro de um grupo de colaboradores e, especialmente, para projetos grandes do Q #, como o próprio kit de desenvolvimento do Quantum.
Essas regras podem ser aplicadas automaticamente usando a ferramenta de formatação integrada ao compilador Q #.

# <a name="guidancetabguidance"></a>[Orientação](#tab/guidance) 

Sugerimos:

- Use quatro espaços em vez de guias para portabilidade.
  Por exemplo, no VS Code:
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- Quebra de linha a 79 caracteres em que é razoável.
- Use espaços em volta de operadores binários.
- Use espaços em qualquer lado dos dois-pontos usados para anotações de tipo.
- Use um único espaço após as vírgulas usadas em literais de matriz e de tupla (por exemplo: em entradas para funções e operações).
- Não use espaços após a função, a operação ou os nomes UDT ou depois da `@` em declarações de atributo.
- Cada declaração de atributo deve estar em sua própria linha.

# <a name="examplestabexamples"></a>[Exemplos](#tab/examples)

|   | Snippet | Descrição |
|---|---------|-------------|
| ☒ | <s>`2+3`</s> | Use espaços em volta de operadores binários. |
| ☒ | <s>`target:Qubit`</s> | Use espaços em volta de dois-pontos de anotação de tipo. |
| ☑ | `Example(a, b, c)` | Os itens na tupla de entrada têm o espaçamento correto para facilitar a leitura. |
| ☒ | <s>`Example (a, b, c)`</s> | Os espaços devem ser suprimidos após os nomes de função, operação ou UDT. |

***

