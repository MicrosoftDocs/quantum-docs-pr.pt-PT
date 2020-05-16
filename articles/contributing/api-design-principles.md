---
title: Q# Princípios de Design da API
description: Q# Princípios de Design da API
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
ms.openlocfilehash: def6a9f12accfa399fd4db3783b9899fc743f025
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426448"
---
# <a name="q-api-design-principles"></a>Q# Princípios de Design da API

## <a name="introduction"></a>Introdução

Como um idioma e como uma plataforma, q# capacita os utilizadores a escrever, executar, entender e explorar aplicações quânticas.
Para capacitar os utilizadores, quando projetamos bibliotecas Q#, seguimos um conjunto de princípios de design da API para orientar os nossos projetos e ajudar-nos a criar bibliotecas utilizáveis para a comunidade de desenvolvimento quântico.
Este artigo enumera estes princípios e dá exemplos para ajudar a orientar como aplicá-los ao conceber ApIs Q#.

> [!TIP]
> Este é um documento bastante detalhado que se destina a ajudar a orientar o desenvolvimento da biblioteca e as contribuições aprofundadas da biblioteca.
> Provavelmente achará mais útil se estiver a escrever as suas próprias bibliotecas em Q#, ou se estiver a contribuir com características maiores para o [repositório de bibliotecas Q#](https://github.com/microsoft/QuantumLibraries).
>
> Por outro lado, se procura aprender a contribuir para o Kit de Desenvolvimento Quântico de uma forma mais geral, sugerimos começar pelo guia de [contribuição.](xref:microsoft.quantum.contributing)
> Se procura informações mais gerais sobre como recomendamos a formatação do seu código Q#, poderá estar interessado em consultar o guia de [estilo](xref:microsoft.quantum.contributing.style).

## <a name="general-principles"></a>Princípios Gerais

**Princípio-chave:** Expor APIs que colocam o foco nas aplicações quânticas.

- ✅**DO** escolha nomes de operação e função que reflitam a estrutura de alto nível de algoritmos e aplicações.
- ⛔️ **NÃO** exponha APIs que se focam principalmente em detalhes de implementação de baixo nível.

**Princípio-chave:** Inicie cada design de API com casos de utilização de amostras para garantir que as APIs são intuitivas de utilização.

- ✅**Do** garantir que cada componente de uma API pública tem um caso de utilização correspondente, em vez de tentar projetar para todas as utilizações possíveis desde o início.
    Dito de outra forma, não introduza APIs públicas no caso de serem úteis, mas certifique-se de que cada parte de uma API tem um exemplo *concreto* no qual será útil.

  *Exemplos:*
  - @"microsoft.quantum.canon.applytoeachca"pode ser usado como para preparar registos em um estado de `ApplyToEachCA(H, _)` superposição uniforme, uma tarefa comum em muitos algoritmos quânticos. A mesma operação também pode ser usada para muitas outras tarefas na preparação, numérico e algoritmos à base de oráculo.

- ✅**DO** brainstorm e workshop novos projetos de API para verificar duas vezes que eles são intuitivos e atender casos de uso propostos.

  *Exemplos:*
  - Inspecione o atual código Q \# para ver como os novos desenhos da API poderiam simplificar e clarificar as implementações existentes.
  - Reveja os projetos da API propostos com representantes do público primário.

**Princípio-chave:** Desenhe APIs para apoiar e incentivar códigolegível.

