---
title: Guia de estilo Microsoft Q#
description: Conheça as convenções de nomeação, entrada, documentação e formatação para programas e bibliotecas Q# .
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 3c8e432378ec563a197a5b87000c3e90cadb8e18
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907448"
---
# <a name="q-style-guide"></a>Guia de estilo Q# #
## <a name="general-conventions"></a>Convenções Gerais ##

As convenções sugeridas neste guia destinam-se a ajudar a tornar os programas e bibliotecas escritos em Q# mais fáceis de ler e entender.

## <a name="guidance"></a>Orientação

Sugerimos:

- Nunca ignore uma convenção a menos que o faça intencionalmente para fornecer um código mais legível e compreensível para os seus utilizadores.

## <a name="naming-conventions"></a>Convenções de Nomeação ##

Ao oferecer o Kit de Desenvolvimento Quântico, esforçamo-nos por nomes de função e operação que ajudam os desenvolvedores quânticos a escrever programas que são fáceis de ler e que minimizam a surpresa.
Uma parte importante disso é que, quando escolhemos nomes para funções, operações e tipos, estamos a estabelecer o *vocabulário* que os programadores usam para expressar conceitos quânticos; com as nossas escolhas, ou ajudamos ou os dificultamos no seu esforço para comunicar claramente.
Isto coloca-nos a responsabilidade de nos assegurarmos de que os nomes que introduzimos ofereçam clareza em vez de obscuridade.
Nesta secção, detalhamos como cumprimos esta obrigação em termos de orientação explícita que nos ajuda a fazer o melhor pela comunidade de desenvolvimento Q#.

### <a name="operations-and-functions"></a>Operações e Funções ###

Uma das primeiras coisas que um nome deve estabelecer é se um determinado símbolo representa uma função ou uma operação.
A diferença entre funções e operações é fundamental para entender como um bloco de código se comporta.
Para comunicar a distinção entre funções e operações aos utilizadores, contamos com as operações quânticas dos modelos Q# através da utilização de efeitos secundários.
Isto é, uma operação *faz* alguma coisa.

Em contraste, as funções descrevem as relações matemáticas entre os dados.
A expressão `Sin(PI() / 2.0)` *é* `1.0`, e não implica nada sobre o estado de um programa ou os seus qubits.

Resumindo, as operações fazem as coisas enquanto as funções são coisas.
Esta distinção sugere que nomeamos as operações como verbos e funciona como substantivos.

> [!NOTE]
> Quando um tipo definido pelo utilizador é declarado, uma nova função que constrói instâncias desse tipo é implicitamente definida ao mesmo tempo.
> Nessa perspetiva, os tipos definidos pelo utilizador devem ser nomeados como substantivos para que tanto o tipo como a função do construtor tenham nomes consistentes.

Se for razoável, certifique-se de que os nomes da operação começam com verbos que indiquem claramente o efeito tomado pela operação.
Por exemplo:

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

Um caso que merece uma menção especial é quando uma operação toma outra operação como entrada e chama-a.
Nesses casos, as medidas tomadas pela operação de entrada não são claras quando a operação externa é definida, de modo a que o verbo direito não seja imediatamente claro.
Recomendamos o verbo `Apply`, como em `ApplyIf`, `ApplyToEach`e `ApplyToFirst`.
Outros verbos também podem ser úteis neste caso, assim como em `IterateThroughCartesianPower`.

| Verbo | Efeito Esperado |
| ---- | ------ |
| Aplicar | Uma operação fornecida como entrada é chamada |
| Declarar | Uma hipótese sobre o resultado de uma possível medição quântica é verificada por um simulador |
| Estimativa | Um valor clássico é devolvido, representando uma estimativa extraída de uma ou mais medidas |
| Medir | Uma medição quântica é realizada, e o seu resultado é devolvido ao utilizador |
| Preparação | Um determinado registo de qubits é inicializado num determinado estado |
| Sample | Um valor clássico é devolvido aleatoriamente de alguma distribuição |

