---
title: Teste e depuração - Técnicas Q# Microsoft Docs
description: Testes e depuração - Técnicas Q#
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: cfc71f08be0f190d9f5f4a48796e3d0ad06d6107
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820118"
---
# <a name="testing-and-debugging"></a>Testes e Depuração

Tal como na programação clássica, é essencial poder verificar se os programas quânticos funcionam como pretendido, e ser capaz de diagnosticar um programa quântico que é incorreto.
Nesta secção, cobrimos as ferramentas oferecidas pela Q# para testar e depurar programas quânticos.

## <a name="unit-tests"></a>Testes unitários

Uma abordagem comum para testar programas clássicos é escrever pequenos programas chamados *testes unitários* que executam código numa biblioteca e comparar a sua produção com alguma saída esperada.
Por exemplo, podemos querer garantir que `Square(2)` retorno `4`, uma vez que sabemos *um priori* que $2^2 = 4$.

Q# suporta a criação de testes unitários para programas quânticos, e que podem ser executados como testes dentro da estrutura de teste da unidade [xUnit.](https://xunit.github.io/)

### <a name="creating-a-test-project"></a>Criação de um Projeto de Teste

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Abra o Visual Studio 2019. Vá ao menu `File` e selecione `New` > `Project...`.
No canto superior direito, procure `Q#`e selecione o modelo `Q# Test Project`.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Linha de Comandos/Visual Studio Code](#tab/tabid-vscode)

A partir da sua linha de comando favorita, corra o seguinte comando:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

O seu novo projeto terá um único ficheiro `Tests.qs`, que fornece um local conveniente para definir novos testes da unidade Q#.
Inicialmente, este ficheiro contém um teste de unidade de amostra `AllocateQubit` que verifica que um qubit recém-atribuído está no estado de $\ket{0}$ e imprime uma mensagem:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:novo: Qualquer operação ou função Q# que tenha um argumento de tipo `Unit` e devoluções `Unit` pode ser marcado como um teste de unidade através do atributo `@Test("...")`. O argumento desse atributo, `"QuantumSimulator"` acima, especifica o alvo em que o teste é executado. Um único teste pode ser executado em vários alvos. Por exemplo, adicione um atributo `@Test("ResourcesEstimator")` acima `AllocateQubit`. 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Guarde o ficheiro e execute todos os testes. Deve agora haver dois testes unitários, um em que o AllocateQubit é executado no QuantumSimulator, e outro onde é executado no ResourceEstimator. 

O compilador Q# reconhece os alvos incorporados "QuantumSimulator", "ToffoliSimulator" e "ResourcesEstimator" como alvos de execução válidos para testes unitários. Também é possível especificar qualquer nome totalmente qualificado para definir um alvo de execução personalizado. 

### <a name="running-q-unit-tests"></a>Testes de unidade Q# em execução

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Como uma configuração única por solução, vá ao menu `Test` e selecione `Test Settings` > `Default Processor Architecture` > `X64`.

> [!TIP]
> A definição de arquitetura de processador padrão para Visual Studio é armazenada no ficheiro de solução (`.suo`) para cada solução.
> Se apagar este ficheiro, terá de selecionar `X64` como arquitetura do seu processador novamente.

Construa o projeto, vá ao menu `Test` e selecione `Windows` > `Test Explorer`. `AllocateQubit` aparecerão na lista de testes do grupo `Not Run Tests`. Selecione `Run All` ou execute este teste individual, e deve passar!

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Linha de Comandos/Visual Studio Code](#tab/tabid-vscode)

Para executar testes, navegue para a pasta do projeto (a pasta que contém `Tests.csproj`), e execute o comando:

```bash
$ dotnet restore
$ dotnet test
```

Deve obter uma saída semelhante à seguinte:

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

Os ensaios unitários podem ser filtrados de acordo com o seu nome e/ou o alvo de execução:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

A função intrínseca <xref:microsoft.quantum.intrinsic.message> tem tipo `(String -> Unit)` e permite a criação de mensagens de diagnóstico.

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Depois de executar um teste no Test Explorer e clicar no teste, aparecerá um painel com informações sobre a execução do teste: Estado passado/falhado, tempo decorrido e uma ligação "Output". Se clicar no link "Output", a saída de teste abrirá numa nova janela.

![saída de teste](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Linha de Comandos/Visual Studio Code](#tab/tabid-vscode)

O estado de passagem/falha de cada teste é impresso na consola por `dotnet test`.
Para testes falhados, as saídas também são impressas na consola para ajudar a diagnosticar a falha.

***

## <a name="assertions"></a>Afirmações

Como as funções em Q# não têm efeitos secundários _lógicos,_ quaisquer _outros tipos_ de efeitos de executar uma função cujo tipo de saída é a tuple vazia `()` nunca podem ser observados dentro de um programa Q#.
Ou seja, uma máquina-alvo pode optar por não executar qualquer função que desfaça `()` com a garantia de que esta omissão não modificará o comportamento de qualquer código Q# seguinte.
Isto torna as funções de retorno `()` uma ferramenta útil para incorporar afirmações e depurar lógica em programas Q#. 

A mesma lógica pode ser aplicada à implementação de afirmações. Vamos considerar um exemplo simples:

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

Aqui, a palavra-chave `fail` indica que o cálculo não deve prosseguir, elevando uma exceção na máquina-alvo que executa o programa Q#.
Por definição, uma falha deste tipo não pode ser observada a partir de Q#, uma vez que nenhum outro código Q# é executado após uma declaração `fail` ser alcançado.
Assim, se passarmos por um apelo à `AssertPositive`, podemos ter a certeza de que o seu contributo foi positivo.

Com base nestas ideias, [o prelúdio](xref:microsoft.quantum.libraries.standard.prelude) oferece duas afirmações especialmente úteis, <xref:microsoft.quantum.intrinsic.assert> e <xref:microsoft.quantum.intrinsic.assertprob> ambas modeladas como operações para `()`. Estas afirmações tomam cada um um operador Pauli descrevendo uma medição particular de interesse, um registo quântico sobre o qual deve ser feita uma medição e um resultado hipotético.
Nas máquinas-alvo que funcionam por simulação, não estamos ligados ao [teorema de não clonagem,](https://en.wikipedia.org/wiki/No-cloning_theorem)e podemos efetuar tais medições sem perturbar o registo passado a tais afirmações.
Um simulador pode então, semelhante à função `AssertPositive` acima, abortar a computação se o resultado hipotético não for observado na prática:

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

No hardware quântico físico, onde o teorema de não clonagem impede o exame do estado quântico, as operações `Assert` e `AssertProb` simplesmente devolvem `()` sem outro efeito.

O espaço de <xref:microsoft.quantum.diagnostics> fornece várias mais funções da família `Assert` que nos permitem verificar condições mais avançadas. 

## <a name="dump-functions"></a>Funções de despejo

Para ajudar a resolver problemas em programas quânticos, o espaço de nome <xref:microsoft.quantum.diagnostics> oferece duas funções que podem despejar num ficheiro o estado atual da máquina-alvo: <xref:microsoft.quantum.diagnostics.dumpmachine> e <xref:microsoft.quantum.diagnostics.dumpregister>. A saída gerada de cada um depende da máquina-alvo.

### <a name="dumpmachine"></a>DumpMachine

O simulador quântico de estado inteiro distribuído como parte do Kit de Desenvolvimento Quântico escreve no ficheiro a função de [onda](https://en.wikipedia.org/wiki/Wave_function) de todo o sistema quântico, como uma matriz unidimensional de números complexos, em que cada elemento representa a amplitude da probabilidade de medir a base computacional estado $\ket{n}$, onde $\ket{n} = \ket{b_{{n-1}... b_1b_0}$ por bits $\{b_i\}$. Por exemplo, numa máquina com apenas dois qubits atribuídos e no estado quântico $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> gera esta saída:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

A primeira linha fornece um comentário com os IDs dos qubits correspondentes na sua ordem significativa.
O resto das linhas descrevem a amplitude da probabilidade de medir o vetor de estado base $\ket{n}$ em ambos os formatos cartesianos e polares. Em detalhe para a primeira fila:

* **`∣0❭:`** esta linha corresponde ao estado de base computacional `0`
* **`0.707107 +  0.000000 i`:** a amplitude da probabilidade em formato cartesiano.
* **` == `** : o sinal de `equal` sepeiza ambas as representações equivalentes.
* **`**********  `** : Uma representação gráfica da magnitude, o número de `*` é proporcional à probabilidade de medir este vetor de estado.
* **`[ 0.500000 ]`:** o valor numérico da magnitude
* **`    ---`** : Uma representação gráfica da fase da amplitude (ver abaixo).
* **`[ 0.0000 rad ]`:** o valor numérico da fase (em radianos).

Tanto a magnitude como a fase são exibidas com uma representação gráfica. A representação de magnitude é direta: mostra uma barra de `*`, maior a probabilidade maior será a barra. Para a fase, mostramos os seguintes símbolos para representar o ângulo com base nas gamas:

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

Os seguintes exemplos mostram `DumpMachine` para alguns Estados comuns:

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
  > O id de um qubit é atribuído no tempo de funcionamento e não está necessariamente alinhado com a ordem em que o qubit foi atribuído ou a sua posição dentro de um registo qubit.


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Você pode descobrir um qubit id no Estúdio Visual colocando um ponto de rutura no seu código e inspecionando o valor de uma variável qubit, por exemplo:
  > 
  > ![mostrar qubit id no Estúdio Visual](~/media/qubit_id.png)
  >
  > o qubit com `0` de índice na `register2` tem id=`3`, o qubit com índice `1` tem id=`2`.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Linha de Comandos/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Pode descobrir um id qubit utilizando a função <xref:microsoft.quantum.intrinsic.message> e passando a variável qubit na mensagem, por exemplo:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > que poderia gerar esta saída:
  >```
  > 0=q:3; 1=q:2
  >```
  > o que significa que o qubit com índice `0` em `register2` tem id=`3`, o qubit com índice `1` tem id=`2`.


***

<xref:microsoft.quantum.diagnostics.dumpmachine> faz parte do espaço de nome <xref:microsoft.quantum.diagnostics>, por isso, para o utilizar, deve adicionar uma declaração `open`:

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

<xref:microsoft.quantum.diagnostics.dumpregister> funciona como <xref:microsoft.quantum.diagnostics.dumpmachine>, só que é preciso também um conjunto de qubits para limitar a quantidade de informação apenas a que seja relevante para os qubits correspondentes.

Tal como acontece com <xref:microsoft.quantum.diagnostics.dumpmachine>, a informação gerada por <xref:microsoft.quantum.diagnostics.dumpregister> depende da máquina-alvo. Para o simulador quântico de todo o estado, escreve no ficheiro a função de onda até uma fase global do subsistema quântico gerado pelos qubits fornecidos no mesmo formato que <xref:microsoft.quantum.diagnostics.dumpmachine>.  Por exemplo, tome novamente uma máquina com apenas dois qubits atribuídos e no estado quântico $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 +i)}{2} \ket{10} = - e^{-i\pi/4} (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ), \end{align} $$ chamando <xref:microsoft.quantum.diagnostics.dumpregister> para `qubit[0]` gera esta saída gera esta saída :

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

e chamar <xref:microsoft.quantum.diagnostics.dumpregister> para `qubit[1]` gera esta saída:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Em geral, o estado de um registo que está enredado com outro registo é um estado misto e não um estado puro. Neste caso, <xref:microsoft.quantum.diagnostics.dumpregister> produz a seguinte mensagem:

```
Qubits provided (0;) are entangled with some other qubit.
```

O exemplo que se segue mostra como pode usar tanto <xref:microsoft.quantum.diagnostics.dumpregister> como <xref:microsoft.quantum.diagnostics.dumpmachine> no seu código Q# :

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

Além das funções e operações de `Assert` e `Dump`, a Q# suporta um subconjunto de capacidades padrão de depuração do Estúdio Visual: definição de breakpoints de [linha,](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)passo através do [código usando F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) e [inspecionar valores de variáveis clássicas](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) são todos possíveis durante a execução de código no simulador.

Depuração em Código de Estúdio Visual aproveita as C# capacidades de depuração fornecidas pela extensão visual do Código do Estúdio powered pela OmniSharp e requer a instalação da [versão mais recente](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp). 