- ✅**Do** garantir que o código é legível por peritos de domínio e não especialistas.
- ✅**DO** coloca o foco nos efeitos de cada operação e função dentro do algoritmo de alto nível, usando documentação para aprofundar detalhes de implementação conforme apropriado.
- ✅**Siga** o [ \# guia](xref:microsoft.quantum.contributing.style) de estilo Q comum sempre que aplicável.

**Princípio-chave:** Design de APIs para ser estável e para proporcionar compatibilidade para a frente.

- ✅**DO** depreciar as APIs antigas graciosamente ao quebrar alterações são necessárias.

- ✅**O DO** fornece operações e funções "shim" que permitem que o código de utilizador existente funcione corretamente durante a depreciação.

  *Exemplos:*
  - Ao renomear uma operação chamada, introduza uma nova operação chamada que chama a operação original com o seu novo nome, para que o `EstimateExpectation` código existente possa continuar a funcionar `EstimateAverage` `EstimateExpectation` corretamente.

- ✅**DO** utilize o @"microsoft.quantum.core.deprecated" atributo para comunicar depreciações ao utilizador.

- ✅Ao renomear uma operação ou função, **doe** o novo nome como entrada de corda para `@Deprecated` .

- ⛔️ **NÃO** remova as funções ou operações existentes sem um período de depreciação de pelo menos seis meses para lançamentos de pré-visualização, ou pelo menos dois anos para lançamentos suportados.

## <a name="functions-and-operations"></a>Funções e Operações

**Princípio-chave:** certifique-se de que cada função e operação têm um único propósito bem definido dentro da API.

- ⛔️ **NÃO** exponha funções e operações que executam múltiplas tarefas não relacionadas.

**Princípio-chave:** funções de conceção e operações para serem o mais reutilizáveis possível e antecipar necessidades futuras.

- ✅**Funções** e operações de conceção DO para compor bem com outras funções e operações, tanto na mesma API como nas bibliotecas anteriormente existentes.

  *Exemplos:*
  - A @"microsoft.quantum.canon.delay" operação faz pressupostos mínimos sobre a sua entrada, podendo assim ser usado para atrasar aplicações de qualquer uma das operações através da biblioteca padrão Q# ou conforme definido pelos utilizadores.
    <!-- TODO: define bad example. -->

- ✅**Do** expor lógica clássica puramente determinística como funções e não operações.

  *Exemplos:*
  - Uma subrotina que quadrada a sua entrada de ponto flutuante pode ser escrita determinicamente, pelo que deve ser exposta ao utilizador como `Squared : Double -> Double` uma operação `Square : Double => Double` . Isto permite que a subrotina seja chamada em mais lugares (por exemplo: dentro de outras funções), e fornece informações úteis de otimização ao compilador que podem afetar o desempenho e otimizações.
  - `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]``Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]`e diferem nas garantias feitas no que diz respeito ao determinismo; ambas são úteis em circunstâncias diferentes.
  - As rotinas da API que transformam a aplicação de operações quânticas podem muitas vezes ser realizadas de forma determinística e, portanto, podem ser disponibilizadas como funções como `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)` .

- ✅**DO** generalizar o tipo de entrada tanto quanto razoável para cada função e operação, utilizando parâmetros do tipo conforme necessário.

  *Exemplos:*
  - `ApplyToEach`tem tipo `<'T>(('T => Unit), 'T[]) => Unit` em vez do tipo específico da sua aplicação mais comum, `((Qubit => Unit), Qubit[]) => Unit` .

> [!TIP]
> É importante antecipar as necessidades futuras, mas também é importante resolver problemas concretos para os seus utilizadores.
> Agir com base neste princípio-chave requer sempre uma ponderação cuidadosa e um equilíbrio para evitar o desenvolvimento de APIs "apenas por precaução".

**Princípio-chave:** escolha os tipos de entrada e de saída para funções e operações previsíveis, e que comuniquem o propósito de um callable.

- ✅**DO** use tipos de tuple para logicamente agrupar inputs e saídas que só são significativas quando consideradas em conjunto. Considere utilizar um tipo definido pelo utilizador nestes casos.

  *Exemplos:*
  - Uma função para a saída do minima local de outra função pode ter de assumir limites de um intervalo de pesquisa como entrada, de tal forma que `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` pode ser uma assinatura adequada.
  - Uma operação para estimar um derivado de um classificador de aprendizagem automática utilizando a técnica de mudança de parâmetros pode ter de tomar os vetores de parâmetros deslocados e não deslocados como inputs. Uma entrada semelhante `(unshifted : Double[], shifted : Double[])` pode ser apropriada neste caso.

- ✅**Do** encomende itens em tuples de entrada e saída consistentemente em diferentes funções e operações.

  *Exemplos:*
  - Se considerar duas ou funções ou operações que cada um tome um ângulo de rotação e um qubit de alvo como inputs, certifique-se de que são encomendados da mesma forma em cada túnica de entrada. Isto é, prefere `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` e.

**Princípio-chave:** funções de design e operações para funcionar bem com \# características linguísticas Q, tais como aplicação parcial.

- ✅**Do** encomendar itens em tuples de entrada de modo que as inputs mais aplicadas ocorrem primeiro (isto é, de modo que a aplicação parcial age de forma semelhante à caril).

  *Exemplos:*
  - Uma operação que leve um número de ponto flutuante e um qubit, uma vez que as `ApplyRotation` inputs podem muitas vezes ser parcialmente aplicadas com a entrada de ponto flutuante primeiro para utilização com operações que esperam uma entrada de tipo `Qubit => Unit` . Assim, uma assinatura de`operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`
      funcionaria de forma mais consistente com a aplicação parcial.
  - Normalmente, esta orientação significa colocar todos os dados clássicos antes de todos os qubits em tuples de entrada, mas use bom senso e examine como a sua API é chamada na prática.

## <a name="user-defined-types"></a>Tipos definidos pelo utilizador

**Princípio-chave:** utilize tipos definidos pelo utilizador para ajudar a tornar as APIs mais expressivas e convenientes de utilização.

- ✅**DO** introduz novos tipos definidos pelo utilizador para fornecer abreviatura útil para tipos longos e/ou complicados.

  *Exemplos:*
  - Nos casos em que um tipo de operação com três inputs de matriz qubit é geralmente tomado como uma entrada ou devolvido como uma saída, fornecendo um UDT como`newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`
      pode ajudar a fornecer uma abreviatura útil.

- ✅**Do** introduz novos tipos definidos pelo utilizador para indicar que um dado tipo de base só deve ser utilizado num sentido muito particular.

  *Exemplos:*
  - Uma operação que deve ser interpretada especificamente como uma operação que codifique os dados clássicos num registo quântico pode ser adequada para rotular com um tipo definido pelo utilizador `newtype InputEncoder = (Apply : (Qubit[] => Unit))` .

- ✅**DO** introduz novos tipos definidos pelo utilizador com itens nomeados que permitem a extensibility futura (por exemplo: uma estrutura de resultados que pode conter itens nomeados adicionais no futuro).

  *Exemplos:*
  - Quando uma operação `TrainModel` expõe um grande número de opções de configuração, expondo estas opções como um novo `TrainingOptions` UDT e fornecendo uma nova função `DefaultTrainingOptions : Unit -> TrainingOptions` permite que os utilizadores sobreponham itens específicos nomeados em valores UDT trainingOptions, permitindo ainda que os desenvolvedores de bibliotecas adicione novos itens UDT conforme apropriado.

- ✅**O DO** declara itens nomeados para novos tipos definidos pelo utilizador, preferencialmente para exigir que os utilizadores saibam a desconstrução correta.

  *Exemplos:*
  - Quando representar um número complexo na sua decomposição polar, `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` `newtype ComplexPolar = (Double, Double)` prefira.

**Princípio-chave:** utilize tipos definidos pelo utilizador de forma a reduzir a carga cognitiva e isso não exige que o utilizador aprenda conceitos e nomenclaturas adicionais.

- ⛔️ **NÃO** introduza tipos definidos pelo utilizador que exijam que o utilizador utilize frequentemente o operador de desembrulhar ( `!` ), ou que geralmente requerem múltiplos níveis de desembrulho. Possíveis estratégias de mitigação incluem:

  - Ao expor um tipo definido pelo utilizador com um único item, considere definir um nome para esse item. Por exemplo, considere `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` preferencialmente `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)` .

  - Garantir que outras funções e operações podem aceitar casos UDT "embrulhados" diretamente.

- ⛔️ **NÃO** introduza novos tipos definidos pelo utilizador que duplicam tipos incorporados sem fornecer expressividade adicional.

  *Exemplos:*
  - Um UDT `newtype QubitRegister = Qubit[]` não fornece nenhuma expressividade adicional sobre , `Qubit[]` e é, portanto, mais difícil de usar sem benefício supreensível.
  - A UDT `newtype LittleEndian = Qubit[]` documenta como o registo subjacente deve ser usado e interpretado, proporcionando assim expressividade adicional sobre o seu tipo base.

- ⛔️ **NÃO** introduza funções de acessório a menos que seja estritamente necessário;   fortemente preferem itens nomeados neste caso.

  *Exemplos:*
  - Ao introduzir um UDT, `newtype Complex = (Double, Double)` prefira modificar a definição `newtype Complex = (Real : Double, Imag : Double)` para a introdução de funções e `GetReal : Complex -> Double` `GetImag : Complex -> Double` .

## <a name="namespaces-and-organization"></a>Espaços de Nomee organização

**Princípio-chave:** escolha nomes de espaço de nome previsíveis e que comuniquem claramente o propósito das funções, operações e tipos definidos pelo utilizador em cada espaço de nome.

- ✅**NOME Sem** nome espaços como `Publisher.Product.DomainArea` .

  *Exemplos:*
  - Funções, operações e UDTs publicados pela Microsoft como parte da funcionalidade de simulação quântica do Kit de Desenvolvimento Quântico são colocados no espaço de `Microsoft.Quantum.Simulation` nome.
  - `Microsoft.Quantum.Math`representa um espaço de nome publicado pela Microsoft como parte do Kit de Desenvolvimento Quântico relativo à área do domínio da matemática.

- ✅**DO** coloca operações, funções e tipos definidos pelo utilizador utilizados para funcionalidades específicas num espaço de nome que descreve essa funcionalidade, mesmo quando essa funcionalidade é usada em diferentes domínios de problemas.

  *Exemplos:*
  - ApIs de preparação estatal publicados pela Microsoft como parte do Kit de Desenvolvimento Quântico seriam colocados em `Microsoft.Quantum.Preparation` .
  - ApIs de simulação quântica publicados pela Microsoft como parte do Kit de Desenvolvimento Quântico seriam colocados em `Microsoft.Quantum.Simulation` .

- ✅**DO** coloca operações, funções e tipos definidos pelo utilizador utilizados apenas em domínios específicos em espaços de nome, indicando o seu domínio de utilidade. Se necessário, utilize espaços com nome sinuoso para indicar tarefas focadas dentro de cada espaço de nome específico para domínio.

  *Exemplos:*
  - A biblioteca de machine learning quântica publicada pela Microsoft está em grande parte colocada no espaço de nome, mas os conjuntos de dados de @"microsoft.quantum.machinelearning" exemplo são fornecidos pelo espaço de @"microsoft.quantum.machinelearning.datasets" nome.
  - As APIs de química quântica publicadas pela Microsoft como parte do Kit de Desenvolvimento Quântico devem ser colocadas em `Microsoft.Quantum.Chemistry` . A funcionalidade específica para implementar a decomposição Jordan--Wigner pode ser colocada, de modo a que a interface primária para a área de domínio de `Microsoft.Quantum.Chemistry.JordanWigner` química quântica não esteja preocupada com implementações.

**Princípio-chave:** Utilize espaços de nome e modificadores de acesso em conjunto para serem intencionais sobre a superfície da API exposta aos utilizadores e para ocultar detalhes internos relacionados com a implementação e teste das suas APIs.

- ✅Sempre que razoável, o **DO** coloca todas as funções e operações necessárias para implementar uma API no mesmo espaço de nome que a API que está a ser implementada, mas marcada com as palavras-chave "privadas" ou "internas" para indicar que não fazem parte da superfície pública da API para uma biblioteca. Use um nome a partir de um sublinhado para `_` distinguir visualmente operações e funções privadas e internas de callables públicos.

  *Exemplos:*
  - O nome de funcionamento indica uma função privada para um determinado espaço de `_Features` nome e montagem, e deve ser acompanhado por qualquer uma das `internal` palavras-chave.

- ✅No caso raro de ser necessário um conjunto extensivo de funções ou operações privadas para implementar a API para um determinado espaço de nome, **do** o coloque-os num novo espaço de nome sincronizado com o espaço de nome sinuoso que está a ser implementado e terminando em `.Private` .

- ✅**Do** coloque todos os ensaios unitários em espaços de nome sincronizados com o espaço de nome em ensaio e terminando em `.Tests` .

## <a name="naming-conventions-and-vocabulary"></a>Convenções de Nomeação e Vocabulário

**Princípio-chave:** Escolha nomes e terminologia que sejam claros, acessíveis e legíveis em várias audiências, incluindo noviços quânticos e especialistas.

- ⛔️ **NÃO** utilize nomes de identificadores discriminatórios ou exclusivos, nem terminologia em comentários de documentação da API.

- ✅**DO** utilize comentários de documentação da API para fornecer contexto, exemplos e referências relevantes, especialmente para conceitos mais difíceis.

- ⛔️ **NÃO** utilize nomes identificadores que sejam desnecessariamente esotéricos, ou que requerem conhecimentos significativos de algoritmos quânticos para ler.

  *Exemplos:*
  - Prefira "amplificação de amplitude" a "iteração de Grover".

- ✅**DO** escolha operações e nomes de funções que comuniquem claramente o efeito pretendido de um callable, e não a sua implementação. Note que a implementação pode e deve ser documentada em comentários de [documentação da API.](xref:microsoft.quantum.guide.filestructure#documentation-comments)

  *Exemplos:*
  - Prefira "estimar a sobreposição" ao "teste de Hadamard", já que este comunica como o primeiro é implementado.

- ✅**DO** use palavras de forma consistente em todas as \# APIs Q:

  - **Verbos:**

    - **Afirmação**: Verifique se uma suposição sobre o estado de uma máquina-alvo e os seus qubits detém, possivelmente utilizando recursos não físicos. As operações que utilizam este verbo devem ser sempre amovíveis com segurança, sem afetar a funcionalidade das bibliotecas e programas executáveis. Note-se que, ao contrário dos factos, as afirmações podem, em geral, depender do estado externo, como o estado de um registo qubit, o ambiente de execução ou assim por diante. Como a dependência do estado externo é uma espécie de efeito colateral, as afirmações devem ser expostas como operações e não como funções.

    - **Estimativa**: Utilizando uma ou mais medições possivelmente repetidas, calcule uma quantidade clássica a partir dos resultados da medição.

      *Exemplos:*
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - **Preparação**: Aplique uma operação quântica ou sequência de operações a um ou mais qubits assumidos para começar em um determinado estado inicial (tipicamente $\ket{00\cdots 0}$), fazendo com que o estado desses qubits evolua para um estado final desejado. Em geral, agir em outros Estados que não o estado inicial **determinado, o MAIO resulta** numa transformação unitária indefinida, mas **deve** ainda preservar que uma operação e a sua adjoint "cancelam" e aplicam uma não-operação.

      *Exemplos:*
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - **Medida**: Aplicar uma operação quântica ou sequência de operações a um ou mais qubits, lendo os dados clássicos de volta.

      *Exemplos:*
      - @"microsoft.quantum.intrinsic.measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - **Aplicar**: Aplicar uma operação quântica ou sequência de operações a um ou mais qubits, fazendo com que o estado desses qubits mude de forma coerente. Este verbo é o verbo mais geral na \# nomenclatura Q, e **não deve ser** utilizado quando um verbo mais específico é mais diretamente relevante.

  - **Substantivos:**

    - **Facto**: Uma condição booleana que depende apenas das suas inputs e não do estado de uma máquina-alvo, do seu ambiente ou do estado dos qubits da máquina. Em contraste com uma afirmação, um facto só é sensível aos *valores* fornecidos a esse facto. Por exemplo:

      *Exemplos:*
      - @"microsoft.quantum.diagnostics.equalityfacti": representa um facto sobre a igualdade sobre dois inputs inteiros; ou os inteiros fornecidos como entrada são iguais uns aos outros, ou não são, independentes de qualquer outro estado de programa.

    - **Opções:** Um UDT contendo vários itens nomeados que podem funcionar como "argumentos opcionais" para uma função ou operação. Por exemplo:

      *Exemplos:*
      - A @"microsoft.quantum.machinelearning.trainingoptions" UDT inclui itens nomeados para taxa de aprendizagem, tamanho de minilote e outros parâmetros configuráveis para treino ml.

  - **Adjetivos:**

    - ⛔️ **Novo**: Este adjetivo **NÃO deve** ser utilizado, de modo a evitar confusão com a sua utilização como verbo em muitas linguagens de programação (por exemplo: C++, C#, Java, TypeScript, PowerShell).

  - **Preposições:** Em alguns casos, as preposições podem ser utilizadas para desambiguar ou clarificar as funções dos substantivos e verbos nos nomes de função e operação. No entanto, há que ter cuidado para o fazer com moderação e de forma consistente.

    - **Como:** Representa que a entrada e a saída de uma função representam a mesma informação, mas que a saída representa essa informação **como** *Um X* em vez da sua representação original. Isto é especialmente comum para funções de conversão de tipo.

      *Exemplos:*
      - `IntAsDouble(2)`indica que tanto a entrada `2` ( ) como a saída representam `2.0` qualitativamente a mesma informação, mas usando diferentes tipos de dados Q \# para o fazer.

    - **A partir de:** Para garantir a consistência, esta preposição **NÃO deve** ser utilizada para indicar funções de conversão de tipo ou qualquer outro caso **em** que seja apropriado.

    - ⛔️: Esta preposição **não deve** ser utilizada, de modo a evitar confusões com a sua utilização como verbo em muitas linguagens de programação. **To:**
