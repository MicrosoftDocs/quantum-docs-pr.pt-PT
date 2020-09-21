---
title: Q#Guia de estilo da Microsoft
description: Aprenda as convenções de nomeação, entrada, documentação e formatação para Q# programas e bibliotecas.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
no-loc:
- Q#
- $$v
ms.openlocfilehash: fef3cea1c11e4fef49ddbf63adb34e07675049d2
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834198"
---
# <a name="no-locq-style-guide"></a>Q# Guia de estilo #
## <a name="general-conventions"></a>Convenções Gerais ##

As convenções sugeridas neste guia destinam-se a ajudar a tornar os programas e bibliotecas escritos Q# de forma mais fácil de ler e compreender.

## <a name="guidance"></a>Orientação

Sugerimos:

- Nunca ignore uma convenção a menos que o faça intencionalmente para fornecer um código mais legível e compreensível para os seus utilizadores.

## <a name="naming-conventions"></a>Convenções de Nomeação ##

Ao oferecermos o Kit de Desenvolvimento Quântico, esforçamo-nos por nomes de funções e de operação que ajudam os desenvolvedores quânticos a escrever programas que são fáceis de ler e que minimizam a surpresa.
Uma parte importante disso é que, quando escolhemos nomes para funções, operações e tipos, estamos a estabelecer o *vocabulário* que os programadores usam para expressar conceitos quânticos; com as nossas escolhas, ou ajudamos ou os dificultamos no seu esforço para comunicar claramente.
Isto coloca-nos a responsabilidade de garantir que os nomes que introduzimos ofereçam clareza em vez de obscuridade.
Nesta secção, detalhamos como cumprimos esta obrigação em termos de orientação explícita que nos ajuda a fazer o melhor pela comunidade de Q# desenvolvimento.

### <a name="operations-and-functions"></a>Operações e Funções ###

Uma das primeiras coisas que um nome deve estabelecer é se um dado símbolo representa uma função ou uma operação.
A diferença entre funções e operações é fundamental para entender como um bloco de código se comporta.
Para comunicar a distinção entre funções e operações aos utilizadores, contamos com os Q# modelos de operações quânticas através da utilização de efeitos secundários.
Isto é, uma operação *faz alguma* coisa.

Em contraste, as funções descrevem as relações matemáticas entre dados.
A expressão `Sin(PI() / 2.0)` *é* `1.0` , e não implica nada sobre o estado de um programa ou seus qubits.

Resumindo, as operações fazem as coisas enquanto as funções são coisas.
Esta distinção sugere que nomeamos as operações como verbos e funções como substantivos.

> [!NOTE]
> Quando um tipo definido pelo utilizador é declarado, uma nova função que constrói instâncias desse tipo é implicitamente definida ao mesmo tempo.
> Nessa perspetiva, os tipos definidos pelo utilizador devem ser nomeados como substantivos para que tanto o tipo em si como a função de construtor tenham nomes consistentes.

Quando razoável, certifique-se de que os nomes de operação começam com verbos que indicam claramente o efeito da operação.
Por exemplo:

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

Um caso que merece uma menção especial é quando uma operação toma outra operação como entrada e chama-a.
Nestes casos, as medidas tomadas pela operação de entrada não são claras quando a operação exterior é definida, de modo a que o verbo certo não seja imediatamente claro.
Recomendamos o `Apply` verbo, como em `ApplyIf` , e `ApplyToEach` `ApplyToFirst` .
Outros verbos podem ser úteis também neste caso, como em `IterateThroughCartesianPower` .

| Verbo | Efeito Esperado |
| ---- | ------ |
| Aplicar | Uma operação fornecida como entrada é chamada |
| Declarar | Uma hipótese sobre o resultado de uma possível medição quântica é verificada por um simulador |
| Obter estimativa | Um valor clássico é devolvido, representando uma estimativa extraída de uma ou mais medições |
| Medir | Uma medição quântica é realizada, e o seu resultado é devolvido ao utilizador |
| Preparação | Um dado registo de qubits é inicializado num determinado estado |
| Sample | Um valor clássico é devolvido aleatoriamente de alguma distribuição |

Para funções, sugerimos evitar a utilização de verbos a favor de substantivos comuns (ver orientação sobre substantivos adequados abaixo) ou adjetivos:

- `ConstantArray`
- `Head`
- `LookupFunction`

Em particular, em quase todos os casos, sugerimos usar os particípios passados, quando apropriado, para indicar que um nome de função está fortemente ligado a uma ação ou efeito colateral em outros lugares de um programa quântico.
Por exemplo,  `ControlledOnInt` usa a forma part participle do verbo "control" para indicar que a função age como um adjetivo para modificar o seu argumento.
Este nome tem o benefício adicional de combinar a semântica do `Controlled` functor incorporado, como discutido mais abaixo.
Da mesma forma, _os substantivos de agente_ podem ser usados para construir funções e nomes de UDT a partir de nomes de operação, como no caso do nome para uma `Encoder` UDT que está fortemente associada a `Encode` .

# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Utilize verbos para nomes de operação.
- Utilize substantivos ou adjetivos para nomes de funções.
- Utilize substantivos para tipos e atributos definidos pelo utilizador.
- Para todos os nomes chamados, use `CamelCase` em forte preferência a , ou `pascalCase` `snake_case` `ANGRY_CASE` . Em particular, certifique-se de que os nomes de chamadas começam com letras maiúsculas.
- Para todas as variáveis locais, utilize `pascalCase` em forte `CamelCase` `snake_case` preferência, ou `ANGRY_CASE` . Em particular, certifique-se de que as variáveis locais começam com letras minúsculas.
- Evite a utilização de sublinhados `_` em nomes de função e operação; onde são necessários níveis adicionais de hierarquia, utilize espaços de nome e pseudónimos de espaço de nome.

# <a name="examples"></a>[Exemplos](#tab/examples)

| &nbsp;  | Nome | Descrição |
|---|------|-------------|
| ☑ | `operation ReflectAboutStart` | Utilização clara de um verbo ("refletir") para indicar o efeito da operação. |
| ☒ | <s>`operation XRotation`</s> | A utilização da frase substantivo sugere função, em vez de funcionar. |
| ☒ | <s>`operation search_oracle`</s> | Uso de `snake_case` Q# notação contravenes. |
| ☒ | <s>`operation Search_Oracle`</s> | A utilização de sublinhas internas para operar nome contravenções Q# notação. |
| ☑ | `function StatePreparationOracle` | A utilização da frase substantivo sugere que a função devolve uma operação. |
| ☑ | `function EqualityFact` | Uso claro do substantivo ("facto") para indicar que esta é uma função, enquanto o adjetivo. |
| ☒ | <s>`function GetRotationAngles`</s> | A utilização de verbo ("get") sugere que se trata de uma operação. |
| ☑ | `newtype GeneratorTerm` | O uso da frase substantivo refere-se claramente ao resultado de chamar o construtor UDT. |
| ☒ | <s>`@Attribute() newtype RunOnce()`</s> | A utilização da frase verbo sugere que o construtor UDT é uma operação. |
| ☑ | `@Attribute() newtype Deprecated(Reason : String)` | A utilização da frase substantivo comunica o uso do atributo. |

***

### <a name="entry-points"></a>Pontos de Entrada

Ao definir um ponto de entrada num Q# programa, o Q# compilador reconhece o [ `@EntryPoint()` atributo](xref:microsoft.quantum.core.entrypoint) exigindo que os pontos de entrada tenham um nome específico (por exemplo: `main` , ou `Main` `__main__` ).
Ou seja, do ponto de vista de um desenvolvedor, os pontos de Q# entrada são operações ordinárias anotadas com `@EntryPoint()` .
Além disso, Q# os pontos de entrada podem ser pontos de entrada para toda uma aplicação (por exemplo, em Q# programas executáveis autónomos), ou podem ser uma interface entre um Q# programa e o programa anfitrião para uma aplicação (ou seja, quando se utiliza Q# com Python ou .NET), de modo que o nome "principal" pode ser enganador quando aplicado a um Q# ponto de entrada.

Sugerimos a utilização de pontos de nomeação para refletir a utilização do `@EntryPoint()` atributo utilizando os conselhos gerais para as operações de nomeação acima enumeradas.


# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Não nomeie as operações de ponto de entrada como "principais".
- Nomeie as operações de ponto de entrada como operações normais.

