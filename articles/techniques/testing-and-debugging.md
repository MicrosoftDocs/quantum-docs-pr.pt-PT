---
title: 'Técnicas de Q # – testando e Depurando | Microsoft Docs'
description: 'Técnicas de Q # – teste e depuração'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: d352ffa315b654cfcf8991fa116465d3dad49f0a
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864275"
---
# <a name="testing-and-debugging"></a>Testando e Depurando

Assim como acontece com a programação clássica, é essencial poder verificar se os programas Quantum atuam como pretendidos e ser capaz de diagnosticar um programa Quantum incorreto.
Nesta seção, abordaremos as ferramentas oferecidas por Q # para testar e depurar programas Quantum.

## <a name="unit-tests"></a>Testes da unidade

Uma abordagem comum para testar programas clássicos é escrever programas pequenos chamados *testes de unidade* que executam código em uma biblioteca e comparam sua saída a alguma saída esperada.
Por exemplo, talvez queiramos garantir que `Square(2)` retorna `4`, já que sabemos *um priori* de que $2 ^ 2 = $4.

O Q # dá suporte à criação de testes de unidade para programas Quantum e que pode ser executado como testes dentro da estrutura de teste de unidade do [xUnit](https://xunit.github.io/) .

### <a name="creating-a-test-project"></a>Criando um projeto de teste

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Abra o Visual Studio 2019. Vá para o menu `File` e selecione `New` > `Project...`.
No canto superior direito, pesquise `Q#`e selecione o modelo de `Q# Test Project`.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Linha de Comandos/Visual Studio Code](#tab/tabid-vscode)

Na sua linha de comando favorita, execute o seguinte comando:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Seu novo projeto terá um único arquivo `Tests.qs`, que fornece um local conveniente para definir novos testes de unidade Q #.
Inicialmente, esse arquivo contém um teste de unidade de exemplo `AllocateQubit` que verifica se um qubit alocado recentemente está no estado $ \ket{0}$ e imprime uma mensagem:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

: New: qualquer operação ou função Q # que usa um argumento do tipo `Unit` e retorna `Unit` pode ser marcada como um teste de unidade por meio do atributo `@Test("...")`. O argumento para esse atributo, `"QuantumSimulator"` acima, especifica o destino no qual o teste é executado. Um único teste pode ser executado em vários destinos. Por exemplo, adicione um atributo `@Test("ResourcesEstimator")` acima `AllocateQubit`. 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Salve o arquivo e execute todos os testes. Agora deve haver dois testes de unidade, um em que AllocateQubit é executado no QuantumSimulator e um onde ele é executado no ResourceEstimator. 

O compilador Q # reconhece os destinos internos "QuantumSimulator", "ToffoliSimulator" e "ResourcesEstimator" como destinos de execução válidos para testes de unidade. Também é possível especificar qualquer nome totalmente qualificado para definir um destino de execução personalizado. 

### <a name="running-q-unit-tests"></a>Executando os testes de unidade de Q #

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Como configuração única por solução, vá para `Test` menu e selecione `Test Settings` > `Default Processor Architecture` > `X64`.

> [!TIP]
> A configuração de arquitetura de processador padrão para o Visual Studio é armazenada no arquivo de opções de solução (`.suo`) para cada solução.
> Se você excluir esse arquivo, será necessário selecionar `X64` como a arquitetura do processador novamente.

Compile o projeto, vá para o menu de `Test` e selecione `Windows` > `Test Explorer`. `AllocateQubit` aparecerá na lista de testes no grupo de `Not Run Tests`. Selecione `Run All` ou execute este teste individual e ele deve passar!

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Linha de Comandos/Visual Studio Code](#tab/tabid-vscode)

Para executar testes, navegue até a pasta do projeto (a pasta que contém `Tests.csproj`) e execute o comando:

```bash
$ dotnet restore
$ dotnet test
```

Você deve obter uma saída semelhante à seguinte:

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

Os testes de unidade podem ser filtrados de acordo com seu nome e/ou o destino de execução:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

A função intrínseca <xref:microsoft.quantum.intrinsic.message> tem o tipo `(String -> Unit)` e habilita a criação de mensagens de diagnóstico.

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Depois de executar um teste no Test Explorer e clicar no teste, um painel será exibido com informações sobre a execução do teste: passou/falha no status, tempo decorrido e um link de "saída". Se você clicar no link "saída", a saída de teste será aberta em uma nova janela.

![saída de teste](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Linha de Comandos/Visual Studio Code](#tab/tabid-vscode)

O status de aprovação/reprovação de cada teste é impresso no console do por `dotnet test`.
Para testes com falha, as saídas também são impressas no console do para ajudar a diagnosticar a falha.

***

## <a name="assertions"></a>Declarações

Como as funções em Q # não têm efeitos colaterais _lógicos_ , quaisquer _outros tipos_ de efeitos de execução de uma função cujo tipo de saída é a tupla vazia `()` nunca podem ser observados em um programa Q #.
Ou seja, um computador de destino pode optar por não executar nenhuma função que retorne `()` com a garantia de que essa omissão não modificará o comportamento de qualquer código Q # a seguir.
Isso faz com que as funções retornem `()` uma ferramenta útil para incorporar asserções e depurar a lógica em programas Q #. 

A mesma lógica pode ser aplicada à implementação de asserções. Vamos considerar um exemplo simples:

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

Aqui, a palavra-chave `fail` indica que a computação não deve continuar, gerando uma exceção no computador de destino que executa o programa Q #.
Por definição, uma falha desse tipo não pode ser observada em Q #, pois nenhum código Q # adicional é executado depois que uma instrução `fail` é atingida.
Portanto, se continuarmos passando por uma chamada para `AssertPositive`, poderemos ter certeza de que sua entrada era positiva.

Com base nessas ideias, [o prelúdio](xref:microsoft.quantum.libraries.standard.prelude) oferece duas declarações especialmente úteis, <xref:microsoft.quantum.intrinsic.assert> e <xref:microsoft.quantum.intrinsic.assertprob> modeladas como operações em `()`. Cada declaração assume um operador Pauli que descreve uma medida de interesse específica, um registro Quantum no qual uma medida deve ser executada e um resultado hipotético.
Em computadores de destino que funcionam por simulação, não estamos vinculados pelo [teorema no-Cloning](https://en.wikipedia.org/wiki/No-cloning_theorem)e podem executar essas medições sem perturbar o registro passado para tais asserções.
Um simulador pode, assim, semelhante à função `AssertPositive` acima, anular a computação se o resultado hipotético não fosse observado na prática:

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

Em hardware Quantum físico, em que o teorema sem clonagem impede o exame do estado Quantum, as operações `Assert` e `AssertProb` simplesmente retornam `()` sem nenhum outro efeito.

O namespace <xref:microsoft.quantum.diagnostics> fornece várias outras funções da família `Assert`, que nos permitem verificar condições mais avançadas. 

## <a name="dump-functions"></a>Funções de despejo

Para ajudar a solucionar problemas de programas Quantum, o namespace <xref:microsoft.quantum.diagnostics> oferece duas funções que podem ser despejadas em um arquivo o status atual da máquina de destino: <xref:microsoft.quantum.diagnostics.dumpmachine> e <xref:microsoft.quantum.diagnostics.dumpregister>. A saída gerada de cada uma depende do computador de destino.

### <a name="dumpmachine"></a>DumpMachine

O simulador de Quantum completo distribuído como parte do kit de desenvolvimento Quantum grava no arquivo a [função de onda](https://en.wikipedia.org/wiki/Wave_function) de todo o sistema Quantum, como uma matriz unidimensional de números complexos, na qual cada elemento representa a amplitude da probabilidade de medir o estado de base computacional $ \ket{n} $, em que $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ para bits $\{b_i\}$. Por exemplo, em um computador com apenas dois qubits alocados e no estado Quantum $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ chamando <xref:microsoft.quantum.diagnostics.dumpmachine> gera essa saída:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

A primeira linha fornece um comentário com as IDs do qubits correspondente em sua ordem significativa.
O restante das linhas descreve a amplitude de probabilidade de medir o vetor de estado base $ \ket{n} $ nos formatos cartesianas e polar. Em detalhes para a primeira linha:

* **`∣0❭:`** essa linha corresponde ao estado de base computacional `0`
* **`0.707107 +  0.000000 i`** : a amplitude de probabilidade no formato cartesiano.
* **` == `** : o sinal de `equal` separa as representações equivalentes.
* **`**********  `** : uma representação gráfica da magnitude, o número de `*` é proporcionalmente à probabilidade de medir esse vetor de estado.
* **`[ 0.500000 ]`** : o valor numérico da magnitude
* **`    ---`** : uma representação gráfica da fase da amplitude (veja abaixo).
* **`[ 0.0000 rad ]`** : o valor numérico da fase (em radianos).

A magnitude e a fase são exibidas com uma representação gráfica. A representação de magnitude é direta: ela mostra uma barra de `*`, quanto maior a probabilidade maior será a barra. Para a fase, mostramos os seguintes símbolos para representar o ângulo com base em intervalos:

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

Os exemplos a seguir mostram `DumpMachine` para alguns Estados comuns:

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > A ID de um qubit é atribuída em tempo de execução e não está necessariamente alinhada com a ordem na qual o qubit foi alocado ou sua posição em um registro qubit.


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Você pode descobrir uma ID de qubit no Visual Studio colocando um ponto de interrupção em seu código e inspecionando o valor de uma variável qubit, por exemplo:
  > 
  > ![Mostrar ID do qubit no Visual Studio](~/media/qubit_id.png)
  >
  > o qubit com o `0` de índice em `register2` tem ID =`3`, o qubit com `1` de índice tem a ID =`2`.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Linha de Comandos/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Você pode descobrir uma ID de qubit usando a função <xref:microsoft.quantum.intrinsic.message> e passando a variável qubit na mensagem, por exemplo:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > que pode gerar essa saída:
  >```
  > 0=q:3; 1=q:2
  >```
  > Isso significa que o qubit com o índice `0` em `register2` tem a ID =`3`, o qubit com `1` de índice tem a ID =`2`.


***

<xref:microsoft.quantum.diagnostics.dumpmachine> faz parte do namespace <xref:microsoft.quantum.diagnostics>, portanto, para usá-lo, você deve adicionar uma instrução `open`:

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a>DumpRegister

<xref:microsoft.quantum.diagnostics.dumpregister> funciona como <xref:microsoft.quantum.diagnostics.dumpmachine>, exceto que ele também usa uma matriz de qubits para limitar a quantidade de informações apenas às relevantes para o qubits correspondente.

Assim como ocorre com <xref:microsoft.quantum.diagnostics.dumpmachine>, as informações geradas pelo <xref:microsoft.quantum.diagnostics.dumpregister> dependem da máquina de destino. Para o simulador de Quantum de estado completo, ele grava no arquivo a função de onda até uma fase global do subsistema Quantum gerado pelo qubits fornecido no mesmo formato que <xref:microsoft.quantum.diagnostics.dumpmachine>.  Por exemplo, use novamente um computador com apenas dois qubits alocados e no estado Quantum $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ pi/4} ((\frac{1}{\sqrt{2}} \ket{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}), \end{align} $ $ chamando <xref:microsoft.quantum.diagnostics.dumpregister> para `qubit[0]` gera essa saída :

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

e chamar <xref:microsoft.quantum.diagnostics.dumpregister> para `qubit[1]` gera essa saída:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Em geral, o estado de um registro que é confusas com outro registro é um estado misto em vez de um estado puro. Nesse caso, <xref:microsoft.quantum.diagnostics.dumpregister> gera a seguinte mensagem:

```
Qubits provided (0;) are entangled with some other qubit.
```

O exemplo a seguir mostra como você pode usar <xref:microsoft.quantum.diagnostics.dumpregister> e <xref:microsoft.quantum.diagnostics.dumpmachine> no código de Q #:

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a>Depurar

Além das funções e operações de `Assert` e `Dump`, o Q # dá suporte a um subconjunto de recursos de depuração padrão do Visual Studio: [definir pontos de interrupção de linha](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), percorrer [código usando F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) e [inspecionar valores de variáveis clássicas](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) é possível durante a execução do código no simulador.

A depuração no Visual Studio Code aproveita os recursos de depuração fornecidos pela C# extensão do para Visual Studio Code da plataforma OmniSharp e requer a instalação da [versão mais recente](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp). 
