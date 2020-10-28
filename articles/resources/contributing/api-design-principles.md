---
title: Q# Princípios de design da API
description: Q# Princípios de design da API
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6b196cf1be584a3157c7a9eb8cf497fe1121dd7a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691818"
---
# <a name="no-locq-api-design-principles"></a>Q# Princípios de design da API

## <a name="introduction"></a>Introdução

Como idioma e como plataforma, Q# capacita os utilizadores a escrever, executar, compreender e explorar aplicações quânticas.
De forma a capacitar os utilizadores, quando projetamos Q# bibliotecas, seguimos um conjunto de princípios de design da API para orientar os nossos projetos e ajudar-nos a fazer bibliotecas utilizáveis para a comunidade de desenvolvimento quântico.
Este artigo enumera estes princípios e dá exemplos para ajudar a orientar a aplicação dos mesmos ao conceber Q# APIs.

> [!TIP]
> Este é um documento bastante detalhado que se destina a ajudar a orientar o desenvolvimento da biblioteca e as contribuições aprofundadas da biblioteca.
> Provavelmente será mais útil se estiver a escrever as suas próprias bibliotecas Q# em , ou se estiver a contribuir com características maiores para o [ Q# repositório de bibliotecas.](https://github.com/microsoft/QuantumLibraries)
>
> Por outro lado, se procura aprender a contribuir para o Kit de Desenvolvimento Quântico de uma forma mais geral, sugerimos que comece com o [guia de contribuição.](xref:microsoft.quantum.contributing)
> Se procura informações mais gerais sobre como recomendamos a formatação do seu Q# código, poderá estar interessado em consultar o [guia](xref:microsoft.quantum.contributing.style)de estilo .

## <a name="general-principles"></a>Princípios Gerais

**Princípio-chave:** Expor APIs que coloca o foco nas aplicações quânticas.

- ✅**ESCOLHA** nomes de funcionamento e função que reflitam a estrutura de alto nível de algoritmos e aplicações.
- ⛔️ **NÃO** exponha APIs que se centrem principalmente em detalhes de implementação de baixo nível.

**Princípio-chave:** Inicie cada design API com casos de utilização de amostras para garantir que as APIs são intuitivas de usar.

- ✅**DO** Certifique-se de que cada componente de uma API pública tem uma caixa de utilização correspondente, em vez de tentar conceber para todas as utilizações possíveis desde o início.
    Dito de outra forma, não introduza APIs públicos no caso de serem úteis, mas certifique-se de que cada parte de uma API tem um exemplo *concreto* no qual será útil.

  *Exemplos:*
  - @"microsoft.quantum.canon.applytoeachca" pode ser usado `ApplyToEachCA(H, _)` como para preparar registos em um estado de superposição uniforme, uma tarefa comum em muitos algoritmos quânticos. A mesma operação também pode ser usada para muitas outras tarefas em preparação, numéricos e algoritmos baseados em oráculo.

- ✅**DO** brainstorm e workshop novos projetos API para verificar duas vezes que eles são intuitivos e atender casos de uso propostos.

  *Exemplos:*
  - Inspecione o código Q atual \# para ver como os novos desenhos da API podem simplificar e clarificar as implementações existentes.
  - Rever projetos de API propostos com representantes de audiências primárias.

**Princípio-chave:** Conceber APIs para apoiar e incentivar código legível.

