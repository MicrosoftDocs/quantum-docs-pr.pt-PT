---
title: Teste e depuração
description: Aprenda a usar testes unitários, factos e afirmações, e despeje funções para testar e depurar programas quânticos.
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2f2181d388a59c1c6c5a0f13c9aa49d5fa1e51ae
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833177"
---
# <a name="testing-and-debugging"></a>Teste e depuração

Tal como acontece com a programação clássica, é essencial poder verificar se os programas quânticos funcionam como pretendido, e ser capaz de diagnosticar comportamentos incorretos.
Nesta secção, cobrimos as ferramentas oferecidas para Q# testar e depurar programas quânticos.

## <a name="unit-tests"></a>Testes de Unidade

Uma abordagem comum para testar programas clássicos é escrever pequenos programas chamados *testes unitários*, que executam código numa biblioteca e comparam a sua saída com alguma saída esperada.
Por exemplo, pode garantir que `Square(2)` os `4` retornos, uma vez que conhece um *priori* que $2^2 = 4$.

Q#suporta a criação de testes unitários para programas quânticos, e que podem ser executados como testes dentro da estrutura de teste da unidade [xUnit.](https://xunit.github.io/)

### <a name="creating-a-test-project"></a>Criação de um Projeto de Teste

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Open Visual Studio 2019. Vá ao menu **'Arquivo'** e selecione **New > Project...**. No canto superior direito, procure `Q#` e selecione o modelo ** Q# do Projeto de Teste.**

#### <a name="command-line--visual-studio-code"></a>[Linha de Comandos/Visual Studio Code](#tab/tabid-vscode)

Da sua linha de comando favorita, executar o seguinte comando:
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

O seu novo projeto tem um único `Tests.qs` ficheiro, que fornece um local conveniente para definir novos Q# testes de unidade.
Inicialmente, este ficheiro contém um teste de unidade de amostra `AllocateQubit` que verifica se um qubit recém-atribuído está no estado de $\ket $ e {0} imprime uma mensagem:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

Qualquer Q# operação ou função que tenha um argumento de tipo `Unit` e devoluções pode ser marcada como um `Unit` teste de unidade através do `@Test("...")` atributo. No exemplo anterior, o argumento a esse atributo, `"QuantumSimulator"` especifica o alvo em que o teste é executado. Um único teste pode ser executado em vários alvos. Por exemplo, adicione um atributo `@Test("ResourcesEstimator")` antes `AllocateQubit` . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Guarde o ficheiro e faça todos os testes. Deve haver agora dois testes de unidade, um em `AllocateQubit` que corre no , e outro onde corre no `QuantumSimulator` `ResourcesEstimator` . 

O Q# compilador reconhece os alvos incorporados `"QuantumSimulator"` , e como `"ToffoliSimulator"` `"ResourcesEstimator"` alvos de execução válidos para testes de unidade. Também é possível especificar qualquer nome totalmente qualificado para definir um alvo de execução personalizado. 

### <a name="running-no-locq-unit-tests"></a>Testes Q# de unidade de execução

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Como configuração única por solução, vá ao menu **de Teste** e selecione **Definições de Teste > Arquitetura do Processador Padrão > X64**.

> [!TIP]
> A definição de arquitetura de processador padrão para o Visual Studio está armazenada nas opções de solução `.suo` () ficheiro para cada solução.
> Se eliminar este ficheiro, terá de selecionar **o X64** como arquitetura do processador novamente.

Construa o projeto, abra o menu **Test** e selecione **Windows > Test Explorer**. **Aloque os** ecrãs Debit na lista de testes no grupo **Testes de Não Execução.** Selecione **Executar Tudo** ou executar este teste individual.

#### <a name="command-line--visual-studio-code"></a>[Linha de Comandos/Visual Studio Code](#tab/tabid-vscode)

Para realizar testes, navegue na pasta do projeto (a pasta que `Tests.csproj` contém), e execute o comando:

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

Os testes de unidade podem ser filtrados de acordo com o seu nome ou o alvo de execução:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

A função intrínseca <xref:microsoft.quantum.intrinsic.message> tem o tipo e permite a `(String -> Unit)` criação de mensagens de diagnóstico.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Depois de realizar um teste no Test Explorer e clicar no teste, um painel apresenta informações sobre o teste: Estado de passagem/falha, tempo decorrido e uma ligação à saída. Clique em **Saída** para abrir a saída do teste numa nova janela.

