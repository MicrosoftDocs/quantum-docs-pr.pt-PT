---
title: 'Escrever e simular programas de nível qubit em Q #'
description: Tutorial passo a passo sobre a escrita e simulação de um programa quântico que opera ao nível do qubit individual
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
ms.openlocfilehash: e7ebdec4cd1aa201030d82759a3aa56473b26417
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275348"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a>Tutorial: Escreva e simula programas de nível qubit em Q\#

Bem-vindo ao tutorial do Kit de Desenvolvimento Quântico sobre a escrita e simulação de um programa quântico básico que opera em qubits individuais. 

Embora Q# tenha sido criado principalmente como uma linguagem de programação de alto nível para programas quânticos em larga escala, ele pode facilmente ser usado para explorar o nível mais baixo de programas quânticos: abordando diretamente qubits específicos.
A flexibilidade do Q# permite que os utilizadores se aproximem dos sistemas quânticos a partir de qualquer tal nível de abstração, e neste tutorial mergulhamos nos próprios qubits.
Especificamente, damos uma olhada sob o capuz da [transformação quântica de Fourier,](https://en.wikipedia.org/wiki/Quantum_Fourier_transform)uma sub-rotina que é parte integrante de muitos algoritmos quânticos maiores.

Note-se que esta visão de baixo nível do processamento de informação quântica é frequentemente descrita em termos de "[circuitos quânticos](xref:microsoft.quantum.concepts.circuits)", que representam a aplicação sequencial dos portões a qubits específicos de um sistema.

Assim, as operações de mono e múltiplos qubits que aplicamos sequencialmente podem ser facilmente representadas num "diagrama de circuito".
No nosso caso, definiremos uma operação Q# para executar a transformação completa de Fourier quântico de três qubits, que tem a seguinte representação como circuito:

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a>Pré-requisitos

* [Instale](xref:microsoft.quantum.install) o Kit de Desenvolvimento Quântico utilizando o seu ambiente de linguagem e desenvolvimento preferido.
* Se já tiver o QDK instalado, confirme que o [atualizou](xref:microsoft.quantum.update) para a versão mais recente


## <a name="in-this-tutorial-youll-learn-how-to"></a>Neste tutorial, ficará a saber como:

> [!div class="checklist"]
> * Definir operações quânticas em Q #
> * Ligue para as operações Q# diretamente da linha de comando ou usando um programa de anfitrião clássico
> * Simular uma operação quântica da alocação de qubits à saída de medição
> * Observe como a simulação de função de onda do sistema quântico evolui ao longo da operação

Executar um programa quântico com o Kit de Desenvolvimento Quântico da Microsoft é normalmente composto por duas partes:
1. O programa em si, que é implementado usando a linguagem de programação quântica Q#, e depois invocado para funcionar em um computador quântico ou simulador quântico. Estes consistem de 
    - Q# operações: sub-rotinas agindo em registos quânticos, e 
    - Funções Q#: sub-rotinas clássicas utilizadas dentro do algoritmo quântico.
2. O ponto de entrada utilizado para chamar o programa quântico e especificar a máquina-alvo na qual deve ser executado.
    Isto pode ser feito diretamente a partir da linha de comando, ou através de um programa de anfitrião escrito em uma linguagem de programação clássica como Python ou C#.
    Este tutorial inclui instruções para o método que preferir.

## <a name="allocate-qubits-and-define-quantum-operations"></a>Alocar qubits e definir operações quânticas

A primeira parte deste tutorial consiste em definir a operação `Perform3qubitQFT` Q#, que executa a transformação quântica de Fourier em três qubits. 

Além disso, usaremos a [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) função para observar como a simulação de função de onda do nosso sistema de três qubits evolui em toda a operação.

O primeiro passo é criar o seu projeto q# e arquivo.
Os passos para tal dependem do ambiente que utilizará para ligar para o programa, podendo encontrar os detalhes nos [respetivos guias de instalação.](xref:microsoft.quantum.install)

Vamos acompanhá-lo através dos componentes do ficheiro passo a passo, mas o código também está disponível como um bloco completo abaixo.

### <a name="namespaces-to-access-other-q-operations"></a>Espaços de nome para aceder a outras operações Q#
Dentro do ficheiro, primeiro definimos o espaço de nome `NamespaceQFT` que será acedido pelo compilador.
Para a nossa operação de fazer uso das operações Q# existentes, abrimos os `Microsoft.Quantum.<>` espaços de nome relevantes.

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a>Definir operações com argumentos e devoluções
Em seguida, definimos a `Perform3qubitQFT` operação:

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

Para já, a operação não aceita argumentos e não devolve nada--- neste caso escrevemos que devolve um `Unit` objeto, que é semelhante a `void` C# ou um tuple vazio, `Tuple[()]` em Python.
Mais tarde, vamos modificá-lo para devolver uma série de resultados de medição, altura em que `Unit` será substituído por `Result[]` . 

### <a name="allocate-qubits-with-using"></a>Alocar qubits com`using`
Dentro da nossa operação Q#, atribuímos primeiro um registo de três qubits com a `using` declaração:

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

Com `using` , os qubits são automaticamente atribuídos no estado $\ket {0} $. Podemos verificar isto utilizando [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) e [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , que imprimimos uma cadeia e o estado atual do sistema para a consola.

> [!NOTE]
> As `Message(<string>)` `DumpMachine()` funções (de [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) e, respectivamente) são ambas impressas diretamente para a consola. Assim como uma computação quântica real, Q# não nos permite aceder diretamente a estados qubit.
> No entanto, à medida `DumpMachine` que imprime o estado atual da máquina-alvo, pode fornecer informações valiosas para depurar e aprender quando usado em conjunto com o simulador de estado completo.


### <a name="applying-single-qubit-and-controlled-gates"></a>Aplicação de portões mono-qubit e controlados

Em seguida, aplicamos os portões que compõem a própria operação.
Q# já contém muitos portões quânticos básicos como operações no [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) espaço de nome, e estes não são exceção. 

Dentro de uma operação Q#, as declarações invocando callables serão, naturalmente, executadas por ordem sequencial.
Assim, o primeiro portão a aplicar é o [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) ao primeiro qubit:

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

Para aplicar uma operação a um qubit específico a partir de um registo (isto é, um único `Qubit` de uma matriz ), `Qubit[]` usamos a notação de índice padrão.
Assim, a aplicação [`H`](xref:microsoft.quantum.intrinsic.h) do primeiro qubit do nosso registo `qs` assume o formulário:

```qsharp
            H(qs[0]);
```

Além de aplicar o `H` portão (Hadamard) a qubits individuais, o circuito QFT consiste principalmente em [`R1`](xref:microsoft.quantum.intrinsic.r1) rotações controladas.
Uma `R1(θ, <qubit>)` operação em geral deixa inalterado o componente $\ket {0} $ do qubit, ao mesmo tempo que aplica uma rotação de $e^{i\theta}$ para o componente $\ket {1} $.

#### <a name="controlled-operations"></a>Operações controladas

Q# torna extremamente fácil condicionar a execução de uma operação em um ou múltiplos qubits de controlo.
Em geral, limitamo-nos a prefaciar a chamada `Controlled` com, e os argumentos da operação mudam como:

 `Op(<normal args>)`$\a$ `Controlled Op([<control qubits>], (<normal args>))` a$ .

Note que os qubits de controlo devem ser fornecidos como uma matriz, mesmo que seja um único qubit.

Depois do `H` , vemos que os portões seguintes são os `R1` portões agindo no primeiro qubit (e controlados pelo segundo/terceiro):

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

Chamamos isto com

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

Note que usamos a [`PI()`](xref:microsoft.quantum.math.pi) função do [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) espaço de nome para definir as rotações em termos de raios pi.
Além disso, dividimo-nos por um `Double` (por `2.0` exemplo) porque dividir por um inteiro `2` lançaria um erro tipo. 

> [!TIP]
> `R1(π/2)`e `R1(π/4)` são equivalentes às `S` `T` operações (também em `Microsoft.Quantum.Intrinsic` ).


Após a aplicação das `H` operações pertinentes e das rotações controladas ao segundo e terceiro qubits:

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

só precisamos de aplicar um [`SWAP`](xref:microsoft.quantum.intrinsic.swap) portão para completar o circuito:

```qsharp
            SWAP(qs[2], qs[0]);
```

Isto é necessário porque a natureza do Quantum Fourier transforma as saídas dos qubits em ordem inversa, de modo que os swaps permitem uma integração perfeita da subbroutina em algoritmos maiores.

Assim, terminamos de escrever as operações de nível qubit do Quantum Fourier transformam-se na nossa operação Q# :

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

No entanto, não podemos encerrar o dia ainda.
Os nossos qubits estavam no estado $\ket {0} $ quando os atribuímos, e tal como na vida, em Q# devemos deixar as coisas da mesma forma que as encontramos (ou melhor!).

### <a name="deallocate-qubits"></a>Qubits de deallocate

Ligamos [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) novamente para ver o estado pós-operação, e finalmente aplicamo-nos ao registo qubit para redefinir os [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) nossos qubits para $\ket {0} $ antes de concluir a operação:

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

Exigir que todos os qubits deallocados sejam explicitamente definidos para $\ket {0} $ é uma característica básica de Q#, pois permite que outras operações conheçam o seu estado precisamente quando começam a usar esses mesmos qubits (um recurso escasso).
Além disso, isto garante que não se enredam com quaisquer outros qubits no sistema.
Se o reset não for efetuado no final de um bloco de `using` atribuição, será lançado um erro de tempo de execução.

O seu ficheiro Q# completo deve agora ser assim:

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


Com o ficheiro Q# e a operação concluídos, o nosso programa quântico está pronto para ser chamado e simulado.

## <a name="execute-the-program"></a>Execute o programa

Tendo definido a nossa operação Q# num `.qs` ficheiro, precisamos agora ligar para essa operação e observar quaisquer dados clássicos devolvidos.
Por enquanto, não há nada devolvido (lembre-se que a nossa operação definida acima de `Unit` voltas), mas quando mais tarde modificarmos a operação Q# para devolver uma série de resultados de medição ( `Result[]` ), iremos abordar isto.

Embora o programa Q# seja omnipresente em todos os ambientes usados para chamá-lo, a maneira de fazê-lo vai naturalmente variar. Como tal, basta seguir as instruções no separador correspondente à sua configuração: trabalhar a partir da aplicação da linha de comando Q# ou utilizar um programa de anfitrião em Python ou C#.

#### <a name="command-line"></a>[Linha de comandos](#tab/tabid-cmdline)

Executar o programa Q# a partir da linha de comando requer apenas uma pequena alteração no ficheiro Q#.

Basta adicionar `@EntryPoint()` a uma linha anterior à definição de operação:

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

Para executar o programa, abra o terminal na pasta do seu projeto e insira

```dotnetcli
dotnet run
```

Após a execução, deverá ver as `Message` saídas e `DumpMachine` saídas abaixo impressas na sua consola.


#### <a name="python"></a>[Python](#tab/tabid-python)

Criar um ficheiro de hospedeiro Python: `host.py` .

O ficheiro do anfitrião é construído da seguinte forma: 
1. Primeiro, importamos o `qsharp` módulo, que regista o carregador de módulos para interoperabilidade Q#. 
    Isto permite que os espaços de nome Q# (por exemplo, o `NamespaceQFT` que definimos no nosso ficheiro Q#) apareçam como módulos Python, a partir dos quais podemos importar operações Q#.
2. Em seguida, importe as operações Q# que iremos invocar directamente--- neste caso, `Perform3qubitQFT` .
    Só precisamos de importar o ponto de entrada num programa Q# _(isto_ é, não operações como `H` e , que são chamadas por `R1` outras operações Q# mas nunca pelo anfitrião clássico).
3. Ao simular operações ou funções Q# utilize o formulário `<Q#callable>.simulate(<args>)` para executá-los na `QuantumSimulator()` máquina-alvo. 

> [!NOTE]
> Se quiséssemos chamar a operação para uma máquina diferente, por `ResourceEstimator()` exemplo, usaríamos `<Q#callable>.estimate_resources(<args>)` simplesmente.
> Em geral, as operações Q# são agnósticas para as máquinas em que são executadas, mas algumas características como `DumpMachine` podem comportar-se de forma diferente.

4. Após a realização da simulação, a chamada de operação devolverá valores conforme definido no ficheiro Q#.
    Por enquanto não há nada devolvido, mas mais tarde veremos um exemplo de atribuição e processamento destes valores.
    Com os dados resultantes nas nossas mãos e totalmente clássicos, podemos fazer o que quisermos com ele.

O seu ficheiro completo `host.py` deve ser o seguinte:

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

Execute o ficheiro Python e impresso na sua consola deve ver as `Message` saídas e `DumpMachine` saídas abaixo. 


#### <a name="c"></a>[C#](#tab/tabid-csharp)

Seguindo as mesmas instruções que no [guia de instalação,](xref:microsoft.quantum.install.cs)crie um ficheiro de anfitrião C# e rebatize-o para `host.cs` .

O anfitrião C# tem quatro partes:
1. Construa um simulador quântico.
    No código abaixo, esta é a `qsim` variável.
2. Calcule todos os argumentos necessários do algoritmo quântico.
    Não há nenhum neste exemplo.
3. Execute o algoritmo quântico. 
    Cada operação Q# gera uma classe C# com o mesmo nome. 
    Esta classe possui um método `Run` que de forma **assíncrona** executa a operação.
    A execução é assíncrona porque a execução no hardware real será assíncrona. 
    Como o `Run` método é assíncrona, chamamos o `Wait()` método; isto bloqueia a execução até que a tarefa complete e retorne o resultado de forma sincronizada. 
4. Processe o resultado devolvido da operação.
    Por enquanto, a operação não devolve nada.


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
Executar a aplicação, e a sua saída deve corresponder a baixo.
O programa será encerrado após premir uma tecla.
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

Quando chamado ao simulador de estado inteiro, `DumpMachine()` fornece estas representações mutliple da função de onda do estado quântico. Os possíveis estados de um sistema de $n$-qubit podem ser representados por $2^n$ estados de base computacional, cada um com um coeficiente complexo correspondente (simplesmente uma amplitude e uma fase).
Os estados de base computacional correspondem a todas as possíveis cadeias binárias de comprimento $n$--- ou seja, todas as combinações possíveis de qubits estados $\ket {0} $ e $\ket {1} $, onde cada dígito binário corresponde a um qubit individual.

A primeira linha fornece um comentário com os IDs dos qubits correspondentes na sua ordem significativa.
Qubit `2` ser o "mais significativo" significa simplesmente que na representação binária do vetor de estado de base $\ket{i}$, o estado do qubit `2` corresponde ao dígito mais à esquerda. Por exemplo, $\ket {6} = \ket {110} $ inclui qubits `2` e ambos em `1` $\ket {1} $ e qubit em `0` $\ket {0} $.


As restantes linhas descrevem a amplitude de probabilidade de medir o vetor de estado base $\ket{i}$ em formatos cartesianos e polares.
Em detalhe para a primeira linha do nosso estado de entrada $\ket {000} $:
* **`|0>:`** esta linha corresponde ao `0` estado de base computacional (dado que a nossa pós-atribuição inicial do Estado era $\ket {000} $, esperamos que este seja o único estado com amplitude de probabilidade neste momento).
* **`1.000000 +  0.000000 i`**: a amplitude de probabilidade no formato cartesiano.
* **` == `**: o `equal` sinal separa ambas as representações equivalentes.
* **`********************`**: Uma representação gráfica da magnitude, o número `*` de é proporcional à probabilidade de medir este vetor de estado. 
* **`[ 1.000000 ]`**: o valor numérico da magnitude
* **`    ---`**: Uma representação gráfica da fase da amplitude.
* **`[ 0.0000 rad ]`**: o valor numérico da fase (em radianos).

Tanto a magnitude como a fase são exibidas com uma representação gráfica. A representação de magnitude é simples: mostra uma barra de `*` , e quanto maior a probabilidade, maior será a barra. Para a fase, consulte [Teste e depuração: funções de despejo](xref:microsoft.quantum.guide.testingdebugging#dump-functions) para as possíveis representações de símbolos baseadas em intervalos de ângulo.


Assim, a saída impressa está ilustrando que os nossos portões programados transformaram o nosso estado de

$$ \ket{\psi} \_ {initial} = \ket {000} $$

para 

$$ \start{align} \ket{\psi} \_ {final} &= \frac {1} {\sqrt {8} } \ket {000} + \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket + \ket + \ket + \ket + \ket + \ket {101} + \ket {110} + \ket {111} \ket \right) \\ \\ &= \frac {1} {\sqrt{2^n}}\sum \_ {j=0}^{2^n-1} \ket{j}, \end{align} $$

que é precisamente o comportamento da transformação de Fourier 3-qubit. 

Se está curioso sobre como outros estados de entrada são afetados, encorajamo-lo a brincar com a aplicação de operações de qubit antes da transformação.

## <a name="adding-measurements"></a>Adição de medições

Infelizmente, uma pedra angular da mecânica quântica diz-nos que um verdadeiro sistema quântico não pode ter tal `DumpMachine` função. Em vez disso, somos forçados a extrair informação através de medições, que em geral não só não nos fornecem todo o estado quântico, como também podem alterar drasticamente o próprio sistema.
Existem muitos tipos de medições quânticas, mas vamos focar-nos nas mais básicas: medições projetivas em qubits únicos.
Após a medição numa determinada base (por exemplo, a base computacional $ \{ \ket {0} , \ket {1} \} $), o estado qubit é projetado para qualquer estado base medido---hence destruindo qualquer superposição entre os dois.

Para implementar medições dentro de um programa Q#, utilizamos a `M` operação (a partir `Microsoft.Quantum.Intrinsic` de), que devolve um `Result` tipo.

Primeiro, modificamos a nossa `Perform3QubitQFT` operação para devolver uma série de resultados de medição, `Result[]` em vez de `Unit` .

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a>Definir e inicializar `Result[]` matriz

Antes mesmo de atribuir qubits (isto é, antes da `using` declaração), declaramos e ligamos este comprimento-3 matriz (um `Result` para cada qubit): 

```qsharp
        mutable resultArray = new Result[3];
```

A `mutable` pré-criação de `resultArray` palavras-chave permite que a variável seja recuperada mais tarde no código--- por exemplo, ao adicionar os resultados da nossa medição.

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a>Executar medições em `for` loop e adicionar resultados à matriz

Depois da transformação fourier no interior do `using` bloco, insira o seguinte código:

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
A [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) função chamada numa matriz (por exemplo, a nossa matriz de qubits, `qs` ) devolve um intervalo sobre os índices da matriz. Aqui, nós o usamos no nosso `for` loop para medir sequencialmente cada qubit usando a `M(qs[i])` declaração.
Cada tipo medido `Result` `Zero` (ou `One` ou ) é adicionado à posição de índice correspondente `resultArray` com uma declaração de atualização e reatribuição.

> [!NOTE]
> A sintaxe desta afirmação é única para Q#, mas corresponde à reatribuição variável semelhante `resultArray[i] <- M(qs[i])` vista em outras línguas como F# e R.

A palavra-chave `set` é sempre usada para reatribuir variáveis ligadas através da utilização `mutable` .

#### <a name="return-resultarray"></a>Retorno`resultArray`

Com os três qubits medidos e os resultados `resultArray` adicionados, estamos seguros para repor e negociar os qubits como antes.
Depois do `using` fecho do quarteirão, insira

```qsharp
        return resultArray;
```
para, em última análise, devolver a saída da nossa operação. 

### <a name="understanding-the-effects-of-measurement"></a>Compreender os efeitos da medição

Vamos alterar a colocação das `DumpMachine` nossas funções para a saída do estado antes e depois das medições.
O código de operação final deve parecer: 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

Se estiver a trabalhar a partir da linha de comando, a matriz devolvida será simplesmente impressa diretamente para a consola no final da execução.
Caso contrário, atualize o seu programa de anfitrião para processar a matriz devolvida.

#### <a name="command-line"></a>[Linha de comandos](#tab/tabid-cmdline)

Para termos mais compreensão da matriz devolvida que será impressa na consola, podemos adicionar outra `Message` no ficheiro Q# pouco antes da `return` declaração:

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

Executar o projeto, e a sua saída deve ser semelhante ao seguinte:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[Python](#tab/tabid-python)

Atualize o seu programa Python para o seguinte:

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

Execute o ficheiro e a sua saída deve ser semelhante ao seguinte:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

Agora que a nossa operação está a devolver um resultado, substitua a chamada de método `Wait()` por ir buscar a `Result` propriedade. Isto ainda realiza a mesma sincronização discutida anteriormente, e podemos ligar diretamente este valor à `measurementResult` variável.

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

Executar o projeto, e a sua saída deve ser semelhante ao seguinte:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

Esta saída ilustra algumas coisas diferentes:
1. Comparando o resultado devolvido com a pré-medição, `DumpMachine` claramente _não_ ilustra a sobreposição pós-QFT sobre estados de base.
    Uma medição apenas devolve um único estado base, com uma probabilidade determinada pela amplitude desse estado na função de onda do sistema.
2. A partir da pós-medição, `DumpMachine` vemos que a medição _muda_ o próprio estado, projetando-o desde a sobreposição inicial sobre estados base para o estado base único que corresponde ao valor medido.

Se repetissemos esta operação muitas vezes, veríamos as estatísticas dos resultados começarem a ilustrar a superposição igualmente ponderada do estado pós-QFT que dá origem a um resultado aleatório em cada disparo.
_No entanto,_ além de ser ineficiente e ainda imperfeito, isso só reproduziria as amplitudes relativas dos estados de base, e não as fases relativas entre eles.
Este último não é um problema neste exemplo, mas veríamos fases relativas aparecerem se lhes fosse dada uma entrada mais complexa para o QFT do que $\ket {000} $.

#### <a name="partial-measurements"></a>Medições parciais 
Para explorar como a medição de apenas alguns qubits do registo pode afetar o estado do sistema, tente adicionar o seguinte dentro do `for` loop, após a linha de medição:
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

Note que para aceder à `IntAsString` função terá de adicionar 
```qsharp
    open Microsoft.Quantum.Convert;
```
com o resto das declarações do espaço de `open` nome.

Na saída resultante, você verá a projeção gradual em subespaços à medida que cada qubit é medido.


## <a name="use-the-q-libraries"></a>Use as bibliotecas Q#
Como mencionamos na introdução, grande parte do poder de Q#assenta no facto de que permite-lhe abstrair as preocupações de lidar com qubits individuais.
Na verdade, se quiser desenvolver programas quânticos em larga escala, aplicáveis, preocupar-se se uma `H` operação vai antes ou depois de uma determinada rotação só o atrasaria. 

As bibliotecas Q# contêm a operação [QFT,](xref:microsoft.quantum.canon.qft) que pode simplesmente tomar e solicitar qualquer número de qubits.
Para experimentar, defina uma nova operação no seu ficheiro Q# que tenha o mesmo conteúdo `Perform3QubitQFT` de, mas com tudo, desde o primeiro `H` até ao substituído por `SWAP` duas linhas fáceis:
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
A primeira linha simplesmente cria uma [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expressão da matriz de qubits atribuído, que é o que a `qs` operação [QFT](xref:microsoft.quantum.canon.qft) toma como argumento.
Isto corresponde à ordem de índice dos qubits no registo.

Para ter acesso a estas operações, adicione `open` declarações para os respetivos espaços de nome no início do ficheiro Q#:
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

Agora, ajuste o seu programa de anfitrião para chamar o nome da sua nova operação (por `PerformIntrinsicQFT` exemplo), e dê-lhe um giro.

Para ver o verdadeiro benefício da utilização das operações da biblioteca Q, altere o número de qubits para outra coisa que `3` não:
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
Pode assim aplicar o QFT adequado para qualquer número de qubits, sem ter que se preocupar com a confusão de novas `H` operações e rotações em cada qubit.

Note que o simulador quântico leva exponencialmente mais tempo para correr à medida que aumenta o número de qubits---precisamente por que esperamos por hardware quântico real!