- ✅**Certifique-se** de que o código é legível por peritos de domínio e não especialistas.
- ✅**DO** colocar o foco nos efeitos de cada operação e função dentro do algoritmo de alto nível, usando documentação para aprofundar detalhes de implementação conforme apropriado.
- ✅**DO** Siga o guia comum [ \# de estilo Q](xref:microsoft.quantum.contributing.style) sempre que aplicável.

**Princípio-chave:** As APIs de conceção são estáveis e proporcionam compatibilidade antecipada.

- ✅**DO** depreciar as antigas APIs graciosamente quando são necessárias alterações.

- ✅**DO** fornecer operações e funções "shim" que permitem que o código do utilizador existente funcione corretamente durante a depreciação.

  *Exemplos:*
  - Ao renomear uma operação chamada `EstimateExpectation`   `EstimateAverage` para , introduza uma nova operação chamada   `EstimateExpectation` que chama a operação original no seu novo nome, para que o código existente possa continuar a funcionar corretamente.

- ✅**DO** utilizar o @"microsoft.quantum.core.deprecated" atributo para comunicar depreciações ao utilizador.

- ✅ Ao renomear uma operação ou função, **doa** fornecer o novo nome como entrada de corda para `@Deprecated` .

- ⛔️ **NÃO** remova as funções ou operações existentes sem um período de depretação de pelo menos seis meses para lançamentos de pré-visualização, ou pelo menos dois anos para lançamentos suportados.

## <a name="functions-and-operations"></a>Funções e Operações

**Princípio-chave:** garantir que cada função e funcionamento tem um único propósito bem definido dentro da API.

- ⛔️ **NÃO** exponha funções e operações que executam várias tarefas não relacionadas.

**Princípio-chave:** funções de conceção e operações para serem o mais reutilizáveis possível e antecipar necessidades futuras.

- ✅**DO** design funções e operações para compor bem com outras funções e operações, tanto na mesma API como em bibliotecas anteriormente existentes.

  *Exemplos:*
  - A @"microsoft.quantum.canon.delay" operação faz pressupostos mínimos sobre a sua entrada, podendo assim ser usada para atrasar aplicações de qualquer uma das operações através da Q# biblioteca padrão ou como definido pelos utilizadores.
    <!-- TODO: define bad example. -->

- ✅**DO** expor a lógica clássica puramente determinista como funções e não operações.

  *Exemplos:*
  - Uma sub-rotina que quadra a sua entrada de ponto flutuante pode ser escrita determinicamente, pelo que deve ser exposta ao utilizador como `Squared : Double -> Double` e não como uma operação `Square : Double => Double` . Isto permite que a subrotina seja chamada em mais lugares (por exemplo: dentro de outras funções), e fornece informações úteis de otimização ao compilador que podem afetar o desempenho e otimizações.
  - `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` e `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` diferem nas garantias feitas no que diz respeito ao determinismo; ambas são úteis em diferentes circunstâncias.
  - As rotinas da API que transformam a aplicação de operações quânticas podem muitas vezes ser realizadas de forma determinística e, portanto, podem ser disponibilizadas como funções como   `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)` .

- ✅**Do** generalizar o tipo de entrada tanto quanto razoável para cada função e funcionamento, utilizando os parâmetros do tipo conforme necessário.

  *Exemplos:*
  - `ApplyToEach` tem tipo `<'T>(('T => Unit), 'T[]) => Unit` e não o tipo específico da sua aplicação mais comum, `((Qubit => Unit), Qubit[]) => Unit` .

> [!TIP]
> É importante antecipar as necessidades futuras, mas também é importante resolver problemas concretos para os seus utilizadores.
> Agir com base neste princípio-chave requer sempre uma cuidadosa consideração e equilíbrio para evitar o desenvolvimento de APIs "apenas por precaução".

**Princípio-chave:** escolha tipos de entrada e saída para funções e operações previsíveis, e que comuniquem o propósito de uma chamada.

- ✅**DO** utilize tipos de tuple para agrupar logicamente entradas e saídas que só são significativas quando consideradas juntas. Considere usar um tipo definido pelo utilizador nestes casos.

  *Exemplos:*
  - Uma função para a saída do minima local de outra função pode precisar de assumir limites de um intervalo de pesquisa como entrada, de modo que `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` pode ser uma assinatura apropriada.
  - Uma operação para estimar um derivado de um classificador de aprendizagem automática usando a técnica de mudança de parâmetros pode precisar de tomar tanto os vetores de parâmetros deslocados como não-deslocados como entradas. Neste caso, pode ser apropriado uma entrada `(unshifted : Double[], shifted : Double[])` semelhante.

- ✅**DO** Encomendar itens em tuples de entrada e saída consistentemente em diferentes funções e operações.

  *Exemplos:*
  - Se considerar duas ou funções ou operações que cada um toma um ângulo de rotação e um qubit alvo como entradas, certifique-se de que são encomendados o mesmo em cada tuple de entrada. Isto é, prefere `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` e `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` para `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` e.

**Princípio-chave:** funções de design e operações para funcionar bem com \# características da língua Q, tais como aplicação parcial.

- ✅**DO** encomendar itens em tuples de entrada de modo a que as entradas mais aplicadas ocorram primeiro (isto é, que a aplicação parcial atue de forma semelhante à caril).

  *Exemplos:*
  - Uma operação `ApplyRotation` que leva um número de ponto flutuante e um qubit, uma vez que as entradas podem muitas vezes ser parcialmente aplicadas com a entrada de ponto flutuante primeiro para utilização com operações que esperam uma entrada do tipo `Qubit => Unit` . Assim, uma assinatura de `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`
      funcionaria de forma mais consistente com aplicação parcial.
  - Tipicamente, esta orientação significa colocar todos os dados clássicos antes de todos os qubits em tuples de entrada, mas use bom senso e examine como a sua API é chamada na prática.

## <a name="user-defined-types"></a>User-Defined Tipos

**Princípio-chave:** utilize tipos definidos pelo utilizador para ajudar a tornar as APIs mais expressivas e convenientes de usar.

- ✅**DO** introduzir novos tipos definidos pelo utilizador para fornecer abreviatura útil para tipos longos e/ou complicados.

  *Exemplos:*
  - Nos casos em que um tipo de operação com três entradas de matriz de qubit é geralmente tomado como uma entrada ou devolvido como uma saída, fornecendo um UDT como `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`
      pode ajudar a fornecer uma abreviatura útil.

- ✅**DO** introduzir novos tipos definidos pelo utilizador para indicar que um dado tipo de base só deve ser utilizado num sentido muito particular.

  *Exemplos:*
  - Uma operação que deve ser interpretada especificamente como uma operação que codifica dados clássicos num registo quântico pode ser adequada para rotular com um tipo definido pelo utilizador `newtype InputEncoder = (Apply : (Qubit[] => Unit))` .

- ✅**DO** introduzir novos tipos definidos pelo utilizador com itens nomeados que permitam uma extensibilidade futura (por exemplo: uma estrutura de resultados que pode conter itens nomeados adicionais no futuro).

  *Exemplos:*
  - Quando uma operação `TrainModel` expõe um grande número de opções de configuração, expondo estas opções como um novo   `TrainingOptions` UDT e fornecendo uma nova função   `DefaultTrainingOptions : Unit -> TrainingOptions` permite que os utilizadores substituam itens específicos nomeados em valores de UDT trainingOptions, permitindo ainda que os desenvolvedores de bibliotecas adicione novos itens UDT conforme apropriado.

- ✅**DO** declarar itens nomeados para novos tipos definidos pelo utilizador, preferencialmente para exigir que os utilizadores saibam a desconstrução correta do tuple.

  *Exemplos:*
  - Quando se representa um número complexo na sua decomposição polar,   `newtype ComplexPolar = (Magnitude: Double, Argument: Double)`   `newtype ComplexPolar = (Double, Double)` prefere.

**Princípio-chave:** utilize tipos definidos pelo utilizador de forma a reduzir a carga cognitiva e que não exijam que o utilizador aprenda conceitos e nomenclatura adicionais.

- ⛔️ **NÃO** introduza tipos definidos pelo utilizador que exijam que o utilizador faça uso frequente do operador de desembrulhagem ( `!` ), ou que normalmente requerem vários níveis de desembrulhar. As possíveis estratégias de mitigação incluem:

  - Ao expor um tipo definido pelo utilizador com um único item, considere definir um nome para esse item. Por exemplo, considere `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)` preferencialmente.

  - Garantindo que outras funções e operações podem aceitar casos de UDT "embrulhados" diretamente.

- ⛔️ **NÃO** introduz novos tipos definidos pelo utilizador que duplicam os tipos incorporados sem fornecer expressividade adicional.

  *Exemplos:*
  - Um UDT `newtype QubitRegister = Qubit[]` não proporciona nenhuma expressividade adicional sobre , `Qubit[]` e é, portanto, mais difícil de usar sem nenhum benefício percetível.
  - Uma UDT `newtype LittleEndian = Qubit[]` documenta como o registo subjacente deve ser usado e interpretado, proporcionando assim expressividade adicional sobre o seu tipo de base.

- ⛔️ **NÃO** introduzas funções acessórias a não ser que seja estritamente necessário;   preferir fortemente itens nomeados neste caso.

  *Exemplos:*
  - Ao introduzir uma UDT, `newtype Complex = (Double, Double)` prefere modificar a definição   `newtype Complex = (Real : Double, Imag : Double)` para introduzir funções e `GetReal : Complex -> Double`   `GetImag : Complex -> Double` .

## <a name="namespaces-and-organization"></a>Espaços de nome e Organização

**Princípio-chave:** escolha nomes de espaço de nome que sejam previsíveis e que comuniquem claramente o propósito de funções, operações e tipos definidos pelo utilizador em cada espaço de nome.

- ✅**Do** namespaces como `Publisher.Product.DomainArea` .

  *Exemplos:*
  - Funções, operações e UDTs publicados pela Microsoft como parte da funcionalidade de simulação quântica do Kit de Desenvolvimento Quântico são colocados no espaço de   `Microsoft.Quantum.Simulation` nomes.
  - `Microsoft.Quantum.Math` representa um espaço de nome publicado pela Microsoft como parte do Kit de Desenvolvimento Quântico relativo à área de domínio da matemática.

- ✅**DO** colocar operações, funções e tipos definidos pelo utilizador usados para funcionalidades específicas num espaço de nome que descreve essa funcionalidade, mesmo quando essa funcionalidade é usada em diferentes domínios de problemas.

  *Exemplos:*
  - As APIs de preparação estatal publicadas pela Microsoft como parte do Kit de Desenvolvimento Quântico seriam colocadas em   `Microsoft.Quantum.Preparation` .
  - As APIs de simulação quântica publicadas pela Microsoft como parte do Kit de Desenvolvimento Quântico seriam colocadas em   `Microsoft.Quantum.Simulation` .

- ✅**DO** colocar operações, funções e tipos definidos pelo utilizador utilizados apenas em domínios específicos em espaços de nomes que indiquem o seu domínio de utilidade. Se necessário, utilize subnamespaces para indicar tarefas focadas em cada espaço de nome específico do domínio.

  *Exemplos:*
  - A biblioteca de aprendizagem de máquinas quânticas publicada pela Microsoft é em grande parte colocada no espaço de @"microsoft.quantum.machinelearning" nomes, mas os conjuntos de dados de exemplo são fornecidos pelo espaço de @"microsoft.quantum.machinelearning.datasets"   nomes.
  - As APIs de Química Quântica publicadas pela Microsoft como parte do Kit de Desenvolvimento Quântico devem ser colocadas em `Microsoft.Quantum.Chemistry` . A funcionalidade específica para a implementação da decomposição Jordan--Wigner pode ser colocada em `Microsoft.Quantum.Chemistry.JordanWigner` , de modo que a interface primária para a área de domínio da química quântica não está preocupada com implementações.

**Princípio-chave:** Utilize espaços de nome e modificadores de acesso em conjunto para ser intencional sobre a superfície da API exposta aos utilizadores, e para ocultar detalhes internos relacionados com a implementação e teste das suas APIs.

- ✅ Sempre que razoável, **DO** coloca todas as funções e operações necessárias para implementar uma API no mesmo espaço de nome que a API que a API está a ser implementada, mas marcada com as palavras-chave "privadas" ou "internas" para indicar que não fazem parte da superfície pública da API para uma biblioteca. Utilize um nome que comece com um sublinhado ( `_` ) para distinguir visualmente as operações e funções privadas e internas das chamadas públicas.

  *Exemplos:*
  - O nome da operação `_Features` indica uma função privada de um determinado espaço e montagem de nomes, e deve ser acompanhada por uma `internal` palavra-chave.

- ✅ No caso raro de um vasto conjunto de funções ou operações privadas serem necessárias para implementar a API para um determinado espaço de nome, **do** colocá-los em um novo espaço de nome que combine o espaço de nome que está sendo implementado e terminando em `.Private` .

- ✅**DO** Colocar todos os testes de unidade em espaços de nome que correspondam ao espaço de nome em teste e terminando em `.Tests` .

## <a name="naming-conventions-and-vocabulary"></a>Convenções de Nomeação e Vocabulário

**Princípio-chave:** Escolha nomes e terminologias claras, acessíveis e legíveis através de um leque diversificado de públicos, incluindo noviças quânticas e especialistas.

- ⛔️ **NÃO** utilizem nomes de identificadores discriminatórios ou exclusivos, nem terminologia em comentários de documentação da API.

- ✅**DO** use comentários de documentação da API para fornecer contexto relevante, exemplos e referências, especialmente para conceitos mais difíceis.

- ⛔️ **NÃO** use nomes de identificadores que sejam desnecessariamente esotéricos, ou que requerem conhecimentos significativos de algoritmos quânticos para ler.

  *Exemplos:*
  - Prefere "iteração de amplificação de amplitude" a "iteração grover".

- ✅**ESCOLHA** as operações e os nomes de funções que comunicam claramente o efeito pretendido de uma chamada, e não a sua implementação. Note que a implementação pode e deve ser documentada em [comentários de documentação da API](xref:microsoft.quantum.guide.filestructure#documentation-comments).

  *Exemplos:*
  - Prefere "estimativa sobreposição" a "Hadamard test", uma vez que este comunica como o primeiro é implementado.

- ✅**DO** usar palavras de forma consistente em todas as \# APIs Q:

  - **Verbos:**

    - **Afirmação** : Verifique se se mantém uma suposição sobre o estado de uma máquina-alvo e os seus qubits, possivelmente utilizando recursos não físicos. As operações que utilizam este verbo devem ser sempre removíveis com segurança sem afetar a funcionalidade das bibliotecas e dos programas executáveis. Note-se que, ao contrário dos factos, as afirmações podem, em geral, depender do estado externo, como o estado de um registo de qubits, o ambiente de execução ou assim por diante. Como a dependência do estado externo é uma espécie de efeito colateral, as afirmações devem ser expostas como operações e não como funções.

    - **Estimativa** : Utilizando uma ou mais medições possíveis repetidas, calcule uma quantidade clássica dos resultados da medição.

      *Exemplos:*
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - **Preparar:** Aplicar uma operação quântica ou sequência de operações a um ou mais qubits presumidos para iniciar num determinado estado inicial (normalmente $\ket{00\cdots 0}$), fazendo com que o estado desses qubits evolua para um estado final desejado. Em geral, agir em estados que não o estado inicial **determinado, o MAY** resulta numa transformação unitária indefinida, mas **deve** ainda preservar que uma operação e o seu adjacente "cancelam" e aplicam uma não-operação.

      *Exemplos:*
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - **Medida** : Aplicar uma operação quântica ou sequência de operações a um ou mais qubits, lendo os dados clássicos de volta.

      *Exemplos:*
      - @"Microsoft.Quantum.Intrinsic.Measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - **Aplicação:** Aplicar uma operação quântica ou sequência de operações a um ou mais qubits, fazendo com que o estado desses qubits mude de forma coerente. Este verbo é o verbo mais geral na \# nomenclatura Q, e **não deve ser** usado quando um verbo mais específico é mais diretamente relevante.

  - **Substantivos:**

    - **Facto** : Uma condição booleana que depende apenas das suas entradas e não do estado de uma máquina-alvo, do seu ambiente ou do estado dos qubits da máquina. Em contraste com uma afirmação, um facto só é sensível aos *valores* fornecidos a esse facto. Por exemplo:

      *Exemplos:*
      - @"microsoft.quantum.diagnostics.equalityfacti": representa um facto de igualdade sobre duas entradas completas; ou os inteiros fornecidos como entrada são iguais uns aos outros, ou não são, independentes de qualquer outro estado do programa.

    - **Opções:** Um UDT contendo vários itens nomeados que podem funcionar como "argumentos opcionais" para uma função ou operação. Por exemplo:

      *Exemplos:*
      - O @"microsoft.quantum.machinelearning.trainingoptions" UDT inclui itens nomeados para taxa de aprendizagem, tamanho de minibatch e outros parâmetros configuráveis para o treino de ML.

  - **Adjetivos:**

    - ⛔️ **Novo** : Este adjetivo **NÃO DEVE** ser utilizado, de modo a evitar confusão com a sua utilização como verbo em muitas línguas de programação (por exemplo: C++, C#, Java, TypeScript, PowerShell).

  - **Preposições:** Em alguns casos, as preposições podem ser usadas para desambiguar ou clarificar as funções de substantivos e verbos em nomes de funções e de funcionamento. No entanto, há que ter o cuidado de o fazer com moderação e de forma consistente.

    - **Como:** Representa que a entrada e a saída de uma função representam a mesma informação, mas que a saída representa essa informação **como** um *X* em vez da sua representação original. Isto é especialmente comum para funções de conversão de tipo.

      *Exemplos:*
      - `IntAsDouble(2)` indica que tanto a entrada ( `2` ) como a saída representam `2.0` qualitativamente a mesma informação, mas usando \# diferentes tipos de dados Q para fazê-lo.

    - **A partir de:** Para garantir a consistência, esta preposição   **NÃO deve** ser utilizada para indicar funções de conversão do tipo ou qualquer outro caso em **que** seja apropriado.

    - ⛔️ **Para:** Esta preposição **NÃO deve** ser utilizada, de modo a evitar confusões com a sua utilização como verbo em muitas linguagens de programação.
