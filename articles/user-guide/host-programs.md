---
title: Formas de executar um Q# programa
description: Visão geral das diferentes formas de executar Q# programas. A partir do pedido de comando, Q# Jupyter Notebooks, e programas de anfitrião clássicos em Python ou uma língua .NET.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: f1eca44dabd72cd107d72d3b9e3ad1081c19c27d
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992195"
---
# <a name="ways-to-run-a-no-locq-program"></a>Formas de executar um Q# programa

Um dos maiores pontos fortes do Kit de Desenvolvimento Quântico é a sua flexibilidade em plataformas e ambientes de desenvolvimento.
No entanto, isto também significa que os novos Q# utilizadores podem encontrar-se confusos ou sobrecarregados com as inúmeras opções encontradas no [guia de instalação](xref:microsoft.quantum.install).
Nesta página, explicamos o que acontece quando um Q# programa é executado, e comparamos as diferentes formas de os utilizadores o poderem fazer.

Uma distinção primária é que Q# pode ser executada:
- como uma aplicação autónoma, onde Q# é a única língua envolvida e o programa é invocado diretamente. Na verdade, dois métodos enquadram-se nesta categoria:
  - a interface de linha de comando
  - Q# Cadernos Jupyter
- com um programa adicional *de anfitrião*, escrito em Python ou uma língua .NET (por exemplo, C# ou F#), que depois invoca o programa e pode processar mais resultados devolvidos.

Para melhor entender estes processos e as suas diferenças, consideramos um programa simples Q# e comparamos as formas como ele pode ser executado.

## <a name="basic-no-locq-program"></a>Programa Q# básico

Um programa quântico básico pode consistir em preparar um qubit em uma superposição igual de Estados {0} $\ket $ e $\ket {1} $, medindo-o, e devolvendo o resultado, que será aleatoriamente qualquer um destes dois estados com igual probabilidade.
Na verdade, este processo está no centro do rápido arranque do [gerador de números aleatórios quânticos.](xref:microsoft.quantum.quickstarts.qrng)

Em Q# , isto seria realizado pelo seguinte código:

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

No entanto, este código por si só não pode ser executado Q# por.
Para isso, tem de constituir o corpo de uma [operação](xref:microsoft.quantum.guide.basics#q-operations-and-functions), que é depois executada quando chamada--- diretamente ou por outra operação. Assim, pode escrever uma operação do seguinte formulário:
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
Definiu uma `MeasureSuperposition` operação, que não leva entradas e devolve um valor do tipo [Resultado](xref:microsoft.quantum.guide.types).

Embora os exemplos nesta página consistam apenas em Q# *operações,* todos os conceitos que discutiremos dizem igualmente respeito às Q# *funções*, e, portanto, referimo-los colectivamente como *callables.* As suas diferenças são discutidas no [ Q# básico: operações e funções,](xref:microsoft.quantum.guide.basics#q-operations-and-functions)e mais detalhes sobre a definição das mesmas podem ser encontrados nas [Operações e funções.](xref:microsoft.quantum.guide.operationsfunctions)

### <a name="callable-defined-in-a-no-locq-file"></a>Calável definido num Q# ficheiro

O callable é precisamente o que é chamado e dirigido Q# por.
No entanto, requer mais algumas adições para incluir um `*.qs` Q# ficheiro completo.

Todos os Q# tipos e callables (tanto aqueles que define como os intrínsecos à língua) são definidos dentro *de espaços de nome,* que fornecem a cada um um nome completo que pode então ser referenciado.

Por exemplo, as [`H`](xref:microsoft.quantum.intrinsic.h) operações e [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) as operações [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) encontram-se nos espaços e [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) nomes (parte das [ Q# Bibliotecas Padrão).](xref:microsoft.quantum.qsharplibintro)
Como tal, podem sempre ser chamados através dos seus nomes *completos,* `Microsoft.Quantum.Intrinsic.H(<qubit>)` e , mas `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` fazê-lo sempre levaria a um código muito desordenado.

Em vez disso, `open` as declarações permitem que os callables sejam referenciados com uma abreviatura mais concisa, como fizemos no corpo de operação acima.
O ficheiro completo Q# que contém a nossa operação consistiria, portanto, em definir o nosso próprio espaço de nome, abrindo os espaços de nome para os callables que a nossa operação utiliza e, em seguida, a nossa operação:

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> Os espaços de nome também podem ser *aliased quando abertos,* o que pode ser útil se nomes callable/tipo em dois espaços de nome conflito.
> Por exemplo, poderíamos, em vez disso, usar `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` acima, e depois ligar `H` via `NamespaceWithH.H(<qubit>)` .

> [!NOTE]
> Uma exceção a tudo isto é o espaço de [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) nome, que é sempre automaticamente aberto.
> Portanto, os calíveis como [`Length`](xref:microsoft.quantum.core.length) podem sempre ser usados diretamente.

### <a name="execution-on-target-machines"></a>Execução em máquinas-alvo

Agora o modelo geral de execução de um Q# programa torna-se claro.

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

Em primeiro lugar, a chamada específica a ser executada tem acesso a quaisquer outros calíveis e tipos definidos no mesmo espaço de nome.
Também acede às que provêm de qualquer uma das [ Q# bibliotecas](xref:microsoft.quantum.libraries), mas estas devem ser referenciadas quer através do seu nome completo, quer através da utilização de `open` declarações acima descritas.

A própria chamada é executada numa *[máquina-alvo.](xref:microsoft.quantum.machines)*
Tais máquinas-alvo podem ser hardware quântico real ou os múltiplos simuladores disponíveis como parte do QDK.
Para os nossos propósitos aqui, a máquina alvo mais útil é um exemplo do [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator) `QuantumSimulator` , que calcula o comportamento do programa como se estivesse sendo executado em um computador quântico sem ruído.

Até agora, descrevemos o que acontece quando uma chamada específica Q# está a ser executada.
Independentemente de ser Q# usado numa aplicação autónoma ou com um programa de acolhimento, este processo geral é mais ou menos o mesmo---a flexibilidade do QDK.
As diferenças entre as diferentes formas de chamar para o Kit de Desenvolvimento Quântico revelam-se, portanto, na *forma como* essa chamada é chamada a Q# ser executada, e de que forma quaisquer resultados são devolvidos.
Mais especificamente, as diferenças giram em torno 
1. indicando qual Q# é a chamada a executar,
2. como potenciais argumentos caláveis são fornecidos,
3. especificando a máquina-alvo em que executá-la, e
4. como quaisquer resultados são devolvidos.

Primeiro, discutimos como isto é feito com a Q# aplicação autónoma a partir do pedido de comando, e depois procedemos à utilização de programas de anfitriões Python e C#.
Reservamos a aplicação autónoma de Q# Cadernos Jupyter para o final, porque ao contrário dos três primeiros, a sua funcionalidade primária não se centra em torno de um Q# arquivo local.

> [!NOTE]
> Embora não o ilustremos nestes exemplos, uma comunhão entre os métodos de execução é que quaisquer mensagens impressas a partir de dentro do Q# programa (por [`Message`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) exemplo) serão normalmente impressas na respetiva consola.

## <a name="no-locq-from-the-command-prompt"></a>Q# a partir da pronta de comando
Uma das formas mais fáceis de começar a escrever Q# programas é evitar preocupar-se com ficheiros separados e uma segunda língua completamente.
A utilização do Visual Studio Code ou do Visual Studio com a extensão QDK permite um fluxo de trabalho sem emenda no qual executamos Q# callables a partir de apenas um Q# ficheiro.

Para isso, vamos, em última análise, invocar a execução do programa entrando
```dotnetcli
dotnet run
```
no pedido de comando.
O fluxo de trabalho mais simples é quando a localização do diretório do terminal é a mesma que o Q# ficheiro, que pode ser facilmente manuseado ao lado Q# da edição de ficheiros utilizando o terminal integrado no Código VS, por exemplo.
No entanto, o [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) aceita inúmeras opções, e o programa também pode ser executado a partir de um local diferente, simplesmente fornecendo `--project <PATH>` a localização do Q# ficheiro.


### <a name="add-entry-point-to-no-locq-file"></a>Adicionar ponto de entrada para Q# arquivar

A maioria dos Q# ficheiros conterá mais do que uma chamada, por isso, naturalmente, precisamos de informar o compilador *sobre qual* a chamada a executar quando fornecessarmos o `dotnet run` comando.
Isto é feito com uma simples alteração ao Q# próprio ficheiro: 
    - adicionar uma linha com `@EntryPoint()` diretamente precedendo o callable.

Nosso arquivo de cima seria, portanto, tornar-se
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

Agora, uma chamada `dotnet run` do pedido de comando leva a ser `MeasureSuperposition` executado, e o valor devolvido é então impresso diretamente para o terminal.
Então, verá um `One` ou `Zero` impresso. 

Note que não importa se tiver mais chamadas definidas abaixo, apenas `MeasureSuperposition` será executado.
Além disso, não é problema se a sua chamada inclui comentários de [documentação](xref:microsoft.quantum.guide.filestructure#documentation-comments) antes da sua declaração, o `@EntryPoint()` atributo pode simplesmente ser colocado acima deles.

### <a name="callable-arguments"></a>Argumentos insutilizáveis

Até agora, só consideramos uma operação que não tem entradas.
Suponha que quiséssemos realizar uma operação semelhante, mas em múltiplos qubits---o número do qual é fornecido como argumento.
Tal operação poderia ser escrito como
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
onde o valor devolvido é um conjunto dos resultados da medição.
Note que [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) e [`ForEach`](xref:microsoft.quantum.arrays.foreach) estão nos [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) espaços e [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) nomes, exigindo declarações adicionais `open` para cada um.

Se movermos o `@EntryPoint()` atributo para preceder esta nova operação (note que só pode haver uma dessas linhas num ficheiro), tentar executá-lo simplesmente `dotnet run` resulta numa mensagem de erro que indica quais as opções adicionais da linha de comando e como expressá-las.

O formato geral da linha de comando é, na `dotnet run [options]` verdade, e os argumentos callable são fornecidos lá.
Neste caso, falta o `n` argumento, e mostra que temos de fornecer a opção. `-n <n>` Para correr `MeasureSuperpositionArray` para `n=4` qubits, portanto usamos

```dotnetcli
dotnet run -n 4
```

produzindo uma saída semelhante a

```output
[Zero,One,One,One]
```

Isto, naturalmente, estende-se a múltiplos argumentos.

> [!NOTE]
> Os nomes de argumentos `camelCase` definidos são ligeiramente alterados pelo compilador para serem aceites como Q# entradas. Por exemplo, se em vez `n` de, nós usamos o nome `numQubits` acima, então esta entrada seria fornecida na linha de comando via `--num-qubits 4` em vez de `-n 4` .

A mensagem de erro também fornece outras opções que podem ser usadas, incluindo como alterar a máquina-alvo.

### <a name="different-target-machines"></a>Diferentes máquinas-alvo

Como as saídas das nossas operações até agora têm sido os resultados esperados da sua ação em qubits reais, é claro que a máquina-alvo padrão da linha de comando é o simulador quântico de estado completo, `QuantumSimulator` .
No entanto, podemos instruir os callables a serem executados numa máquina-alvo específica com a opção `--simulator` (ou a abreviatura). `-s`

Por exemplo, poderíamos executá-lo [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) em:

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

A saída impressa é então

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

Para obter mais informações sobre o que estas métricas indicam, consulte [o estimador de recursos: métricas reportadas](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).

### <a name="command-line-execution-summary"></a>Resumo da execução da linha de comando
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a>Q# `dotnet run` Não-opções

Como mencionamos brevemente acima com a `--project` opção, o [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) também aceita opções não relacionadas com os Q# argumentos caláveis.
Se fornecer ambos os tipos de opções, as `dotnet` opções específicas devem ser fornecidas primeiro, seguidas por um delimetro `--` , e depois as Q# opções específicas.
Por exemplo, especificar um caminho juntamente com um número de qubits para a operação acima seria executado via `dotnet run --project <PATH> -- -n <n>` .

## <a name="no-locq-with-host-programs"></a>Q# com programas de anfitrião

Com o nosso Q# ficheiro na mão, uma alternativa para chamar uma operação ou funcionar diretamente a partir do pedido de comando é usar um *programa de anfitrião* em outra língua clássica. Especificamente, isto pode ser feito com python ou uma língua .NET como C# ou F# (por uma questão de brevidade só vamos detalhar C# aqui).
É necessário um pouco mais de configuração para permitir a interoperabilidade, mas esses detalhes podem ser encontrados nos [guias de instalação](xref:microsoft.quantum.install).

Em resumo, a situação agora inclui um ficheiro de programa de anfitrião (por `*.py` exemplo, `*.cs` ou) no mesmo local que o nosso Q# ficheiro.
É agora o programa *de anfitrião* que é executado, e no decorrer da sua execução pode chamar Q# operações e funções específicas do Q# arquivo.
O núcleo da interoperabilidade baseia-se no Q# compilador que torna o conteúdo do Q# ficheiro acessível ao programa anfitrião para que possam ser chamados.

Um dos principais benefícios da utilização de um programa de anfitrião é que os dados clássicos devolvidos pelo Q# programa podem então ser processados na língua de acolhimento.
Isto poderia consistir em algum processamento avançado de dados (por exemplo, algo que não pode ser realizado internamente), e, em Q# seguida, chamar mais Q# ações com base nesses resultados, ou algo tão simples como traçar os Q# resultados.

O esquema geral é mostrado aqui, e discutimos as implementações específicas para Python e C# abaixo. Uma amostra utilizando um programa de anfitrião F# pode ser encontrada nas [amostras de interoperabilidade .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> O `@EntryPoint()` atributo utilizado para Q# aplicações não pode ser utilizado com programas de anfitrião.
> Um erro será levantado se estiver presente no Q# ficheiro sendo chamado por um anfitrião. 

Para trabalhar com diferentes programas de anfitrião, não são necessárias alterações a um `*.qs` Q# ficheiro.
As seguintes implementações do programa anfitrião funcionam com o mesmo Q# ficheiro:

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

Selecione o separador correspondente ao seu idioma de interesse anfitrião.

### <a name="python"></a>[Python](#tab/tabid-python)
Um programa de anfitrião Python é construído da seguinte forma:
1. Importe o `qsharp` módulo, que regista o carregador de módulos para Q# interoperabilidade. 
    Isto permite que Q# os espaços de nome apareçam como módulos Python, a partir dos quais podemos "importar" Q# callables.
    Note-se que, tecnicamente, não são os Q# próprios callables que são importados, mas sim os canhotos Python que permitem chamá-los.
    Estes comportam-se então como objetos de classes Python, nos quais usamos métodos para especificar as máquinas-alvo para enviar a operação para a execução.

2. Importe os Q# calíveis que invocaremos directamente--- neste caso, `MeasureSuperposition` `MeasureSuperpositionArray` e.
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    Com o `qsharp` módulo importado, também pode importar callables diretamente dos espaços de nome da Q# biblioteca.

3. Entre qualquer outro código Python, pode agora ligar para as chamadas em máquinas-alvo específicas e atribuir os seus retornos a variáveis (se devolverem um valor) para posterior utilização.

#### <a name="specifying-target-machines"></a>Especificar máquinas-alvo
Chamar uma operação a ser executada numa máquina-alvo específica é feita através de diferentes métodos Python no objeto importado.
Por `.simulate(<args>)` exemplo, usa o `QuantumSimulator` para executar a operação, enquanto `.estimate_resources(<args>)` o faz no `ResourcesEstimator` .

#### <a name="passing-inputs-to-q"></a>Passando entradas para Q\#
Os argumentos para a Q# chamada devem ser apresentados sob a forma de um argumento de palavra-chave, em que a palavra-chave é o nome do argumento na Q# definição de chamada.
Ou `MeasureSuperpositionArray.simulate(n=4)` seja, é válido, ao passo `MeasureSuperpositionArray.simulate(4)` que um erro.

Portanto, o programa de anfitrião Python 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

resulta numa saída como a seguinte:

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a>Utilização Q# de código de outros projetos ou pacotes

Por predefinição, o `import qsharp` comando carrega todos os `.qs` ficheiros na pasta atual e disponibiliza as suas Q# operações e funções para utilização a partir do interior do script Python.

Para carregar Q# código de outra pasta, a [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) pode ser usada para adicionar uma referência a um `.csproj` ficheiro para um projeto Q# (isto é, um projeto que faz `Microsoft.Quantum.Sdk` referência).
Este comando compilará quaisquer `.qs` ficheiros na pasta que contenha as `.csproj` sub-dobradeiras e as suas sub-dobradeiras. Também carregará novamente quaisquer pacotes referenciados através `PackageReference` ou Q# projetos referenciados através `ProjectReference` desse `.csproj` ficheiro.

Como exemplo, o seguinte código Python importa um projeto externo, referindo o seu percurso em relação à pasta atual, e invoca uma das suas Q# operações:

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

Isto resulta em saídas como as seguintes:

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

Para carregar pacotes externos que contenham Q# código, utilize a [ `qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).

Se o Q# código da pasta atual depender de projetos ou pacotes externos, poderá ver erros ao executar , uma vez que as `import qsharp` dependências ainda não foram carregadas.
Para carregar os pacotes ou projetos externos necessários Q# durante o `import qsharp` comando, certifique-se de que a pasta com o script Python contém um `.csproj` ficheiro que faz referências `Microsoft.Quantum.Sdk` . Nisso, `.csproj` adicione a propriedade ao `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` `<PropertyGroup>` . Isto instrui-me Q# a carregar novamente quaisquer `ProjectReference` ou `PackageReference` itens encontrados nele `.csproj` durante o `import qsharp` comando.

Por exemplo, aqui está um ficheiro simples `.csproj` que faz com que eu Q# carregue automaticamente a `Microsoft.Quantum.Chemistry` embalagem:

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> Atualmente esta propriedade personalizada `<IQSharpLoadAutomatically>` é exigida pelos anfitriões Python, mas no futuro, este pode tornar-se o comportamento padrão para um `.csproj` ficheiro localizado na mesma pasta que o script Python.

> [!NOTE]
> Atualmente, a `<QsharpCompile>` definição no `.csproj` é ignorada pelos anfitriões Python, e todos os `.qs` ficheiros na pasta das `.csproj` sub-dobras (incluindo sub-24) são carregados e compilados. O suporte para `.csproj` definições será melhorado no futuro (ver [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) para mais detalhes).


### <a name="c"></a>[C#](#tab/tabid-csharp)

Um programa de anfitrião C# tem vários componentes, e funciona muito de perto com alguns componentes do QDK, como os simuladores, que são eles próprios construídos em C#.

O Q# compilador funciona aqui gerando um espaço de nome C# do espaço de Q# nomes no nosso Q# ficheiro.
Gera ainda uma classe C# de nome equivalente para cada uma das Q# ligas ou tipos neles definidos.

Em primeiro lugar, disponibilizamos todas as aulas usadas no nosso programa de anfitriões com `using` declarações, que são aproximadamente analagous às `open` declarações no nosso Q# ficheiro:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

Em seguida, declaramos o nosso espaço de nome C#, algumas outras peças (ver o bloco de código completo abaixo), e, em seguida, qualquer programação clássica que gostaríamos (por exemplo, argumentos de computação para os Q# callables).
Este último não é necessário no nosso caso, mas um exemplo de tal utilização pode ser encontrado na  [amostra de interoperabilidade .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).

#### <a name="target-machines"></a>Computadores de destino

Voltando Q# a, temos de criar uma instância de qualquer máquina alvo em que executaremos as nossas operações.

```csharp
            using var sim = new QuantumSimulator();
```

A utilização de outras máquinas-alvo é tão simples como instantanear uma diferente, embora a forma de o fazer e processar as devoluções possa ser ligeiramente diferente.
Para a brevidade, ficamos com o [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) por enquanto, e incluímos o [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [abaixo.](#including-the-resources-estimator)

Cada classe C# gerada a partir das Q# operações tem um `Run` método, o primeiro argumento que deve ser a instância-alvo da máquina.
Então, para correr `MeasureSuperposition` `QuantumSimulator` no, nós usamos `MeasureSuperposition.Run(sim)` .
Os resultados devolvidos podem então ser atribuídos a variáveis em C#:

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> O `Run` método é executado assíncroticamente porque este será o caso de hardware quântico real, e, portanto, a `await` palavra-chave bloqueia a execução até que a tarefa esteja concluída.

Se a Q# chamada não tiver quaisquer devoluções (ou seja, tem tipo de `Unit` retorno), então a execução ainda pode ser feita da mesma forma sem atribuí-la a uma variável.
Nesse caso, toda a linha seria simplesmente consistir em 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>Argumentos

Quaisquer argumentos para a Q# chamada são simplesmente passados como argumentos adicionais aferir a máquina-alvo.
Daí os resultados de `MeasureSuperpositionArray` `n=4` em qubits seria recolhido através 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

Um programa de anfitrião C# completo poderia assim parecer

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

Na localização do ficheiro C#, o programa de anfitrião pode ser executado a partir do pedido de comando, introduzindo
```dotnetcli
dotnet run
```
e neste caso verá a saída escrita para a consola semelhante a 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> Devido à interoperabilidade do compilador com espaços de nome, poderíamos, em alternativa, Q# disponibilizar os nossos callables sem a `using NamespaceName;` declaração e simplesmente combinar o título de espaço de nome C# com ele.
> Isto é, substituindo `namespace host` `namespace NamespaceName` por.

#### <a name="including-the-resources-estimator"></a>Incluindo o estimador de recursos

[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Requer uma implementação ligeiramente diferente para recuperar a saída.

Em primeiro lugar, em vez de os instantanear como uma variável com uma `using` afirmação (como fazemos com `QuantumSimulator` o), mais diretamente instantâneos objetos da classe via

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

Note que em vez de um único simulador de alvo para ser usado por múltiplas Q# operações, instantaneamente um para cada um. Isto porque os próprios objetos são modificados quando utilizados como máquinas-alvo, podendo os seus resultados ser recuperados posteriormente com o método de classe `.ToTSV()` .

Para executar as operações nos estimadores de recursos, usamos

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
e, em seguida, obter os resultados como valores separados por separados (TSV) com `estimatorSingleQ.ToTSV()` e `estimatorMultiQ.ToTSV()` .

Assim, um programa de anfitrião C# completo que faz uso de ambos `QuantumSimulator` e pode assumir o `ResourcesEstimator` formulário:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


que produziria produção semelhante a

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="no-locq-jupyter-notebooks"></a>Q# Cadernos Jupyter
Q# Os Cadernos Jupyter utilizam o Q# núcleo I, que permite definir, compilar e executar Q# callables num único caderno--- tudo ao lado de instruções, notas e outros conteúdos.
Isto significa que, embora seja possível importar e utilizar o conteúdo dos `*.qs` Q# ficheiros, estes não são necessários no modelo de execução.

Aqui, vamos detalhar como executar as Q# operações acima definidas, mas uma introdução mais ampla à utilização Q# de Cadernos Jupyter é fornecida na [Introdução e Q# Jupyter Notebooks.](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)

### <a name="defining-operations"></a>Definição de operações

Num Q# Caderno Jupyter, introduzes Q# código como nós de dentro do espaço de nome de um Q# ficheiro.

Assim, podemos permitir o acesso a callables a partir das [ Q# bibliotecas padrão](xref:microsoft.quantum.qsharplibintro) com `open` declarações para os respetivos espaços de nome.
Ao executar uma célula com tal afirmação, as definições desses espaços de nome estão disponíveis em todo o espaço de trabalho.

> [!NOTE]
> As chamadas da [Microsoft.Quantum.Intrínseca](xref:microsoft.quantum.intrinsic) e [da Microsoft.Quantum.Canon](xref:microsoft.quantum.canon) (por [`H`](xref:microsoft.quantum.intrinsic.h) exemplo, [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) e) estão automaticamente disponíveis para operações definidas dentro de células em Q# Cadernos Jupyter.
> No entanto, isso não é verdade para o código trazido a partir de ficheiros de origem externa Q# (um processo mostrado na Introdução e na [ Q# Jupyter Notebooks).](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb) 
> 

Da mesma forma, a definição de operações requer apenas escrever o Q# código e executar a célula.

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="773">

A saída enumera então essas operações, que podem ser chamadas de futuras células.

### <a name="target-machines"></a>Computadores de destino

A funcionalidade para executar operações em máquinas-alvo específicas é fornecida através de [I Q# Comandos Mágicos](xref:microsoft.quantum.guide.quickref.iqsharp).
Por exemplo, `%simulate` faz uso do , e usa o `QuantumSimulator` `%estimate` `ResourcesEstimator` :

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a Q# operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a>Passando entradas para funções e operações

Para passar entradas para as Q# operações, os argumentos podem ser passados como `key=value` pares para o comando mágico da execução.
Então, para correr `MeasureSuperpositionArray` com quatro qubits, podemos `%simulate MeasureSuperpositionArray n=4` correr:

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a Q# operation with arguments" width="773">

Este padrão pode ser usado da mesma forma com `%estimate` outros comandos de execução.

### <a name="using-no-locq-code-from-other-projects-or-packages"></a>Utilização Q# de código de outros projetos ou pacotes

Por predefinição, um Q# Bloco de Notas Jupyter carrega todos os `.qs` ficheiros da pasta atual e disponibiliza as suas Q# operações e funções para utilização a partir de dentro do caderno. O [ `%who` comando mágico](xref:microsoft.quantum.iqsharp.magic-ref.who) lista todas as operações e funções atualmente Q# disponíveis.

Para carregar Q# código de outra pasta, o comando [ `%project` mágico](xref:microsoft.quantum.iqsharp.magic-ref.project) pode ser usado para adicionar uma referência a um `.csproj` ficheiro para um projeto Q# (isto é, um projeto que faz `Microsoft.Quantum.Sdk` referência). Este comando compilará quaisquer `.qs` ficheiros na pasta que contenha as `.csproj` (e sub-dobras). Também carregará novamente quaisquer pacotes referenciados através `PackageReference` ou Q# projetos referenciados através `ProjectReference` desse `.csproj` ficheiro. 

Como exemplo, as seguintes células simulam uma Q# operação a partir de um projeto externo, onde o percurso do projeto é referenciado em relação à pasta atual:

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a Q# operation from an external project" width="773">

Para carregar pacotes externos que contenham Q# código, utilize o [ `%package` comando mágico](xref:microsoft.quantum.iqsharp.magic-ref.package).
O carregamento de um pacote também disponibilizará quaisquer comandos mágicos personalizados ou codificadores de exibição que estejam contidos em quaisquer conjuntos que façam parte do pacote.

Para carregar pacotes ou projetos externos Q# no tempo de invisibilidade do portátil, certifique-se de que a pasta do portátil contém um `.csproj` ficheiro que faz referências `Microsoft.Quantum.Sdk` . Nisso, `.csproj` adicione a propriedade ao `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` `<PropertyGroup>` . Isto instrui-me Q# para carregar novamente qualquer `ProjectReference` ou `PackageReference` itens encontrados no `.csproj` tempo de carregamento do caderno.

Por exemplo, aqui está um ficheiro simples `.csproj` que faz com que eu Q# carregue automaticamente a `Microsoft.Quantum.Chemistry` embalagem:

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> Atualmente esta propriedade personalizada `<IQSharpLoadAutomatically>` é exigida pelos Q# anfitriões do Jupyter Notebook, mas no futuro, este pode tornar-se o comportamento padrão para um `.csproj` ficheiro localizado na mesma pasta que o ficheiro do portátil.

> [!NOTE]
> Atualmente, a `<QsharpCompile>` definição no `.csproj` é ignorada pelos Q# anfitriões do Jupyter Notebook, e todos os `.qs` ficheiros na pasta das `.csproj` sub-dobras (incluindo sub-24) são carregados e compilados. O suporte para `.csproj` definições será melhorado no futuro (ver [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) para mais detalhes).