# <a name="examples"></a>[Exemplos](#tab/examples)

| &nbsp;  | Nome | Descrição |
|---|------|-------------|
| ☑ | `@EntryPoint() operation RunSimulation` | Comunica claramente o propósito do ponto de entrada através do nome de operação. |
| ☒ | <s>`@EntryPoint() operation Main`</s> | O uso não `Main` comunica claramente o propósito do ponto de entrada, e é redundante com `@EntryPoint()` atributo. |

***

### <a name="shorthand-and-abbreviations"></a>Abreviaturas e Abreviaturas ###

Apesar dos conselhos acima, existem muitas formas de abreviatura que vêem o uso comum e pervasivo na computação quântica.
Sugerimos a utilização de abreviaturas existentes e comuns onde ela existe, especialmente para operações intrínsecas ao funcionamento de uma máquina-alvo.
Por exemplo, escolhemos o nome `X` em vez de , e em vez de `ApplyX` `Rz` `RotateAboutZ` .
Ao utilizar esta abreviatura, os nomes de funcionamento devem ser todos maiúsculas (por exemplo: `MAJ` ).

É necessário ter algum cuidado na aplicação desta convenção no caso de siglas e inicialismos comumente usados, tais como "QFT" para "transformação quântica de Fourier".
Sugerimos que se seguem as convenções gerais .NET para a utilização de siglas e inicialismos em nomes completos, que prevêem que:

- siglas e inicialismos de duas letras são nomeados em maiúscula (por exemplo: `BE` para "big-endian"),
- todas as siglas e inicialismos mais longos são nomeados `CamelCase` em (por exemplo: `Qft` para "quantum Fourier transform")

Assim, uma operação de implementação do QFT poderia ser chamada `QFT` de abreviatura, ou escrita como `ApplyQft` .

Para operações e funções particularmente utilizadas, pode ser desejável fornecer um nome abreviado como pseudónimo para _uma_ forma mais longa:

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Considere nomes de abreviação geralmente aceites e amplamente utilizados quando apropriado.
- Utilize maiúsculas para abreviaturas.
- Utilize maiúsculas para siglas e inicialismos curtos (duas letras).
- Utilize `CamelCase` para siglas e inicialismos mais longos (três ou mais letras).

# <a name="examples"></a>[Exemplos](#tab/examples)

| &nbsp;   | Nome | Descrição |
|---|------|-------------|
| ☑ | `X` | Abreviatura bem entendida para "aplicar uma transformação de $X$" |
| ☑ | `CNOT` | Abreviatura bem entendida para "controlled-NOT" |
| ☒ | <s>`Cnot`</s> | Abreviatura não deve estar dentro `CamelCase` . |
| ☑ | `ApplyQft` | O inicialismo comum "QFT" aparece como parte de um nome de longa forma. |
| ☑ | `QFT` | O inicialismo comum "QFT" aparece como parte de um nome abreviado. |



***


### <a name="proper-nouns-in-names"></a>Substantivos adequados em nomes ###

Enquanto na física é comum nomear as coisas depois da primeira pessoa a publicar sobre elas, a maioria dos não-físicos não estão familiarizados com os nomes de todos e toda a história.
Confiar demasiado na nomeação de convenções da física pode, assim, criar uma barreira substancial à entrada, uma vez que os utilizadores de outras origens devem aprender um grande número de nomes aparentemente opacos para utilizar operações e conceitos comuns.
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
Assim, recomendamos que, sempre que sejam razoáveis, substantivos comuns que descrevam um conceito sejam adotados em forte preferência aos substantivos adequados que descrevem a história da publicação de um conceito.
A título particular, as operações SWAP e NÃO duplamente controladas são muitas vezes chamadas de operações "Fredkin" e "Toffoli" na literatura académica, mas são identificadas Q# principalmente como `CSWAP` e `CCNOT` .
Em ambos os casos, os comentários da documentação da API fornecem nomes sinónimos baseados em substantivos adequados, juntamente com todas as citações apropriadas.

