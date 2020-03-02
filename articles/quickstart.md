---
title: Noções básicas dos programas quânticos com Q#
description: Saiba como escrever um programa quântico em Q#. Desenvolver uma aplicação de Estado de Bell com o Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 10/07/2019
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 8d3b2d7c8da39a961f4eedcc5989ad3a1e134ade
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906734"
---
# <a name="quantum-basics-with-q"></a>Noções básicas dos programas quânticos com Q#

Neste Início Rápido, mostramos como escrever um programa em Q# que manipula e mede qubits, além de demonstrar os efeitos da sobreposição e do entrelaçamento.  Este guia vai orientá-lo na instalação do QDK, na compilação do programa e na execução desse programa num simulador quântico.  

Vai escrever uma aplicação denominada Bell para demonstrar o entrelaçamento quântico.  O nome Bell refere-se aos estados de Bell, que são estados quânticos específicos de dois qubits, utilizados para representar os exemplos mais simples de sobreposição e de entrelaçamento quântico. 

## <a name="pre-requisites"></a>Pré-requisitos

Se estiver preparado para começar a programar, siga estes passos antes de continuar: 

* [Instalar](xref:microsoft.quantum.install) o Quantum Development Kit com o ambiente de desenvolvimento e a linguagem da sua preferência
* Se já tiver o QDK instalado, confirme que o [atualizou](xref:microsoft.quantum.update) para a versão mais recente

Também pode acompanhar a narrativa sem instalar o QDK e rever as descrições gerais da linguagem de programação Q# e os conceitos iniciais da computação quântica.

## <a name="demonstrating-qubit-behavior-with-q"></a>Demonstrar o comportamento dos qubits com Q#