Para funções, sugerimos evitar a utilização de verbos a favor de substantivos comuns (ver orientação sobre substantivos adequados abaixo) ou adjetivos:

- `ConstantArray`
- `Head`
- `LookupFunction`

Em particular, em quase todos os casos, sugerimos a utilização de particípios passados, sempre que apropriado, para indicar que um nome de função está fortemente ligado a uma ação ou efeito colateral em outros lugares de um programa quântico.
Por exemplo, `ControlledOnInt` usa a parte do "controlo" do verbo para indicar que a função funciona como um adjetivo para modificar o seu argumento.
Este nome tem o benefício adicional de combinar a semântica do functor `Controlled` embutido, como discutido mais abaixo.
Da mesma forma, _os substantivos_ de agente podem ser usados para construir nomes de funções e UDT a partir de nomes de operação, como no caso do nome `Encoder` para um UDT fortemente associado com `Encode`.

# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Utilize verbos para nomes de operação.
- Utilize substantivos ou adjetivos para nomes de funções.
- Utilize substantivos para tipos e atributos definidos pelo utilizador.
- Para todos os nomes insensíveis, utilize `CamelCase` em forte preferência por `pascalCase`, `snake_case`ou `ANGRY_CASE`. Em particular, certifique-se de que os nomes insensíveis começam com letras maiúsculas.
- Para todas as variáveis locais, utilize `pascalCase` em forte preferência por `CamelCase`, `snake_case`ou `ANGRY_CASE`. Em particular, certifique-se de que as variáveis locais começam com letras minúsculas.
- Evitar a utilização de sublinhados `_` em nomes de funções e funcionamento; onde forem necessários níveis adicionais de hierarquia, utilize espaços de nome e pseudónimos de espaço de nome.

# <a name="examples"></a>[Exemplos](#tab/examples)

|   | Nome | Descrição |
|---|------|-------------|
| ☑ | `operation ReflectAboutStart` | Utilização clara de um verbo ("refletir") para indicar o efeito da operação. |
| ☒ | <s>`operation XRotation`</s> | O uso da frase do substantivo sugere função, em vez de funcionar. |
| ☒ | <s>`operation search_oracle`</s> | O uso de `snake_case` viola a notação Q#. |
| ☒ | <s>`operation Search_Oracle`</s> | O uso de sublinhados internos para o nome de operação viola a notação Q#. |
| ☑ | `function StatePreparationOracle` | A utilização da frase do substantivo sugere que a função devolve uma operação. |
| ☑ | `function EqualityFact` | Uso claro do substantivo ("facto") para indicar que esta é uma função, enquanto o adjetivo. |
| ☒ | <s>`function GetRotationAngles`</s> | A utilização do verbo ("get") sugere que se trata de uma operação. |
| ☑ | `newtype GeneratorTerm` | O uso da frase substantivo refere-se claramente ao resultado de chamar o construtor da UDT. |
| ☒ | <s>`@Attribute() newtype RunOnce()`</s> | O uso da frase verbo sugere que o construtor uDT é uma operação. |
| ☑ | `@Attribute() newtype Deprecated(Reason : String)` | O uso da frase substantivo comunica o uso do atributo. |

***

### <a name="shorthand-and-abbreviations"></a>Abreviaturas e Abreviaturas ###

Apesar dos conselhos acima referidos, existem muitas formas de abreviatura que vêem o uso comum e pervasivo na computação quântica.
Sugerimos a utilização de abreviaturas existentes e comuns onde ela existe, especialmente para operações intrínsecas ao funcionamento de uma máquina-alvo.
Por exemplo, escolhemos o nome `X` em vez de `ApplyX`, e `Rz` em vez de `RotateAboutZ`.
Quando utilizar esta abreviatura, os nomes de funcionamento devem ser todos maiúsculos (por exemplo: `MAJ`).