![saída de teste](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Linha de Comandos/Visual Studio Code](#tab/tabid-vscode)

O estado de passe/falha de cada teste é impresso na consola por `dotnet test` .
Para testes falhados, as saídas também são impressas na consola para ajudar a diagnosticar a falha.

***

## <a name="facts-and-assertions"></a>Factos e Afirmações

Como as funções Q# não têm efeitos colaterais _lógicos,_ nunca se pode observar, a partir de um Q# programa, quaisquer outros tipos de efeitos de funcionamento de uma função cujo tipo de saída é o tuple vazio `()` .
Ou seja, uma máquina-alvo pode optar por não executar qualquer função que retorne `()` com a garantia de que esta omissão não modificará o comportamento de qualquer código que se Q# segue.
Este comportamento faz com que as funções retornem `()` `Unit` (como) uma ferramenta útil para incorporar afirmações e depurar lógica em Q# programas. 

Vamos considerar um exemplo simples:

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

Aqui, a palavra-chave `fail` indica que o cálculo não deve prosseguir, e levanta uma exceção na máquina-alvo que executa o Q# programa.
Por definição, uma falha deste tipo não pode ser observada a partir de dentro Q# , uma vez que a máquina-alvo já não executa o código após chegar a uma Q# `fail` declaração.
Assim, se avançarmos para além de um `PositivityFact` apelo, podemos ter a certeza de que o seu contributo foi positivo.

Note que podemos implementar o mesmo comportamento `PositivityFact` que usar a [`Fact`](xref:microsoft.quantum.diagnostics.fact) função a partir do espaço de <xref:microsoft.quantum.diagnostics> nomes:

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

*As afirmações*, por outro lado, são usadas da mesma forma aos factos, mas podem depender do estado da máquina-alvo. Consequentemente, são definidas como operações, enquanto os factos são definidos como funções (como no exemplo anterior).
Para compreender a distinção, considere a seguinte utilização de um facto dentro de uma afirmação:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

Aqui, estamos a usar a operação <xref:microsoft.quantum.environment.getqubitsavailabletouse> para devolver o número de qubits disponíveis para usar.
Como isso depende do estado global do programa e do seu ambiente de funcionamento, a nossa definição deve `AssertQubitsAreAvailable` ser também uma operação.
No entanto, podemos usar esse estado global para produzir um valor simples `Bool` como entrada para a `Fact` função.

[O prelúdio](xref:microsoft.quantum.libraries.standard.prelude), baseado nestas ideias, oferece duas afirmações especialmente úteis, <xref:microsoft.quantum.diagnostics.assertmeasurement> e ambas <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> modeladas como operações `()` em. Estas afirmações cada uma delas leva um operador Pauli descrevendo uma determinada medição de interesse, um registo quântico no qual é realizada uma medição, e um resultado hipotético.
As máquinas-alvo que funcionam por simulação não estão ligadas [pelo teorema da não clonagem](https://en.wikipedia.org/wiki/No-cloning_theorem), e podem efetuar tais medições sem perturbar o registo que passa para tais afirmações.
Um simulador pode então, semelhante à `PositivityFact` função anterior, parar a computação se o resultado hipotético não for observado na prática:

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

No hardware quântico físico, onde o teorema de não clonagem impede o exame de um estado quântico, as `AssertMeasurement` `AssertMeasurementProbability` operações simplesmente regressam `()` sem outro efeito.

O <xref:microsoft.quantum.diagnostics> espaço de nomes proporciona várias outras funções da família, com as `Assert` quais pode verificar condições mais avançadas. 

## <a name="dump-functions"></a>Funções de despejo

Para ajudar a resolver os programas quânticos, o <xref:microsoft.quantum.diagnostics> espaço de nome oferece duas funções que podem despejar num ficheiro o estado atual da máquina-alvo: e <xref:microsoft.quantum.diagnostics.dumpmachine> <xref:microsoft.quantum.diagnostics.dumpregister> . A saída gerada de cada uma depende da máquina-alvo.

### <a name="dumpmachine"></a>DumpMachine

O simulador quântico de estado completo distribuído como parte do Kit de Desenvolvimento Quântico escreve no ficheiro a [função](https://en.wikipedia.org/wiki/Wave_function) de onda de todo o sistema quântico, como uma matriz unidimensional de números complexos, em que cada elemento representa a amplitude da probabilidade de medir o estado de base computacional $\ket{n}$, onde $\ket{n} = \ket{b_{n-1}... b_1b_0}$ por bits $ \{ b_i \} $. Por exemplo, numa máquina com apenas dois qubits atribuídos e no estado quântico $$ \start{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} - \frac{(1 + i)} {2} \ket, {10} \end{align} $$ chamando <xref:microsoft.quantum.diagnostics.dumpmachine> gera esta saída:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

A primeira linha fornece um comentário com os ids dos qubits correspondentes na sua ordem significativa.
As restantes linhas descrevem a amplitude de probabilidade de medir o vetor de estado base $\ket{n}$ em formatos cartesianos e polares. Em detalhe para a primeira linha:

* **`∣0❭:`** esta linha corresponde ao `0` estado de base computacional
* **`0.707107 +  0.000000 i`**: a amplitude de probabilidade no formato cartesiano.
* **` == `**: o `equal` sinal separa ambas as representações equivalentes.
* **`**********  `**: Uma representação gráfica da magnitude, o número `*` de é proporcional à probabilidade de medir este vetor de estado.
* **`[ 0.500000 ]`**: o valor numérico da magnitude
* **`    ---`**: Representação gráfica da fase da amplitude (ver seguinte saída).
* **`[ 0.0000 rad ]`**: o valor numérico da fase (em radianos).

Tanto a magnitude como a fase são exibidas com uma representação gráfica. A representação de magnitude é direta: mostra uma barra de `*` , quanto maior for a probabilidade, maior será a fasquia. Para a fase, mostramos os seguintes símbolos para representar o ângulo baseado em intervalos:

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

Os seguintes exemplos mostram `DumpMachine` alguns Estados comuns:

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
  > O id de um qubit é atribuído em tempo de execução e não está necessariamente alinhado com a ordem em que o qubit foi atribuído ou a sua posição dentro de um registo qubit.


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Pode localizar um id qubit no Visual Studio colocando um ponto de rutura no seu código e inspecionando o valor de uma variável qubit, por exemplo:
  > 
  > ![mostrar qubit id no Estúdio Visual](~/media/qubit_id.png)
  >
  > o qubit com índice `0` em `register2` tem id= `3` , o qubit com índice tem `1` id= `2` .

#### <a name="command-line--visual-studio-code"></a>[Linha de Comandos/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Pode localizar um id qubit utilizando a <xref:microsoft.quantum.intrinsic.message> função e passando a variável qubit na mensagem, por exemplo:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > que poderia gerar esta saída:
  >```
  > 0=q:3; 1=q:2
  >```
  > o que significa que o qubit com índice `0` em `register2` tem id= `3` , o qubit com índice tem `1` id= `2` .


***

Uma <xref:microsoft.quantum.diagnostics.dumpmachine> vez que faz parte do espaço de  <xref:microsoft.quantum.diagnostics> nomes, deve adicionar uma `open` declaração para aceder a ele:

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

<xref:microsoft.quantum.diagnostics.dumpregister> funciona como <xref:microsoft.quantum.diagnostics.dumpmachine> , exceto que também é preciso uma matriz de qubits para limitar a quantidade de informação apenas à relevante para os qubits correspondentes.

Tal como <xref:microsoft.quantum.diagnostics.dumpmachine> acontece, a informação gerada depende <xref:microsoft.quantum.diagnostics.dumpregister> da máquina-alvo. Para o simulador quântico de estado completo, escreve no ficheiro a função de onda até uma fase global do subsistil quântico gerado pelos qubits fornecidos no mesmo formato que <xref:microsoft.quantum.diagnostics.dumpmachine> .  Por exemplo, tomar novamente uma máquina com apenas dois qubits atribuídos e no estado quântico $$ \start{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} - \frac{(1 + i)} {2} \ket {10} = - e^{-i\pi/4} (\frac {1} {\sqrt {2} } \ket {0} - \frac{(1 + i)} {2} {1} \ket ) \otimes \otimes \frac{-(1 + i)}{\sqrt {2} } \ket {0} ) , \end{align} $} chamando <xref:microsoft.quantum.diagnostics.dumpregister> para gerar esta `qubit[0]` saída:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

e apelar <xref:microsoft.quantum.diagnostics.dumpregister> para `qubit[1]` gerar esta saída:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Em geral, o estado de um registo que está emaranhado com outro registo é um estado misto e não um estado puro. Neste caso, <xref:microsoft.quantum.diagnostics.dumpregister> produz a seguinte mensagem:

```
Qubits provided (0;) are entangled with some other qubit.
```

O exemplo a seguir mostra-lhe como pode usar ambos <xref:microsoft.quantum.diagnostics.dumpregister> e <xref:microsoft.quantum.diagnostics.dumpmachine> no seu Q# código:

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

Além de `Assert` `Dump` funções e operações, Q# suporta um subconjunto de capacidades padrão de depuração do Estúdio Visual: [definir pontos](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)de rutura de linha, [passar pelo código usando F10,](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)e [inspecionar valores de variáveis clássicas](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) são todos possíveis ao executar o seu código no simulador.

Depurar em Visual Studio Code aproveita as capacidades de depuração fornecidas pela extensão C# para Código de Estúdio Visual alimentada pela OmniSharp e requer a instalação da [versão mais recente](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp). 
