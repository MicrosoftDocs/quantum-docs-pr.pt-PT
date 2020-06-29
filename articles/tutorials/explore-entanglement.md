---
title: Explorar o entrelaçamento com Q#
description: Saiba como escrever um programa quântico em Q#. Desenvolver uma aplicação de Estado de Bell com o Quantum Development Kit (QDK)
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 16c93b3dd17363c06602529cb34e8fc84aadc7a8
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415427"
---
# <a name="tutorial-explore-entanglement-with-q"></a>Tutorial: Explorar o entrelaçamento com Q\#

Neste tutorial, mostramos como escrever um programa em Q# que manipula e mede qubits e demonstra os efeitos da sobreposição e do entrelaçamento.

Vai escrever uma aplicação denominada Bell para demonstrar o entrelaçamento quântico.
O nome Bell refere-se aos estados de Bell, que são estados quânticos específicos de dois qubits, utilizados para representar os exemplos mais simples de sobreposição e de entrelaçamento quântico.

## <a name="pre-requisites"></a>Pré-requisitos

Se estiver preparado para começar a programar, siga estes passos antes de continuar: 

* [Instale](xref:microsoft.quantum.install) o Kit de Desenvolvimento Quântico utilizando o seu ambiente de linguagem e desenvolvimento preferido.
* Se já tiver o QDK instalado, confirme que o [atualizou](xref:microsoft.quantum.update) para a versão mais recente

Também pode acompanhar a narrativa sem instalar o QDK, revendo as visãos gerais da linguagem de programação Q# e os primeiros conceitos de computação quântica.

## <a name="in-this-tutorial-youll-learn-how-to"></a>Neste tutorial, ficará a saber como:

> [!div class="checklist"]
> * Criar e combinar operações em Q\#
> * Criar operações para colocar qubits em superposição, enredar e medi-los.
> * Demonstre o emaranhado quântico com um programa Q# executado num simulador. 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a>Demonstrando comportamento qubit com o QDK