É necessário algum cuidado ao aplicar esta convenção no caso de siglas e rubricas comumente usadas, como "QFT" para "quantum Fourier transform".
Sugerimos que se seguem convenções gerais .NET para a utilização de siglas e rubricas em nomes completos, que prescrevem que:

- as siglas de duas letras e os iniciantes são nomeados em maiúsculas (por exemplo: `BE` para "grande endian"),
- todos os siglas e iniciais mais longos são nomeados em `CamelCase` (por exemplo: `Qft` para "quantum Fourier transform")

Assim, uma operação de execução do QFT pode ser chamada de `QFT` como abreviatura, ou escrita como `ApplyQft`.

Para operações e funções particularmente utilizadas, pode ser desejável fornecer um nome abreviado como _pseudónimo_ para uma forma mais longa:

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Considere nomes de abreviaturas geralmente aceites e amplamente utilizados quando apropriado.
- Utilize maiúsculas para abreviar.
- Utilize maiúsculas para siglas curtas (de duas letras) e inicialismos.
- Utilize `CamelCase` para siglas e rubricas mais longas (três ou mais letras).

# <a name="examples"></a>[Exemplos](#tab/examples)

|   | Nome | Descrição |
|---|------|-------------|
| ☑ | `X` | Abreviatura bem entendida para "aplicar uma transformação $X$" |
| ☑ | `CNOT` | Abreviatura bem compreendida para "controlled-NOT" |
| ☒ | <s>`Cnot`</s> | Abreviatura não deve estar em `CamelCase`. |
| ☑ | `ApplyQft` | O inicialismo comum "QFT" aparece como parte de um nome de longa forma. |
| ☑ | `QFT` | O inicialismo comum "QFT" aparece como parte de um nome abreviado. |



***


### <a name="proper-nouns-in-names"></a>Substantivos próprios em nomes ###

Enquanto na física é comum nomear coisas depois da primeira pessoa a publicar sobre elas, a maioria dos não-físicos não estão familiarizados com os nomes de todos e toda a história.
Confiar demasiado na nomeação de convenções da física pode, assim, colocar uma barreira substancial à entrada, uma vez que os utilizadores de outras origens devem aprender um grande número de nomes aparentemente opacos para utilizar operações e conceitos comuns.
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
Assim, recomendamos que, sempre que razoáveis, substantivos comuns que descrevem um conceito sejam adotados com forte preferência pelos substantivos adequados que descrevem a história da publicação de um conceito.
Como exemplo particular, as operações de SWAP e NOT controladas com ousadia são muitas vezes chamadas de operações "Fredkin" e "Toffoli" na literatura académica, mas são identificadas em Q# principalmente como `CSWAP` e `CCNOT`.
Em ambos os casos, os comentários de documentação da API fornecem nomes sinónimos baseados em substantivos adequados, juntamente com todas as citações apropriadas.

Esta preferência é especialmente importante dado que algum uso de substantivos adequados será sempre necessário - Q# segue a tradição definida por muitas línguas clássicas, por exemplo, e refere-se a `Bool` tipos em referência à lógica booleana, que por sua vez é nomeado em homenagem a George Boole.
Alguns conceitos quânticos são igualmente nomeados de forma semelhante, incluindo o tipo `Pauli` incorporado à língua Q#.
Minimizando a utilização de substantivos adequados onde tal utilização não é essencial, reduzimos o impacto em que os substantivos adequados não podem ser razoavelmente evitados.

# <a name="guidance"></a>[Orientação](#tab/guidance) 

Sugerimos:

- Evite a utilização de substantivos adequados em nomes.

# <a name="examples"></a>[Exemplos](#tab/examples)

***

### <a name="type-conversions"></a>Conversões de tipo ###