Lembre-se da nossa [definição de qubit](xref:microsoft.quantum.overview.what#the-qubit) simples.  Enquanto os bits clássicos contêm um único valor binário como 0 ou 1, o estado de um qubit pode estar numa **sobreposição** de 0 e 1 simultaneamente.  Conceitualmente, um qubit pode ser pensado como uma direção no espaço (também conhecido como um vetor).  Um qubit pode estar em qualquer uma das possíveis direções. Os dois **estados clássicos** são as duas direções, que representam 100% de probabilidade de medir 0 e 100% de probabilidade de medir 1.  Esta representação também é visualizada mais formalmente pela [Esfera de Bloch](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).


O ato de medição produz um resultado binário e altera o estado de um qubit. A medição produz um valor binário de 0 ou 1.  O qubit vai do estado de sobreposição (qualquer direção) até um dos estados clássicos.  Depois disso, repetir a mesma medição sem nenhuma operação intermediária produz o mesmo resultado binário.  

É possível **entrelaçar** vários qubits. Quando fazemos a medição de um qubit entrelaçado, o nosso conhecimento do estado do(s) outro(s) também é atualizado.

Agora, estamos prontos para demonstrar de que forma o Q# expressa este comportamento.  Vai começar com o programa mais simples possível e compilá-lo para demonstrar a sobreposição quântica e o entrelaçamento quântico.

## <a name="setup"></a>Configuração

As aplicações desenvolvidas com o Microsoft Quantum Development Kit consiste em duas partes:

1. Um ou mais algoritmos quânticos, implementados com a linguagem de programação quântica Q#.
1. Um programa anfitrião, implementado numa linguagem de programação como Python ou C# e que serve como ponto de entrada principal e invoca operações Q# para executar um algoritmo quântico.

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Escolha uma localização para a aplicação

1. Crie um ficheiro denominado `Bell.qs`. Este ficheiro conterá o código Q#.

1. Crie um ficheiro denominado `host.py`. Este ficheiro conterá o código anfitrião Python.

#### <a name="c-command-line"></a>[Linha de Comandos C#](#tab/tabid-csharp)

1. Crie um novo projeto Q#:

    ```bash
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    Deve ver um ficheiro `.csproj`, um ficheiro Q# denominado `Operations.qs` e um ficheiro de programa anfitrião denominado `Driver.cs`

1. Mude o nome do ficheiro Q#

    ```bash
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. Criar um novo projeto

   * Abrir o Visual Studio
   * Aceda ao menu **Ficheiro** e selecione **Novo** -> **Projeto...**
   * No explorador de modelos do projeto, escreva `Q#` no campo de pesquisa e selecione o modelo `Q# Application`
   * Atribua o nome `Bell` ao projeto

1. Mude o nome do ficheiro Q#

   * Navegue até ao **Explorador de Soluções**
   * Clique com o botão direito do rato no ficheiro `Operations.qs`
   * Mude o nome para `Bell.qs`

* * *

## <a name="write-a-q-operation"></a>Escrever uma operação Q#

O nosso objetivo é preparar dois qubits num estado quântico específico, ao demonstrar como trabalhar nos qubits com Q# para alterar o estado deles e demonstrar os efeitos da sobreposição e do entrelaçamento. Vamos criar isto peça a peça para demonstrar as medições, as operações e os estados dos qubits.

**Descrição geral:**  no primeiro código abaixo, mostramos como utilizar os qubits em Q#.  Vamos apresentar duas operações, `M` e `X`, as quais transformam o estado de um qubit. 

Neste fragmento de código, é definida uma operação `Set`, que utiliza um qubit como parâmetro e outro parâmetro, `desired`, que representa o estado em que queremos que o qubit esteja.  A operação `Set` executa uma medição no qubit através da operação `M`.  Em Q#, a medição de um qubit devolve sempre `Zero` ou `One`.  Se a medição devolver um valor diferente do valor pretendido, a operação Set “inverte” o qubit, ou seja, executa uma operação `X` que altera o estado do qubit para um novo estado no qual as probabilidades de uma medição devolver `Zero` e `One` são invertidas.  Para demonstrar o efeito da operação `Set`, é adicionada uma operação `TestBellState`.  Esta operação utiliza como entrada `Zero` ou `One`, chama a operação `Set` várias vezes com essa entrada e contabiliza o número de vezes que `Zero` foi devolvido pela medição do qubit e o número de vezes que `One` foi devolvido. Como é óbvio, nesta primeira simulação da operação `TestBellState`, esperamos que o resultado mostre que todas as medições do conjunto de qubits com `Zero` como entrada de parâmetro devolva `Zero` e todas as medições de um conjunto de qubits com `One` como entrada de parâmetro devolva `One`.  Além disso, vamos adicionar código a `TestBellState` para demonstrar a sobreposição e o entrelaçamento.


### <a name="q-operation-code"></a>Código de operação Q#

1. Substitua o conteúdo do ficheiro Bell.qs pelo seguinte código:

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    Esta operação agora pode ser chamada para definir um qubit para um estado clássico, ao devolver `Zero` ou `One` 100% do tempo.  `Zero` e `One` são constantes que representam os dois únicos resultados possíveis da medição de um qubit.

    A operação `Set` mede o qubit.
    Se o qubit estiver no estado pretendido, `Set` não fará nada. Caso contrário, ao executar a operação `X`, alteramos o estado do qubit para o estado pretendido.

### <a name="about-q-operations"></a>Acerca das operações Q#

Uma operação Q# é uma sub-rotina quântica. Ou seja, é uma rotina que pode ser chamada que contém operações quânticas.

Os argumentos para uma operação são especificados como uma cadeia de identificação, entre parênteses.

O tipo de retorno da operação é especificado após os dois pontos. Neste caso, a operação `Set` não tem retorno, pelo qual é marcada como `Unit` de retorno. É o equivalente Q# de `unit` em F#, o que é aproximadamente análogo a `void` em C# e uma cadeia de identificação vazia (`Tuple[()]`) em Python.

Utilizou duas operações quânticas na primeira operação Q#:

* A operação [M](xref:microsoft.quantum.intrinsic.m), que mede o estado do qubit
* A operação [X](xref:microsoft.quantum.intrinsic.x), que inverte o estado do qubit

Uma operação quântica transforma o estado de um qubit. Por vezes, as pessoas falam sobre portas quânticas em vez de operações, em analogia às portas de lógica clássicas e que tem origem nos primórdios da computação quântica quando os algoritmos eram meramente uma construção teórica e visualizados como diagramas da mesma forma que os diagramas de circuito na computação clássica.

### <a name="add-q-test-code"></a>Adicionar o código de teste de Q#

1. Adicione a seguinte operação ao ficheiro `Bell.qs`, dentro do espaço de nomes, após o fim da operação `Set`:

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    Esta operação (`TestBellState`) vai gerar um ciclo de `count` iterações, definir um valor `initial` especificado num qubit e, em seguida, medir (`M`) o resultado. Vai recolher estatísticas sobre quantos zeros e uns foram medidos e devolvê-los ao autor da chamada. E, executa ainda outra operação necessária. Redefine o qubit para um estado conhecido (`Zero`) antes de o devolver, o que permitirá que outros aloquem este qubit num estado conhecido. Esta operação é exigida pela instrução `using`.

### <a name="about-variables-in-q"></a>Acerca das variáveis em Q#

Por predefinição, as variáveis Q# são imutáveis; o valor dessas variáveis não pode ser alterado após serem vinculadas. A palavra-chave `let` é utilizada para indicar a vinculação de uma variável imutável. Os argumentos da operação são sempre imutáveis.

Se precisar de uma variável cujo valor pode ser alterado, como `numOnes`, poderá declarar a variável com a palavra-chave `mutable`. Um valor de variável mutável pode ser alterado com uma instrução `set`.

Em ambos os casos, o tipo de variável é inferido pelo compilador. A Q# não requer nenhum tipo de anotação para as variáveis.

### <a name="about-using-statements-in-q"></a>Acerca das instruções `using` em Q#

A instrução `using` também é especial para Q#. É utilizada para alocar qubits para utilização num bloco de código. Em Q#, todos os qubits são alocados e libertados dinamicamente, em vez de serem recursos fixos presente durante toda a duração de um algoritmo complexo. Uma instrução `using` aloca um conjunto de qubits no início e liberta esses qubits no final do bloco.

## <a name="create-the-host-application-code"></a>Criar o código da aplicação anfitriã

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Abra o ficheiro `host.py` e adicione-o ao seguinte código:

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

1. Substitua o conteúdo do ficheiro `Driver.cs` pelo código seguinte:

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a>Acerca do código da aplicação anfitriã

#### <a name="python"></a>[Python](#tab/tabid-python)

A aplicação anfitriã do Python possui três partes:

* Calcule todos os argumentos necessários do algoritmo quântico. No exemplo, o argumento `count` foi fixado em 1000 e `initial` é o valor inicial do qubit.
* Execute o algoritmo quântico ao chamar o método `simulate()` da operação Q# importada.
* Processe o resultado da operação. No exemplo, `res` recebe o resultado da operação. Aqui, o resultado é uma cadeia de identificação do número de zeros (`num_zeros`) e do número de uns (`num_ones`) medidos pelo simulador. Vamos desconstruir a cadeia de identificação para obter dois campos e imprimir os resultados.

#### <a name="c"></a>[C#](#tab/tabid-csharp)

A aplicação anfitriã C# possui quatro partes:

* Construa um simulador quântico. No exemplo, `qsim` é o simulador.
* Calcule todos os argumentos necessários do algoritmo quântico. No exemplo, o argumento `count` foi fixado em 1000 e `initial` é o valor inicial do qubit.
* Execute o algoritmo quântico. Cada operação Q# gera uma classe C# com o mesmo nome. Esta classe possui um método `Run` que de forma **assíncrona** executa a operação. A execução é assíncrona porque a execução no hardware real será assíncrona. Como o método `Run` é assíncrono, vamos obter a propriedade `Result`, que bloqueia a execução até que a tarefa seja concluída e devolva o resultado de forma síncrona.
* Processe o resultado da operação. No exemplo, `res` recebe o resultado da operação. Aqui, o resultado é uma cadeia de identificação do número de zeros (`numZeros`) e do número de uns (`numOnes`) medidos pelo simulador. E, é devolvido como um ValueTuple em C#. Vamos desconstruir a cadeia de identificação para obter dois campos, imprimir os resultados e aguardar que uma tecla seja premida.

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a>Compilar e executar

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Execute o seguinte comando no terminal:

    ```
    python host.py
    ```

    Este comando executa a aplicação anfitriã, que simula a operação Q#.

Os resultados devem ser:

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[Linha de Comandos/Visual Studio Code](#tab/tabid-csharp)

1. Execute o seguinte no terminal:

    ```bash
    dotnet run
    ```

    Este comando vai transferir automaticamente todos os pacotes necessários, compilar a aplicação e, em seguida, executar a linha de comandos.

1. Em alternativa, prima **F1** para abrir a Paleta de Comandos e selecione **Depurar: Iniciar sem Depuração**.
Pode ser-lhe pedido que crie um novo ficheiro ``launch.json``, onde descreve como iniciar o programa.
A predefinição ``launch.json`` deve funcionar bem para a maioria das aplicações.

Os resultados devem ser:

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. Basta premir `F5` para o programa ser compilado e executado!

Os resultados devem ser:

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

O programa será encerrado após premir uma tecla.

* * *

## <a name="prepare-superposition"></a>Preparar a sobreposição

**Descrição geral**: agora, vamos ver como o Q# expressa formas de colocar os qubits em sobreposição.  Lembre-se de que o estado de um qubit pode estar numa sobreposição de 0 e 1.  Vamos utilizar a operação `Hadamard` para esta ação. Se o qubit estiver num dos estados clássicos (em que uma medição devolve sempre `Zero` ou `One`), a operação `Hadamard` ou `H` colocará o qubit num estado em que uma medição do qubit devolverá `Zero` e `One` 50% do tempo.  Conceitualmente, o qubit pode ser pensado como estando entre `Zero` e `One`.  Agora, quando simularmos a operação `TestBellState`, veremos que os resultados vão devolver aproximadamente um número igual de `Zero` e `One` após a medição.  

Primeiro, vamos tentar inverter o qubit (se este estiver num estado `Zero`, será invertido para `One` e vice-versa). Esta inversão pode ser feita ao realizar uma operação `X` antes de o medir em `TestBellState`:

```qsharp
X(qubit);
let res = M(qubit);
```

Os resultados (após premir `F5`) são invertidos:

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

No entanto, tudo o que vimos até agora é clássico. Vamos, então, obter um resultado quântico. Para tal, só precisamos de substituir a operação `X` na execução anterior por uma operação `H` ou Hadamard. Em vez de inverter totalmente o qubit de 0 para 1, vamos invertê-lo apenas metade. As linhas substituídas em `TestBellState` agora são semelhantes ao seguinte:

```qsharp
H(qubit);
let res = M(qubit);
```

Os resultados começam a ficar mais interessantes:

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

Sempre que medimos, pedimos um valor clássico, mas o qubit encontra-se a meio entre 0 e 1 e assim obtemos (estatisticamente) 0 metade das vezes e 1 metade das vezes, o quer é conhecido como __sobreposição__ e dá-nos a nossa primeira vista real de um estado quântico.

## <a name="prepare-entanglement"></a>Preparar o entrelaçamento

**Descrição geral:**  agora, vamos ver como o Q# expressa formas de entrelaçar os qubits.  Primeiro, definimos o primeiro qubit para o estado inicial e utilizamos a operação `H` para colocá-lo em sobreposição.  Em seguida, antes de medirmos o primeiro qubit, utilizamos uma nova operação (`CNOT`), que significa Controlled-Not (Não Controlado).  O resultado da execução desta operação em dois qubits é inverter o segundo qubit se o primeiro qubit for `One`.  Agora, os dois qubits estão entrelaçados.  As nossas estatísticas para o primeiro qubit não foram alteradas (uma probabilidade de 50-50 de um `Zero` ou de um `One` após a medição), mas quando medirmos o segundo qubit, este será __sempre__ igual ao que medimos para o primeiro qubit. O nosso `CNOT` entrelaçou os dois qubits, de modo a que aquilo que acontecer a um deles, aconteça também ao outro. Se as medições fossem invertidas (a medição do segundo qubit antes do primeiro), aconteceria a mesma coisa. A primeira medida seria aleatória e a segunda estaria num passo bloqueado para a medição que tivesse sido detetada primeiro.

A primeira coisa que vamos precisar de fazer é alocar dois qubits em vez de um em `TestBellState`:

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

Este procedimento vai permitir adicionar uma nova operação (`CNOT`) antes de medir (`M`) em `TestBellState`:

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

Adicionámos outra operação `Set` para inicializar o primeiro qubit para confirmar que está sempre no estado `Zero` quando começamos.

Precisamos também de redefinir o segundo qubit antes de o libertar.

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

A rotina completa é agora semelhante ao seguinte:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

Se a executarmos, vamos obter exatamente o mesmo resultado de 50-50 que obtivemos anteriormente. No entanto, o que nos interessa é a forma como o segundo qubit reage à primeira medição. Vamos adicionar esta estatística com a nova versão da operação `TestBellState`:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

O novo valor de retorno (`agree`) controla cada vez que a medição do primeiro qubit corresponde à medição do segundo qubit. É também necessário atualizar a aplicação anfitriã em conformidade:

#### <a name="python"></a>[Python](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

Agora, quando executarmos, vamos obter um resultado incrível:

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

Conforme mencionado na descrição geral, as nossas estatísticas para o primeiro qubit não foram alteradas (uma probabilidade de 50-50 de um 0 ou de um 1), mas quando medirmos o segundo qubit, este será __sempre__ igual ao que medimos para o primeiro qubit, uma vez que estão entrelaçados!

Parabéns! Acabou de escrever o primeiro programa quântico.

## <a name="whats-next"></a>Passos seguintes?

O Início Rápido [Pesquisa de Grover](xref:microsoft.quantum.quickstarts.search) mostra como compilar e executar a pesquisa de Grover, um dos algoritmos de computação quântica mais populares e dá um ótimo exemplo de um programa Q# que pode ser utilizado para resolver problemas reais através de computação quântica.  

A [Introdução ao Quantum Development Kit](xref:microsoft.quantum.welcome) recomenda mais formas de aprender a linguagem Q# e a programação quântica.