Esta preferência é especialmente importante dado que algum uso de substantivos adequados será sempre necessário - Q# segue a tradição definida por muitas línguas clássicas, por exemplo, e refere-se a `Bool` tipos de referência à lógica booleana, que por sua vez é nomeado em homenagem a George Boole.
Alguns conceitos quânticos são igualmente nomeados de forma semelhante, incluindo o `Pauli` tipo incorporado à Q# linguagem.
Ao minimizar o uso de substantivos adequados onde tal utilização não é essencial, reduzimos o impacto onde os substantivos adequados não podem ser razoavelmente evitados.

# <a name="guidance"></a>[Orientação](#tab/guidance) 

Sugerimos:

- Evite a utilização de substantivos adequados em nomes.

# <a name="examples"></a>[Exemplos](#tab/examples)

***

### <a name="type-conversions"></a>Conversões de tipo ###

Uma vez Q# que é uma linguagem forte e estática, um valor de um tipo só pode ser usado como um valor de outro tipo usando uma chamada explícita para uma função de conversão de tipo.
Isto contrasta com as línguas que permitem que os valores mudem os tipos implicitamente (por exemplo: promoção do tipo), ou através do casting.
Como resultado, as funções de conversão de tipo desempenham um papel importante no Q# desenvolvimento da biblioteca, e compreendem uma das decisões mais comumente encontradas sobre o nome.
Notamos, no entanto, que como as conversões de tipo são sempre _determinísticas,_ podem ser escritas como funções e, portanto, enquadrar-se nos conselhos acima referidos.
Em particular, sugerimos que as funções de conversão do tipo nunca devem ser nomeadas como verbos (por exemplo: `ConvertToX` ) ou frases pré-posicionais adverb `ToX` (), mas devem ser nomeadas como frases préposicionais adjetivas que indicam os tipos de origem e destino `XAsY` ().
Ao listar tipos de matrizes em nomes de funções de conversão de tipo, recomendamos a abreviatura `Arr` .
Salvo circunstâncias excecionais, recomendamos que todas as funções de conversão do tipo sejam nomeadas utilizando `As` para que possam ser rapidamente identificadas.

# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Se uma função converter um valor do tipo `X` para um valor do `Y` tipo, utilize o nome ou `AsY` `XAsY` .

# <a name="examples"></a>[Exemplos](#tab/examples)

| &nbsp;   | Nome | Descrição |
|---|------|-------------|
| ☒ | <s>`ToDouble`</s> | A preposição "a" resulta numa frase verbo, indicando uma operação e não uma função. |
| ☒ | <s>`AsDouble`</s> | O tipo de entrada não é claro a partir do nome da função. |
| ☒ | <s>`PauliArrFromBoolArr`</s> | Os tipos de entrada e saída aparecem na ordem errada. |
| ☑ | `ResultArrAsBoolArr` | Tanto os tipos de entrada como os tipos de saída são claros. |

***

### <a name="private-or-internal-names"></a>Nomes Privados ou Internos ###

Em muitos casos, um nome destina-se estritamente a ser utilizado internamente numa biblioteca ou projeto, e não é uma parte garantida da API oferecida por uma biblioteca.
É útil indicar claramente que é esse o caso quando se nomeia funções e operações, de modo a que as dependências acidentais do código interno sejam tornadas óbvias.
Se uma operação ou função não for destinada a uso direto, mas sim a utilização de uma chamada correspondente que aja por aplicação parcial, considere utilizar um nome que comece pela `internal` palavra-chave para a chamada que é parcialmente aplicada.

# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Quando uma função, operação ou tipo definido pelo utilizador não faz parte da API pública para uma Q# biblioteca ou programa, certifique-se de que está marcada como interna colocando a `internal` palavra-chave antes do `function` , ou `operation` `newtype` declaração.

# <a name="examples"></a>[Exemplos](#tab/examples)

| &nbsp;  | Nome | Descrição |
|---|------|-------------|
| ☒ | <s>`operation _ApplyDecomposedOperation`</s> | Não utilize um sublinhado `_` que indique que esta operação é apenas para uso interno. |
| ☑ | `internal operation ApplyDecomposedOperation` | A `internal` palavra-chave no início indica claramente que esta operação é apenas para uso interno. |

***
### <a name="variants"></a>Variantes ###

Embora esta limitação possa não persistir em futuras versões de Q# , é atualmente o caso de existirem frequentemente grupos de operações ou funções relacionadas que se distinguem pelo qual os funtores suportam os seus inputs, ou pelos tipos concretos dos seus argumentos.
Estes grupos podem ser distinguidos usando o mesmo nome de raiz, seguidos por uma ou duas letras que indicam a sua variante.