Uma vez que Q# é uma linguagem forte e estática dactilografada, um valor de um tipo só pode ser usado como um valor de outro tipo usando uma chamada explícita para uma função de conversão de tipo.
Isto contrasta com as línguas que permitem que os valores mudem de forma implícita (por exemplo: promoção do tipo), ou através do casting.
Como resultado, as funções de conversão de tipo desempenham um papel importante no desenvolvimento da biblioteca Q# e compreendem uma das decisões mais comummente encontradas sobre nomeação.
Notamos, no entanto, que, uma vez que as conversões de tipo são sempre _determinísticas,_ podem ser escritas como funções e, portanto, enquadrar-se nos conselhos acima referidos.
Em particular, sugerimos que as funções de conversão de tipo nunca devem ser nomeadas como verbos (por exemplo: `ConvertToX`) ou frases preposicionais advérbios (`ToX`), mas devem ser nomeadas como frases preposicionais adjetivas que indiquem os tipos de origem e destino (`XAsY`).
Ao enumerar os tipos de matriz em nomes de funções de conversão de tipo, recomendamos a abreviatura `Arr`.
Excluindo circunstâncias excecionais, recomendamos que todas as funções de conversão do tipo sejam nomeadas usando `As` para que possam ser rapidamente identificadas.

# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Se uma função converter um valor de `X` de tipo para um valor de `Y`, utilize o nome `AsY` ou `XAsY`.

# <a name="examples"></a>[Exemplos](#tab/examples)

|   | Nome | Descrição |
|---|------|-------------|
| ☒ | <s>`ToDouble`</s> | A preposição "a" resulta numa frase verbo, indicando uma operação e não uma função. |
| ☒ | <s>`AsDouble`</s> | O tipo de entrada não é claro a partir do nome da função. |
| ☒ | <s>`PauliArrFromBoolArr`</s> | Os tipos de entrada e saída aparecem na ordem errada. |
| ☑ | `ResultArrAsBoolArr` | Tanto os tipos de entrada como os tipos de saída são claros. |

***

### <a name="private-or-internal-names"></a>Nomes privados ou internos ###

Em muitos casos, um nome destina-se estritamente a ser usado internamente para uma biblioteca ou projeto, e não é uma parte garantida da API oferecida por uma biblioteca.
É útil indicar claramente que é esse o caso quando se marcam funções e operações para que as dependências acidentais do código interno sejam tornadas óbvias.
Se uma operação ou função não se destinar a uma utilização direta, mas deve ser utilizada por um callable correspondente que atue por aplicação parcial, considere utilizar um nome a partir de `_` para o callable que é parcialmente aplicado.

# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Quando uma função, operação ou tipo definido pelo utilizador não faz parte da API pública para uma biblioteca ou programa Q#, certifique-se de que o seu nome começa com um sublinhado líder (`_`).

# <a name="examples"></a>[Exemplos](#tab/examples)

|   | Nome | Descrição |
|---|------|-------------|
| ☒ | <s>`ApplyDecomposedOperation_`</s> | O sublinhado `_` não deve aparecer no final do nome. |
| ☑ | `_ApplyDecomposedOperation` | O sublinhado `_` no início indica claramente que esta operação é apenas para uso interno. |

***

### <a name="variants"></a>Variantes ###

Embora esta limitação possa não persistir em futuras versões de Q#, é atualmente o caso de que muitas vezes haverá grupos de operações ou funções relacionadas que se distinguem pelos quais os functores apoiam os seus inputs, ou pelos tipos concretos dos seus argumentos.
Estes grupos podem ser distinguidos usando o mesmo nome raiz, seguidos por uma ou duas letras que indicam a sua variante.

| Sufixo | Significado |
|--------|---------|
| `A` | Input esperado para apoiar `Adjoint` |
| `C` | Input esperado para apoiar `Controlled` |
| `CA` | Espera-se que os contributos apoiem `Controlled` e `Adjoint` |
| `I` | As inputs ou as inputs são do tipo `Int` |
| `D` | As inputs ou as inputs são do tipo `Double` |
| `L` | As inputs ou as inputs são do tipo `BigInt` |

# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Se uma função ou operação não estiver relacionada com funções ou operações semelhantes pelos tipos e suporte do functor das suas inputs, não utilize um sufixo.
- Se uma função ou operação estiver relacionada com funções ou operações semelhantes pelos tipos e suporte functor das suas inputs, utilize sufixos como na tabela acima para distinguir variantes.

# <a name="examples"></a>[Exemplos](#tab/examples)

***

### <a name="arguments-and-variables"></a>Argumentos e Variáveis ###

Um objetivo chave do código Q# para uma função ou operação é que seja facilmente lido e compreendido.
Da mesma forma, os nomes de inputs e argumentos de tipo devem comunicar como uma função ou argumento será usado uma vez fornecido.


# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Para todos os nomes variáveis e de entrada, utilize `pascalCase` em forte preferência por `CamelCase`, `snake_case`ou `ANGRY_CASE`.
- Os nomes de entrada devem ser descritivos; evitar um ou dois nomes de letras sempre que possível.
- As operações e funções que aceitam exatamente um tipo de argumento devem denotar esse tipo de argumento por `T` quando o seu papel é óbvio.
- Se uma função ou operação tiver argumentos de vários tipos, ou se o papel de um único tipo de argumento não for óbvio, considere usar uma palavra capitalizada curta prefaciada por `T` (por exemplo: `TOutput`) para cada tipo.
- Não inclua nomes de tipo em nomes de argumentos e variáveis; esta informação pode e deve ser fornecida pelo seu ambiente de desenvolvimento.
- Denote tipos escalar pelos seus nomes literais (`flagQubit`) e tipos de matriz por um plural (`measResults`).
  Para conjuntos de qubits em particular, considere denotar tais tipos por `Register` onde o nome se refere a uma sequência de qubits que estão intimamente relacionados de alguma forma.
- As variáveis utilizadas como índices em matrizes devem começar com `idx` e devem ser singulares (por exemplo: `things[idxThing]`).
  Em especial, evite misé-lo-de-letra como índices; considerar usar `idx` no mínimo.
- As variáveis utilizadas para conter os comprimentos das matrizes devem começar com `n` e devem ser pluralizadas (por exemplo: `nThings`).

# <a name="examples"></a>[Exemplos](#tab/examples)

***

### <a name="user-defined-type-named-items"></a>Itens nomeados por tipo definido do utilizador ###

Os itens nomeados em tipos definidos pelo utilizador devem ser nomeados como `CamelCase`, mesmo em entrada para construtores UDT.
Isto ajuda a separar claramente os itens nomeados de referências a variáveis de âmbito local quando se utiliza a notação acessónica (por exemplo: `callable::Apply`) ou notação de cópia e atualização (`set arr w/= Data <- newData`).

# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Os artigos nomeados em construtores da UDT devem ser nomeados como `CamelCase`; isto é, devem começar com uma maiúscula inicial.
- Os itens nomeados que resolvem as operações devem ser nomeados como fases verbo.
- Os itens nomeados que não se resolvem às operações devem ser nomeados como frases de substantivos.
- Para os UDTs que encerram operações, um único item chamado `Apply` deve ser definido.

# <a name="examples"></a>[Exemplos](#tab/examples)

|   | Corte | Descrição |
|---|---------|-------------|
| ☑ | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | O nome `Apply` é uma frase verbo `CamelCase`-formatada, sugerindo que o item nomeado é uma operação. |
| ☒ | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | Os itens nomeados devem começar com uma letra maiúscula inicial. |
| ☒ | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | Os itens nomeados que se resolvem com as funções devem ser nomeados como frases de substantivo, e não como frases verbos. |

***

## <a name="input-conventions"></a>Convenções de Entrada ##

