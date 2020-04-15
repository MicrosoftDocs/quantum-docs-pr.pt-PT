---
title: Simuladores quânticos e aplicações anfitriãs | Microsoft Docs
description: Descreve como controlar simuladores quânticos com uma linguagem de computação .NET clássica, normalmente C# ou Q#.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/13/2020
ms.locfileid: "73442215"
---
# <a name="quantum-simulators-and-host-applications"></a>Simuladores quânticos e aplicações anfitriãs

## <a name="what-youll-learn"></a>O que irá aprender

> [!div class="checklist"]
> * Como se executam algoritmos quânticos
> * Simuladores quânticos incluídos nesta versão
> * Como escrever um controlador em C# para o algoritmo quântico

## <a name="the-quantum-development-kit-execution-model"></a>O Modelo de Execução do Quantum Development Kit

Em [Escrever um programa quântico](xref:microsoft.quantum.write-program), executámos o nosso algoritmo quântico ao transmitir um objeto `QuantumSimulator` para o método `Run` da classe de algoritmo.
A classe `QuantumSimulator` executa o algoritmo quântico ao simular na íntegra o vetor de estado quântico, que é ideal para executar e testar `Teleport`.
Veja o [Guia de conceitos](xref:microsoft.quantum.concepts.intro) para obter mais informações sobre os vetores quânticos.

Outros computadores de destino podem ser utilizados para executar um algoritmo quântico.
O computador é responsável por fornecer implementações de primitivos quânticos para o algoritmo.
Tal inclui operações primitivas como H, CNOT e Medição, bem como gestão e monitorização de qubits.
Classes diferentes de computadores quânticos representam diferentes modelos de execução para o mesmo algoritmo quântico.

Cada tipo de computador quântico pode fornecer diferentes implementações desses primitivos.
Por exemplo, o simulador de rastreio do computador quântico incluído no development kit não faz nenhuma simulação.
Em vez disso, rastreia a porta, o qubit e outras utilizações dos recursos para o algoritmo.

### <a name="quantum-machines"></a>Computadores Quânticos

Posteriormente, vamos definir classes adicionais de computadores quânticos para suportar outros tipos de simulações e para suportar a execução em computadores quânticos topológicos.
Permitir que o algoritmo se mantenha constante enquanto se varia a implementação do computador subjacente facilita testar e depurar um algoritmo na simulação e, em seguida, executá-lo em hardware real com a confiança de que o algoritmo não mudou.

### <a name="whats-included-in-this-release"></a>O que está Incluído nesta Versão

Esta versão do kit de programador quântico inclui diversas classes de computadores quânticos.
Todas estão definidas no espaço de nomes `Microsoft.Quantum.Simulation.Simulators`.

* Um [simulador de vetor de estado completo](xref:microsoft.quantum.machines.full-state-simulator), a classe `QuantumSimulator`.
* Um [simulador de recursos simples](xref:microsoft.quantum.machines.resources-estimator), a classe `ResourcesEstimator`, permite uma análise de nível superior dos recursos necessários para executar um algoritmo quântico.
* Um [simulador de recursos baseado em rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro), a classe `QCTraceSimulator`, que permite uma análise avançada doe consumos de recursos para todo o grafo de chamada do algoritmo.
* Um [simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator), a classe `ToffoliSimulator`.

## <a name="writing-a-host-application"></a>Escrever uma aplicação anfitriã

Em [Escrever um programa quântico](xref:microsoft.quantum.write-program), escrevemos um controlador C# simples para o nosso algoritmo teleport. Um controlador C# tem quatro objetivos principais:

* Construir o computador de destino
* Calcular todos os argumentos necessários do algoritmo quântico
* Executar o algoritmo quântico com o simulador
* Processar o resultado da operação

Aqui, vamos falar de cada passo mais detalhadamente.

### <a name="constructing-the-target-machine"></a>Construir o Computador de Destino

Os computadores quânticos são instâncias de classes .NET normais, por isso, são criados ao invocar o construtor, como em qualquer classe .NET.
Alguns simuladores, como o `QuantumSimulator`, implementam a interface .NET <xref:System.IDisposable?displayProperty=nameWithType> e por isso devem ser encapsulados numa instrução C# `using`.

### <a name="computing-arguments-for-the-algorithm"></a>Argumentos de Computação para o Algoritmo

No nosso exemplo `Teleport`, calculámos alguns argumentos relativamente artificiais para transmitir para o nosso algoritmo quântico.
No entanto, é mais frequente que o algoritmo requeira dados significativos, e o mais fácil é fornecê-los do controlador clássico.