| Sufixo | Significado |
|--------|---------|
| `A` | Entrada esperada para apoiar `Adjoint` |
| `C` | Entrada esperada para apoiar `Controlled` |
| `CA` | Entrada esperada para apoiar `Controlled` e `Adjoint` |
| `I` | Entradas ou entradas são do tipo `Int` |
| `D` | Entradas ou entradas são do tipo `Double` |
| `L` | Entradas ou entradas são do tipo `BigInt` |

# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Se uma função ou funcionamento não estiver relacionado com funções ou operações semelhantes pelos tipos e suporte functor das suas entradas, não utilize um sufixo.
- Se uma função ou funcionamento estiver relacionado com quaisquer funções ou operações semelhantes pelos tipos e suporte functor das suas entradas, utilize sufixos como no quadro acima para distinguir variantes.

# <a name="examples"></a>[Exemplos](#tab/examples)

***

### <a name="arguments-and-variables"></a>Argumentos e Variáveis ###

Um objectivo-chave do Q# código para uma função ou operação é que seja facilmente lido e compreendido.
Da mesma forma, os nomes das entradas e dos argumentos de tipo devem comunicar como uma função ou argumento será usado uma vez fornecido.


# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Para todos os nomes variáveis e de entrada, utilize `pascalCase` em forte `CamelCase` `snake_case` preferência, ou `ANGRY_CASE` .
- Os nomes de entrada devem ser descritivos; evitar um ou dois nomes de letras sempre que possível.
- As operações e funções que aceitam exatamente um argumento de tipo devem denotar esse argumento de tipo `T` quando o seu papel é óbvio.
- Se uma função ou operação tiver múltiplos argumentos de tipo, ou se o papel de um único argumento de tipo não for óbvio, considere a utilização de uma palavra maiúscula curta prefaciada por `T` (por exemplo: `TOutput` ) para cada tipo.
- Não inclua nomes de tipo em argumentos e nomes variáveis; esta informação pode e deve ser fornecida pelo seu ambiente de desenvolvimento.
- Denotar tipos de escalar pelos seus nomes `flagQubit` literais () e tipos de matrizes por um plural ( `measResults` ).
  Para matrizes de qubits em particular, considere denotar tais tipos por `Register` onde o nome se refere a uma sequência de qubits que estão intimamente relacionados de alguma forma.
- As variáveis utilizadas como índices em matrizes devem começar `idx` e devem ser singulares (por exemplo: `things[idxThing]` ).
  Em especial, evitem utilizar nomes variáveis de letra única como índices; considerar a `idx` utilização no mínimo.
- As variáveis utilizadas para manter os comprimentos das matrizes devem começar `n` e devem ser pluralizadas (por exemplo: `nThings` ).

# <a name="examples"></a>[Exemplos](#tab/examples)

***

### <a name="user-defined-type-named-items"></a>Itens nomeados para o tipo definido pelo utilizador ###

Os itens nomeados em tipos definidos pelo utilizador devem ser nomeados como `CamelCase` , mesmo na entrada para os construtores UDT.
Isto ajuda a separar claramente os itens nomeados de referências a variáveis de âmbito local quando se utilizam notações acessórias (por exemplo: `callable::Apply` ) ou notação de cópia e atualização ( `set arr w/= Data <- newData` ).

# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Os itens nomeados nos construtores UDT devem ser nomeados como `CamelCase` ; ou seja, devem começar com uma maiúscula inicial.
- Os itens nomeados que se resolvem para as operações devem ser nomeados como fases de verbo.
- Os itens nomeados que não se resolvem para operações devem ser nomeados como frases substantivos.
- Para as UDTs que envolvem operações, deve ser definido um único item chamado. `Apply`

# <a name="examples"></a>[Exemplos](#tab/examples)

| &nbsp;  | Fragmento de código | Descrição |
|---|---------|-------------|
| ☑ | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | O nome `Apply` é uma `CamelCase` frase verbo formatada, sugerindo que o item nomeado é uma operação. |
| ☒ | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | Os itens nomeados devem começar com uma letra maiúscula inicial. |
| ☒ | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | Os itens nomeados que se resolvem para funções devem ser nomeados como frases substantivos, e não como frases verbos. |