Enquanto os bits clássicos contêm um único valor binário como 0 ou 1, o estado de um [qubit](xref:microsoft.quantum.glossary#qubit) pode estar numa **sobreposição** de 0 e 1.  Conceptualmente, o estado de um qubit pode ser considerado como uma direção em um espaço abstrato (também conhecido como um vetor).  Um estado qubit pode estar em qualquer uma das direções possíveis. Os dois **estados clássicos** são as duas direções, que representam 100% de probabilidade de medir 0 e 100% de probabilidade de medir 1.

O ato de medição produz um resultado binário e altera o estado de um qubit.
A medição produz um valor binário, 0 ou 1.  O qubit vai do estado de sobreposição (qualquer direção) até um dos estados clássicos.  Depois disso, repetir a mesma medição sem nenhuma operação intermediária produz o mesmo resultado binário.  

É possível [**entrelaçar**](xref:microsoft.quantum.glossary#entanglement) vários qubits.  Quando fazemos a medição de um qubit entrelaçado, o nosso conhecimento do estado do(s) outro(s) também é atualizado.

Agora, estamos prontos para demonstrar de que forma o Q# expressa este comportamento.  Vai começar com o programa mais simples possível e compilá-lo para demonstrar a sobreposição quântica e o entrelaçamento quântico.

## <a name="creating-a-q-project"></a>Criar um projeto Q#

A primeira coisa a fazer é criar um novo projeto Q#. Neste tutorial vamos utilizar o ambiente com base em [aplicações de linha de comando com código VS.](xref:microsoft.quantum.install.standalone)

Para criar um novo projeto, em Código VS: 

1. Clique **em Ver Paleta**de  ->  **Comando** e selecione **Q#: Criar novo projeto**.
2. Clique **na aplicação de consola autónoma**.
3. Navegue até ao local para salvar o projeto e clique em **Criar Projeto.**
4. Quando o projeto for criado com sucesso, clique em **Abrir novo projeto...** no direito inferior.

Neste caso, chamámos o `Bell` projeto. Isto gera dois ficheiros: `Bell.csproj` o ficheiro do projeto `Program.qs` e, um modelo de uma aplicação Q# que usaremos para escrever a nossa aplicação. O conteúdo `Program.qs` deve ser:

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a>Escreva a \# aplicação Q
 
O nosso objetivo é preparar dois qubits num estado quântico específico, ao demonstrar como trabalhar nos qubits com Q# para alterar o estado deles e demonstrar os efeitos da sobreposição e do entrelaçamento. Vamos construir isto peça a peça para introduzir estados qubit, operações e medição.

### <a name="initialize-qubit-using-measurement"></a>Inicialize o qubit usando a medição

no primeiro código abaixo, mostramos como utilizar os qubits em Q#.  Vamos introduzir duas operações, [`M`](xref:microsoft.quantum.intrinsic.m) e [`X`](xref:microsoft.quantum.intrinsic.x) que transformam o estado de um qubit. Neste fragmento de código, é definida uma operação `SetQubitState`, que utiliza um qubit como parâmetro e outro parâmetro, `desired`, que representa o estado em que queremos que o qubit esteja.  A operação `SetQubitState` executa uma medição no qubit através da operação `M`.  Em Q#, uma medição de qubit sempre retorna ou `Zero` `One` . .  Se a medição devolver um valor não igual ao valor pretendido, `SetQubitState` "inverte" o qubit; ou seja, executa uma `X` operação, que altera o estado qubit para um novo estado em que as probabilidades de uma medição regressam `Zero` e são `One` invertidas. Desta forma, `SetQubitState` coloca sempre o qubit alvo no estado desejado.

Substitua o conteúdo do `Program.qs` seguinte código:


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

Esta operação agora pode ser chamada para definir um qubit para um estado clássico, ao devolver `Zero` ou `One` 100% do tempo.
`Zero` e `One` são constantes que representam os dois únicos resultados possíveis da medição de um qubit.

A operação `SetQubitState` mede o qubit. Se o qubit estiver no estado pretendido, `SetQubitState` não fará nada. Caso contrário, ao executar a operação `X`, alteramos o estado do qubit para o estado pretendido.

#### <a name="about-q-operations"></a>Acerca das operações Q#

Uma operação Q# é uma sub-rotina quântica. Ou seja, é uma rotina callable que contém chamadas para outras operações quânticas.

Os argumentos para uma operação são especificados como uma cadeia de identificação, entre parênteses.

O tipo de retorno da operação é especificado após os dois pontos. Neste caso, a operação `SetQubitState` não tem retorno, pelo qual é marcada como `Unit` de retorno. É o equivalente Q# de `unit` em F#, o que é aproximadamente análogo a `void` em C# e uma cadeia de identificação vazia (`Tuple[()]`) em Python.

Utilizou duas operações quânticas na primeira operação Q#:

* A [`M`](xref:microsoft.quantum.intrinsic.m) operação, que mede o estado do qubit
* A [`X`](xref:microsoft.quantum.intrinsic.x) operação, que inverte o estado de um qubit

Uma operação quântica transforma o estado de um qubit. Por vezes, as pessoas falam sobre portas quânticas em vez de operações, em analogia às portas de lógica clássicas e que tem origem nos primórdios da computação quântica quando os algoritmos eram meramente uma construção teórica e visualizados como diagramas da mesma forma que os diagramas de circuito na computação clássica.

### <a name="counting-measurement-outcomes"></a>Contagem dos resultados da medição

Para demonstrar o efeito da operação `SetQubitState`, é adicionada uma operação `TestBellState`. Esta operação utiliza como entrada `Zero` ou `One`, chama a operação `SetQubitState` várias vezes com essa entrada e contabiliza o número de vezes que `Zero` foi devolvido pela medição do qubit e o número de vezes que `One` foi devolvido. Como é óbvio, nesta primeira simulação da operação `TestBellState`, esperamos que o resultado mostre que todas as medições do conjunto de qubits com `Zero` como entrada de parâmetro devolva `Zero` e todas as medições de um conjunto de qubits com `One` como entrada de parâmetro devolva `One`. Mais à frente, vamos adicionar código `TestBellState` para demonstrar superposição e emaranhamento.

Adicione a seguinte operação ao ficheiro `Bell.qs`, dentro do espaço de nomes, após o fim da operação `SetQubitState`:

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
Note que adicionámos uma linha antes de `return` imprimir uma mensagem explicativa na consola com a função `Message` ()[microsoft.quantum.intrínseca.message]

Esta operação (`TestBellState`) vai gerar um ciclo de `count` iterações, definir um valor `initial` especificado num qubit e, em seguida, medir (`M`) o resultado. Vai recolher estatísticas sobre quantos zeros e uns foram medidos e devolvê-los ao autor da chamada. E, executa ainda outra operação necessária. Redefine o qubit para um estado conhecido (`Zero`) antes de o devolver, o que permitirá que outros aloquem este qubit num estado conhecido. Esta operação é exigida pela instrução `using`.

#### <a name="about-variables-in-q"></a>Sobre variáveis em Q\#

Por predefinição, as variáveis Q# são imutáveis; o valor dessas variáveis não pode ser alterado após serem vinculadas. A palavra-chave `let` é utilizada para indicar a vinculação de uma variável imutável. Os argumentos da operação são sempre imutáveis.

Se precisar de uma variável cujo valor pode ser alterado, como `numOnes`, poderá declarar a variável com a palavra-chave `mutable`. Um valor de variável mutável pode ser alterado com uma instrução `setQubitState`.

Em ambos os casos, o tipo de variável é inferido pelo compilador. A Q# não requer nenhum tipo de anotação para as variáveis.

#### <a name="about-using-statements-in-q"></a>Sobre `using` declarações em Q\#

A instrução `using` também é especial para Q#. É utilizada para alocar qubits para utilização num bloco de código. Em Q#, todos os qubits são alocados e libertados dinamicamente, em vez de serem recursos fixos presente durante toda a duração de um algoritmo complexo. Uma instrução `using` aloca um conjunto de qubits no início e liberta esses qubits no final do bloco.

## <a name="execute-the-code-from-the-command-line"></a>Execute o código a partir da linha de comando

Para executar o código, precisamos de especificar o compilador *que* pode ser executado quando fornenciamos o `dotnet run` comando. Isto é feito com uma simples alteração no ficheiro Q# adicionando uma linha com `@EntryPoint()` precedível diretamente: a `TestBellState` operação neste caso. O código completo deve ser:

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

Para executar o programa precisamos especificar `count` e argumentos da linha de `initial` comando. Vamos escolher por exemplo `count = 1000` `initial = One` e. Introduza o seguinte comando:

```dotnetcli
dotnet run --count 1000 --initial One
```

E deve observar a seguinte saída:

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

Se tentar `initial = Zero` com o seu deve observar:

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a>Preparar a sobreposição

Agora vamos ver como Q# expressa formas de colocar qubits em superposição.  Lembre-se de que o estado de um qubit pode estar numa sobreposição de 0 e 1.  Vamos utilizar a operação `Hadamard` para esta ação. Se o qubit estiver num dos estados clássicos (em que uma medição devolve sempre `Zero` ou `One`), a operação `Hadamard` ou `H` colocará o qubit num estado em que uma medição do qubit devolverá `Zero` e `One` 50% do tempo.  Conceitualmente, o qubit pode ser pensado como estando entre `Zero` e `One`.  Agora, quando simularmos a operação `TestBellState`, veremos que os resultados vão devolver aproximadamente um número igual de `Zero` e `One` após a medição.  

### <a name="x-flips-qubit-state"></a>`X`flips qubit estado

Primeiro, vamos tentar inverter o qubit (se este estiver num estado `Zero`, será invertido para `One` e vice-versa). Esta inversão pode ser feita ao realizar uma operação `X` antes de o medir em `TestBellState`:

```qsharp
X(qubit);
let res = M(qubit);
```

Agora os resultados são invertidos:

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

Agora vamos explorar as propriedades quânticas dos qubits.

### <a name="h-prepares-superposition"></a>`H`prepara superposição

Para tal, só precisamos de substituir a operação `X` na execução anterior por uma operação `H` ou Hadamard. Em vez de inverter totalmente o qubit de 0 para 1, vamos invertê-lo apenas metade. As linhas substituídas em `TestBellState` agora são semelhantes ao seguinte:

```qsharp
H(qubit);
let res = M(qubit);
```

Os resultados começam a ficar mais interessantes:

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

Sempre que medimos, pedimos um valor clássico, mas o qubit encontra-se a meio entre 0 e 1 e assim obtemos (estatisticamente) 0 metade das vezes e 1 metade das vezes,
o quer é conhecido como **sobreposição** e dá-nos a nossa primeira vista real de um estado quântico.

## <a name="prepare-entanglement"></a>Preparar o entrelaçamento

agora, vamos ver como o Q# expressa formas de entrelaçar os qubits.
Primeiro, definimos o primeiro qubit para o estado inicial e utilizamos a operação `H` para colocá-lo em sobreposição.  Depois, antes de medirmos o primeiro qubit, usamos uma nova operação ( `CNOT` , que significa Controlled-NOT.  O resultado da execução desta operação em dois qubits é inverter o segundo qubit se o primeiro qubit for `One`.  Agora, os dois qubits estão entrelaçados.  As nossas estatísticas para o primeiro qubit não foram alteradas (uma probabilidade de 50-50 de um `Zero` ou de um `One` após a medição), mas quando medirmos o segundo qubit, este será __sempre__ igual ao que medimos para o primeiro qubit. O nosso `CNOT` entrelaçou os dois qubits, de modo a que aquilo que acontecer a um deles, aconteça também ao outro. Se as medições fossem invertidas (a medição do segundo qubit antes do primeiro), aconteceria a mesma coisa. A primeira medida seria aleatória e a segunda estaria num passo bloqueado para a medição que tivesse sido detetada primeiro.

A primeira coisa que temos de fazer é alocar dois qubits em vez de um `TestBellState` em:

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

Este procedimento vai permitir adicionar uma nova operação (`CNOT`) antes de medir (`M`) em `TestBellState`:

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

Adicionámos outra operação `SetQubitState` para inicializar o primeiro qubit para confirmar que está sempre no estado `Zero` quando começamos.

Precisamos também de redefinir o segundo qubit antes de o libertar.

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

A rotina completa é agora semelhante ao seguinte:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
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
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

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
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

O novo valor de retorno (`agree`) controla cada vez que a medição do primeiro qubit corresponde à medição do segundo qubit.

Executando o código que obtemos:

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

Conforme mencionado na descrição geral, as nossas estatísticas para o primeiro qubit não foram alteradas (uma probabilidade de 50-50 de um 0 ou de um 1), mas quando medirmos o segundo qubit, este será __sempre__ igual ao que medimos para o primeiro qubit, uma vez que estão entrelaçados!

## <a name="next-steps"></a>Passos seguintes

O tutorial [Pesquisa de Grover](xref:microsoft.quantum.quickstarts.search) mostra como compilar e executar a pesquisa de Grover, um dos algoritmos de computação quântica mais populares e dá um ótimo exemplo de um programa Q# que pode ser utilizado para resolver problemas reais através da computação quântica.  

A [Introdução ao Quantum Development Kit](xref:microsoft.quantum.welcome) recomenda mais formas de aprender a linguagem Q# e a programação quântica.