Quando um desenvolvedor chama a uma operação ou função, as várias inputs para essa operação ou função devem ser especificadas numa determinada ordem, aumentando a carga cognitiva que um desenvolvedor enfrenta para fazer uso de uma biblioteca.
Em particular, a tarefa de lembrar as encomendas de entrada é muitas vezes uma distração da tarefa em questão: programar uma implementação de um algoritmo quântico.
Embora o apoio rico do IDE possa mitigar isso em grande medida, um bom design e aadesão a convenções comuns também podem ajudar a minimizar a carga cognitiva imposta por uma API.

Sempre que possível, pode ser útil reduzir o número de inputs esperados por uma operação ou função, de modo que o papel de cada entrada seja mais imediatamente óbvio tanto para os desenvolvedores que ligam para essa operação ou função, como para os desenvolvedores que lêem esse código mais tarde.
Especialmente quando não é possível ou razoável reduzir o número de argumentos para uma operação ou função, é importante ter uma ordem consistente que minimize a surpresa que um utilizador enfrenta ao prever a ordem dos inputs.

Recomendamos uma convenção de encomenda de entrada que deriva em grande parte da reflexão da aplicação parcial como uma generalização da currying f(x, y) ≤ f(x)(y).
Assim, a aplicação parcial dos primeiros argumentos deve resultar num callable que seja útil por si só sempre que isso seja razoável.
Seguindo este princípio, considere a utilização da seguinte ordem de argumentação:

- Argumentos clássicos não-insensíveis, tais como ângulos, vetores de poderes, etc.
- Argumentos insensíveis (funções e argumentos).
  Se ambas as funções e operações forem tomadas como argumentos, considere a colocação de operações após funções.
- As coleções foram tomadas por argumentos insensíveis de forma semelhante à `Map`, `Iter`, `Enumerate`e `Fold`.
- Argumentos qubit usados como controlos.
- Argumentos qubit usados como alvos.

Considere uma operação `ApplyPhaseEstimationIteration` para utilização na estimativa de fase que toma um ângulo e um oráculo, passa o ângulo para `Rz` modificado por uma variedade de diferentes fatores de escala, e, em seguida, controla as aplicações do oráculo.
Ordenamos que os inputs `ApplyPhaseEstimationIteration` da seguinte forma:

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
Como um caso especial de minimização surpresa, algumas funções e operações imitam o comportamento dos functors incorporados `Adjoint` e `Controlled`.
Por exemplo, `ControlledOnInt<'T>` tem `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`tipo , de tal forma que `ControlledOnInt<Qubit[]>(5, _)` age como o functor `Controlled`, mas na condição de que o registo de controlo represente o estado $\ket{5} = \ket{101}$.
Assim, um desenvolvedor espera que as inputs `ControlledOnInt` coloquem o callable sendo transformado por último, e que a operação resultante assuma como sua entrada `(Qubit[], 'T)` --- a mesma ordem seguida pela saída do functor `Controlled`.

# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Utilize pedidos de entrada consistentes com a utilização da aplicação parcial.
- Utilize pedidos de entrada consistentes com functores incorporados.
- Coloque todas as inputs clássicas antes de qualquer entrada quântica.

# <a name="examples"></a>[Exemplos](#tab/examples)

***

## <a name="documentation-conventions"></a>Convenções da Documentação ##

O idioma Q# permite anexar documentação a operações, funções e tipos definidos pelo utilizador através da utilização de comentários de documentação especialmente formatados.
Denotados por cortes triplos (`///`), estes comentários de documentação são pequenos documentos [de Markdown com sabor do DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) que podem ser usados para descrever o propósito de cada operação, função e tipo definido pelo utilizador, o que cada entrada espera, e assim por diante.
O compilador fornecido com o Kit de Desenvolvimento Quântico extrai estes comentários e usa-os para ajudar a escrever documentação semelhante à de https://docs.microsoft.com/quantum.
Da mesma forma, o servidor de idiomas fornecido com o Kit de Desenvolvimento Quântico utiliza estes comentários para fornecer ajuda aos utilizadores quando pairam sobre símbolos no seu código Q#.
Fazer uso de comentários de documentação pode, assim, ajudar os utilizadores a fazer sentido do código, fornecendo uma referência útil para detalhes que não são facilmente expressos usando as outras convenções deste documento.