***

## <a name="input-conventions"></a>Convenções de Entrada ##

Quando um desenvolvedor chama para uma operação ou função, as várias entradas para essa operação ou função devem ser especificadas numa determinada ordem, aumentando a carga cognitiva que um desenvolvedor enfrenta para fazer uso de uma biblioteca.
Em particular, a tarefa de lembrar as encomendas de entrada é muitas vezes uma distração da tarefa em questão: programar uma implementação de um algoritmo quântico.
Embora o rico suporte IDE possa mitigar isso em grande medida, o bom design e a adesão a convenções comuns também podem ajudar a minimizar a carga cognitiva imposta por uma API.

Sempre que possível, pode ser útil reduzir o número de entradas esperadas por uma operação ou função, de modo que o papel de cada entrada seja mais imediatamente óbvio tanto para os desenvolvedores que ligam para essa operação ou função, como para os desenvolvedores lerem esse código mais tarde.
Especialmente quando não é possível ou razoável reduzir o número de argumentos para uma operação ou função, é importante ter uma ordem consistente que minimize a surpresa que um utilizador enfrenta ao prever a ordem de entradas.

Recomendamos uma convenção de pedido de entrada que deriva em grande parte do pensamento da aplicação parcial como uma generalização do currying f(x, y) ≡ f(x)(y).
Assim, a aplicação parcial dos primeiros argumentos deverá resultar numa chamada que seja útil por si só sempre que isso seja razoável.
Seguindo este princípio, considere a utilização da seguinte ordem de argumentos:

- Argumentos clássicos não-chamados, tais como ângulos, vetores de poderes, etc.
- Argumentos insutilizáveis (funções e argumentos).
  Se ambas as funções e operações forem tomadas como argumentos, considere a colocação de operações após funções.
- As coleções atuavam com argumentos inutilizáveis de forma semelhante `Map` `Iter` a, `Enumerate` e `Fold` .
- Argumentos qubit usados como controlos.
- Argumentos qubit usados como alvos.

Considere uma operação `ApplyPhaseEstimationIteration` para utilização na estimativa de fase que toma um ângulo e um oráculo, passa o ângulo para `Rz` modificado por uma série de diferentes fatores de escala, e depois controla as aplicações do oráculo.
Ordenaríamos que os inputs fossem `ApplyPhaseEstimationIteration` da seguinte forma:

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
Como caso especial de minimização da surpresa, algumas funções e operações imitam o comportamento dos functores embutidos `Adjoint` e `Controlled` .
Por exemplo, `ControlledOnInt<'T>` tem tipo , tal que age como o `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` `ControlledOnInt<Qubit[]>(5, _)` `Controlled` functor, mas na condição de o registo de controlo representar o estado $\ket {5} = \ket {101} $.
Assim, um desenvolvedor espera que as entradas para `ControlledOnInt` colocar o ser calável em último lugar, e que a operação resultante toma como sua entrada `(Qubit[], 'T)` --- a mesma ordem seguida pela saída do `Controlled` functor.

# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Utilize pedidos de entrada consistentes com a utilização de aplicações parciais.
- Utilize pedidos de entrada consistentes com functors incorporados.
- Coloque todas as entradas clássicas antes de qualquer entrada quântica.

# <a name="examples"></a>[Exemplos](#tab/examples)

***

## <a name="documentation-conventions"></a>Convenções de Documentação ##

O Q# idioma permite anexar documentação a operações, funções e tipos definidos pelo utilizador através da utilização de comentários de documentação especialmente formatados.
Denotados por triplo-slashes ( `///` ), estes comentários documentais são pequenos documentos [markdown com sabor DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) que podem ser usados para descrever o propósito de cada operação, função e tipo definido pelo utilizador, o que cada um espera, e assim por diante.
O compilador fornecido com o Kit de Desenvolvimento Quântico extrai estes comentários e usa-os para ajudar a tipet documentação semelhante à da https://docs.microsoft.com/quantum .
Da mesma forma, o servidor de idiomas fornecido com o Kit de Desenvolvimento Quântico utiliza estes comentários para fornecer ajuda aos utilizadores quando pairam sobre símbolos no seu Q# código.
Fazer uso de comentários documentais pode, assim, ajudar os utilizadores a dar sentido ao código, fornecendo uma referência útil para detalhes que não são facilmente expressos usando as outras convenções neste documento.