Por exemplo, ao trabalhar em soluções químicas, o algoritmo quântico requer uma grande tabela de integrantes de interação orbital molecular.
Geralmente, são lidos a partir de um ficheiro fornecido ao executar o algoritmo.
Uma vez que o Q# não tem um mecanismo para aceder ao sistema de ficheiros, a melhor forma de recolher este tipo de dados é utilizar o controlador clássico e transmitir para o método `Run` do algoritmo quântico.

Outro caso em que o controlador clássico desempenha um papel fundamental é em métodos de variação.
Nesta classe de algoritmos, um estado quântico é preparado com base em parâmetros clássicos e esse estado utiliza-se para calcular um valor de interesse.
Os parâmetros ajustam-se com base num tipo de algoritmo de aprendizagem automática ou “hill climbing” e o algoritmo quântico é executado novamente.
Nestes algoritmos, o algoritmo “hill climbing” propriamente dito é mais bem implementado como uma função estritamente clássica que é chamada pelo controlador clássico; os resultados do “hill climbing” são depois transmitidos para a execução seguinte do algoritmo quântico.

### <a name="running-the-quantum-algorithm"></a>Executar o Algoritmo Quântico

Esta parte é geralmente muito simples.
Todas as operações Q# são compiladas numa classe que fornece um método `Run` estático.
Os argumentos deste método são dados pela cadeia de identificação de argumento aplanado da operação propriamente dita, além de um primeiro argumento adicional, que é o simulador com o qual executar. Para uma operação que espera a cadeia de identificação com nome do tipo `(a: String, (b: Double, c: Double))`, o seu equivalente aplanado é do tipo `(String a, Double b, Double c)`.


Existem determinadas nuances ao transmitir argumentos para o método `Run`:

* As matrizes têm de ser encapsuladas num objeto `Microsoft.Quantum.Simulation.Core.QArray<T>`.
    Uma classe `QArray` tem um construtor que pode assumir qualquer coleção ordenada (`IEnumerable<T>`) de objetos apropriados.
* A cadeia de identificação, `()` em Q#, é representada por `QVoid.Instance` em C#.
* As cadeias de identificação não vazias são representadas como instâncias .NET `ValueTuple`.
* Os tipos definidos pelo utilizador Q# são transmitidos como o respetivo tipo de base.
* Para transmitir uma operação ou função para um método `Run`, tem de obter uma instância da classe da função ou operação através do método `Get<>` do simulador.

### <a name="processing-the-results"></a>Processar os Resultados

Os resultados do algoritmo quântico são devolvidos do método `Run`.
O método `Run` é executado de forma assíncrona, pelo que devolve uma instância de <xref:System.Threading.Tasks.Task`1>.
Existem várias formas de obter os resultados reais da operação. A forma mais simples é utilizar, em `Task`, a propriedade [`Result`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
Mas outras técnicas, como utilizar o método [`Wait`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) ou a palavra-chave C# [`await`](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) também funcionam.

Como acontece em argumentos, as cadeias de identificação Q# são representadas como instâncias `ValueTuple` e as matrizes Q# são representadas como instâncias `QArray`.
Os tipos definidos pelo utilizador são devolvidos como o respetivo tipo de base.
A cadeia de identificação vazia, `()`, é devolvida como uma instância da classe `QVoid`.

Muitos algoritmos quânticos requerem uma quantidade substancial de pós-processamento para gerar respostas úteis.
Por exemplo, a parte quântica do algoritmo de Shor é apenas o início de um cálculo que obtém os fatores de um número.

Na maioria dos casos, o mais simples e fácil é fazer este tipo de pós-processamento no controlador clássico.
Apenas o controlador clássico pode reportar resultados ao utilizador ou escrever os mesmos no disco.
O controlador clássico terá acesso a bibliotecas analíticas e outras funções matemáticas que não estão expostas em Q#.


## <a name="failures"></a>Falhas

Quando a instrução Q# `fail` for atingida durante a execução de uma operação, será lançada uma `ExecutionFailException`.

Devido à utilização de `System.Task` no método `Run`, a exceção lançada como resultado de uma instrução `fail` será encapsulada num `System.AggregateException`.
Para descobrir o verdadeiro motivo da falha, terá de iterar em `AggregateException` 
`InnerExceptions`, por exemplo:

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a>Outras Linguagens Clássicas

Apesar de os exemplos que fornecemos estarem em C#, F# e Python, o Development Kit Quantum suporta também a escrita de programas anfitriões clássicos noutras linguagens.
Por exemplo, se quiser escrever um programa anfitrião no Visual Basic, [este deverá funcionar bem](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).