<div class="nextstepaction">
    [Documentação comentário sintax referenciação](xref:microsoft.quantum.language.statements#documentation-comments)
</div>

Para utilizar eficazmente esta funcionalidade para ajudar os utilizadores, recomendamos que tenha algumas coisas em mente à medida que escreve comentários de documentação.

# <a name="guidance"></a>[Orientação](#tab/guidance)

Sugerimos:

- Cada função pública, operação e tipo definido pelo utilizador devem ser imediatamente precedidos por um comentário de documentação.
- No mínimo, cada comentário de documentação deve incluir as seguintes secções:
    - Resumo
    - Input
    - Saída (se aplicável)
- Certifique-se de que todos os resumos são duas frases ou menos. Se for necessário mais espaço, forneça uma secção `# Description` imediatamente a seguir `# Summary` com detalhes completos.
- Quando razoável, não inclua matemática em resumos, uma vez que nem todos os clientes apoiam a notação TeX em resumos. Note que ao escrever documentos de prosa (por exemplo, TeX ou Markdown), pode ser preferível utilizar comprimentos de linha mais longos.
- Forneça todas as expressões matemáticas relevantes na secção `# Description`.
- Ao descrever as inputs, não repita os tipos de cada entrada, uma vez que estas podem ser inferidas pelo compilador e correr o risco de introduzir inconsistência.
- Forneça exemplos conforme apropriado, cada um na sua própria secção `# Example`.
- Descreva brevemente cada exemplo antes de listar o código.
- Cite todas as publicações académicas relevantes (por exemplo: trabalhos, procedimentos, posts de blogs e implementações alternativas) numa secção `# References` como uma lista de links.
- Certifique-se de que, sempre que possível, todas as ligações de citação são para identificadores permanentes e imutáveis (DOIs ou números arXiv versados).
- Quando uma operação ou função estiver relacionada com outras operações ou funções por variantes de functor, enumerar outras variantes como balas na secção `# See Also`.
- Deixe uma linha de comentários em branco entre as secções de nível 1 (`/// #`), mas não deixe uma linha em branco entre as secções de nível 2 (`/// ##`).

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
Tais regras de formatação por natureza tendem a ser um pouco arbitrárias e fortemente até estética seletiva.
No entanto, recomendamos a manutenção de um conjunto consistente de convenções de formatação dentro de um grupo de colaboradores, e especialmente para grandes projetos Q# como o próprio Quantum Development Kit.
Estas regras podem ser aplicadas automaticamente utilizando a ferramenta de formatação integrada com o compilador Q#.

# <a name="guidance"></a>[Orientação](#tab/guidance) 

Sugerimos:

- Utilize quatro espaços em vez de separadores para portabilidade.
  Por exemplo, no Código VS:
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- Embrulho de linha em 79 caracteres onde razoável.
- Utilize espaços em torno de operadores binários.
- Utilize espaços em ambos os lados dos cólons utilizados para anotações de tipo.
- Utilize um único espaço após as vírgulas utilizadas em matriz e tuple literal (por exemplo: em inputs para funções e operações).
- Não utilize espaços após função, funcionamento ou nomes uDT, ou após o `@` em declarações de atributos.
- Cada declaração de atributo deve estar na sua própria linha.

# <a name="examples"></a>[Exemplos](#tab/examples)

|   | Corte | Descrição |
|---|---------|-------------|
| ☒ | <s>`2+3`</s> | Utilize espaços em torno de operadores binários. |
| ☒ | <s>`target:Qubit`</s> | Utilize espaços em torno de cólons de anotação tipo. |
| ☑ | `Example(a, b, c)` | Os itens em tuple de entrada são corretamente espaçados para a legibilidade. |
| ☒ | <s>`Example (a, b, c)`</s> | Os espaços devem ser suprimidos após a função, operação ou nomes uDT. |

***