> [!div class="nextstepaction"]
> [Referência de sintaxe de comentário de documentação](xref:microsoft.quantum.guide.filestructure#documentation-comments).

Para utilizar eficazmente esta funcionalidade para ajudar os utilizadores, recomendamos ter algumas coisas em mente enquanto escreve comentários de documentação.

# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Cada função pública, operação e tipo definido pelo utilizador devem ser imediatamente precedidos por um comentário de documentação.
- No mínimo, cada comentário de documentação deve incluir as seguintes secções:
    - Resumo
    - Entrada
    - Saída (se aplicável)
- Certifique-se de que todos os resumos são duas frases ou menos. Se for necessário mais espaço, forneça uma `# Description` secção imediatamente a seguir com todos os `# Summary` detalhes.
- Quando razoável, não inclua matemática em resumos, uma vez que nem todos os clientes suportam a notação TeX em resumos. Note que ao escrever documentos em prosa (por exemplo, TeX ou Markdown), pode ser preferível utilizar comprimentos de linha mais longos.
- Fornecer todas as expressões matemáticas relevantes na `# Description` secção.
- Ao descrever as entradas, não repita os tipos de cada entrada, uma vez que estes podem ser deduzidos pelo compilador e corre o risco de introduzir inconsistência.
- Fornecer exemplos conforme apropriado, cada um na sua própria `# Example` secção.
- Descreva brevemente cada exemplo antes de listar o código.
- Cite todas as publicações académicas relevantes (por exemplo: papéis, procedimentos, posts de blog e implementações alternativas) numa `# References` secção como uma lista de links.
- Certifique-se de que, sempre que possível, todas as ligações de citação são para identificadores permanentes e imutáveis (DOIs ou números arXiv em versão).
- Quando uma operação ou função estiver relacionada com outras operações ou funções por variantes do functor, liste outras variantes como balas na `# See Also` secção.
- Deixe uma linha de comentário em branco entre as secções de nível 1 ( `/// #` ), mas não deixe uma linha em branco entre as secções de nível 2 ( `/// ##` ).

# <a name="examples"></a>[Exemplos](#tab/examples)

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

## <a name="formatting-conventions"></a>Convenções de Formatação ##

Além das sugestões anteriores, é útil ajudar a tornar o código o mais legível possível para usar regras de formatação consistentes.
Tais regras de formatação por natureza tendem a ser um pouco arbitrárias e fortemente à altura da estética pessoal.
No entanto, recomendamos a manutenção de um conjunto consistente de convenções de formatação dentro de um grupo de colaboradores, e especialmente para grandes Q# projetos como o próprio Kit de Desenvolvimento Quântico.
Estas regras podem ser aplicadas automaticamente utilizando a ferramenta de formatação integrada com o Q# compilador.

# <a name="guidance"></a>[Orientação](#tab/guidance) 

Sugerimos:

- Utilize quatro espaços em vez de separadores para portabilidade.
  Por exemplo, no Código VS:
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- Embrulho de linha em 79 caracteres onde razoável.
- Use espaços em torno de operadores binários.
- Utilize espaços em ambos os lados dos cólons utilizados para anotações de tipo.
- Utilize um único espaço após vírgulas utilizadas em matrizes e tuple literais (por exemplo: nas entradas para funções e operações).
- Não utilize espaços após função, funcionamento ou nomes UDT, ou após as `@` declarações de atributos.
- Cada declaração de atributos deve estar na sua própria linha.

# <a name="examples"></a>[Exemplos](#tab/examples)

| &nbsp; | Fragmento de código | Descrição |
|---|---------|-------------|
| ☒ | <s>`2+3`</s> | Use espaços em torno de operadores binários. |
| ☒ | <s>`target:Qubit`</s> | Use espaços em torno de cólons de anotação tipo. |
| ☑ | `Example(a, b, c)` | Os itens na entrada são corretamente espaçados para a legibilidade. |
| ☒ | <s>`Example (a, b, c)`</s> | Os espaços devem ser suprimidos após a função, o funcionamento ou os nomes de UDT. |

***
