---
title: Diagnósticos nas Q# bibliotecas padrão
description: Conheça as funções e operações de diagnóstico nas Q# bibliotecas padrão usadas para apanhar erros ou erros em programas quânticos.
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: d13122187a24893d297cfdbb3ad4db03eb22ded0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858688"
---
# <a name="diagnostics"></a>Diagnóstico #

Tal como acontece com o desenvolvimento clássico, é importante ser capaz de diagnosticar erros e erros em programas quânticos.
As Q# bibliotecas padrão fornecem uma variedade de maneiras diferentes para garantir a correção dos programas quânticos, conforme detalhado em <xref:microsoft.quantum.guide.testingdebugging> .
Em grande parte, este suporte vem sob a forma de funções e operações que instruem a máquina-alvo a fornecer informações de diagnóstico adicionais ao programa de acolhimento ou ao desenvolvedor, ou a impor a correção das condições e invariantes expressas pela função ou chamada de funcionamento.

## <a name="machine-diagnostics"></a>Diagnóstico de Máquinas ##

Os diagnósticos sobre valores clássicos podem ser obtidos utilizando a <xref:Microsoft.Quantum.Intrinsic.Message> função para registar uma mensagem de forma dependente da máquina.
Por padrão, isto escreve a corda para a consola.
Usado em conjunto com cordas interpoladas, <xref:Microsoft.Quantum.Intrinsic.Message> torna fácil relatar informações de diagnóstico sobre valores clássicos:

```qsharp
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message` tem assinatura `(String -> Unit)` , mais uma vez representando que a emissão de uma mensagem de registo de depurado não pode ser observada a partir de dentro Q# .

Os <xref:Microsoft.Quantum.Diagnostics.DumpMachine> e <xref:Microsoft.Quantum.Diagnostics.DumpRegister> os callables instruem as máquinas-alvo a fornecer informações de diagnóstico sobre todos os qubits atualmente atribuídos ou sobre um registo específico de qubits, respectivamente.
Cada máquina-alvo varia em que informações de diagnóstico são fornecidas em resposta a uma instrução de despejo.
A máquina alvo [de simulador de estado completo,](xref:microsoft.quantum.machines.full-state-simulator) por exemplo, fornece o programa de anfitrião com o vetor de estado que usa internamente para representar um registo de qubits.
Em comparação, a máquina-alvo [do simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) fornece uma única bit clássica para cada qubit.

 Para saber mais sobre a saída [completa do simulador de estado,](xref:microsoft.quantum.machines.full-state-simulator) `DumpMachine` veja a secção de funções de despejo do nosso artigo de [teste e depuragem](xref:microsoft.quantum.guide.testingdebugging#dump-functions).


## <a name="facts-and-assertions"></a>Factos e Afirmações ##

Tal como discutido em [Testes e Depuragem](xref:microsoft.quantum.guide.testingdebugging), uma função ou operação com assinatura `Unit -> Unit` `Unit => Unit` ou, respectivamente, pode ser marcada como um *teste de unidade*.
Cada teste de unidade geralmente consiste num pequeno programa quântico, juntamente com uma ou mais condições que verificam a correção desse programa.
Estas condições podem surgir sob a forma de qualquer um dos _factos_, que verificam os valores das suas entradas, ou _afirmações_, que verificam os estados de um ou mais qubits passados como entrada.

Por exemplo, `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` representa o facto matemático de que $1 + 1 = 2$, enquanto representa a condição de que a `AssertQubit(One, qubit)` medição `qubit` devolverá um com `One` certeza.
No primeiro caso, podemos verificar a correção da condição dado apenas os seus valores, enquanto neste último, temos de saber algo sobre o estado do qubit para avaliar a afirmação.

As Q# bibliotecas-padrão fornecem várias funções diferentes para representar factos, incluindo:

- <xref:Microsoft.Quantum.Diagnostics.Fact>
- <xref:Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact>
- <xref:Microsoft.Quantum.Diagnostics.NearEqualityFactC>
- <xref:Microsoft.Quantum.Diagnostics.EqualityFactI>


### <a name="testing-qubit-states"></a>Teste estados qubit ###

Na prática, as afirmações baseiam-se no facto de que as simulações clássicas da mecânica quântica não precisam de obedecer ao [teorema da não clonagem,](https://arxiv.org/abs/quant-ph/9607018)de modo a podermos fazer medições e afirmações não físicas quando usamos um simulador para a nossa máquina-alvo.
Assim, podemos testar operações individuais num simulador clássico antes de implementar em hardware.
Nas máquinas-alvo que não permitem a avaliação de afirmações, as chamadas <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> podem ser ignoradas com segurança.

De uma forma mais geral, a <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> operação afirma que a medição dos qubits dados na base pauli dada terá sempre o resultado dado.
Se a afirmação falhar, a corrida termina ligando `fail` com a mensagem dada.
Por predefinição, esta operação não é implementada; os simuladores que podem apoiá-lo devem fornecer uma implementação que executa a verificação do tempo de execução.
`AssertMeasurement` tem assinatura `((Pauli[], Qubit[], Result, String) -> ())` .
Uma vez `AssertMeasurement` que é uma função com um tuple vazio como seu tipo de saída, nenhum efeito de ter chamado `AssertMeasurement` são observáveis dentro de um Q# programa.

A <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> função de operação afirma que a medição dos qubits dados na dada base Pauli terá o resultado dado com a probabilidade dada, dentro de alguma tolerância.
A tolerância é aditivo (por exemplo, `abs(expected-actual) < tol` ).
Se a afirmação falhar, a corrida termina ligando `fail` com a mensagem dada.
Por predefinição, esta operação não é implementada; os simuladores que podem apoiá-lo devem fornecer uma implementação que executa a verificação do tempo de execução.
`AssertMeasurementProbability` tem assinatura `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)` . O primeiro dos `Double` parâmetros dá a probabilidade desejada do resultado, e o segundo a tolerância.

Podemos fazer mais do que afirmar uma única medição, usando que a informação clássica utilizada por um simulador para representar o estado interno de um qubit é passível de copiar, de modo que não precisamos realmente de realizar uma medição para testar a nossa afirmação.
Em particular, isto permite-nos raciocinar sobre medições *incompatíveis* que seriam impossíveis em hardware real.

Suponha que `P : Qubit => Unit` seja uma operação destinada a preparar o estado $\ket{\psi}$ quando a sua entrada estiver no estado $\ket {0} $.
Deixe $\ket{\psi'}$ ser o estado real preparado por `P` .
Em seguida, $\ket{\psi} = \ket{\psi'}$ se e somente se medir $\ket{\psi}} no eixo descrito por $\ket{\psi}$ sempre regressa `Zero` .
Ou seja, \start{align} \ket{\psi} = \ket{\psi}} \text{ if if } \braket{\psi | \psi'} = 1.
\end{align} Utilizando as operações primitivas definidas no prelúdio, podemos efetuar diretamente uma medição que retorne `Zero` se $\ket{\psi}} for um eigenstate de um dos operadores pauli.


A operação <xref:Microsoft.Quantum.Diagnostics.AssertQubit> fornece uma abreviatura particularmente útil para fazê-lo no caso de pretendermos testar a afirmação $\ket{\psi} = \ket {0} $.
Isto é comum, por exemplo, quando não temos acomputação de devolver os qubits de ancilla a $\ket {0} $ antes de os libertar.
Afirmar contra $\ket {0} $ também é útil quando queremos afirmar que duas preparações e operações estatais preparam o mesmo `P` `Q` estado, e quando `Q` `Adjoint` apoiamos .
Em particular,

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

De um modo mais geral, porém, podemos não ter acesso a afirmações sobre estados que não coincidem com os estados da Eigenstates dos operadores da Pauli.
Por exemplo, $\ket{\psi} = (\ket {0} + e^{i \pi / 8} \ket {1} ) / \sqrt {2} $ não é um eigenstate de qualquer operador Pauli, de modo que não podemos usar <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> para determinar exclusivamente que um estado $\ket{\psi'}$ é igual a $\ket{\psi}$.
Em vez disso, temos de decompor a afirmação $\ket{\psi}} = \ket{\psi}$ em pressupostos que podem ser testados diretamente usando os primitivos suportados pelo nosso simulador.
Para tal, deixe $\ket{\psi} = \alfa \ket {0} + \beta \ket {1} $ para números complexos $\alpha = a \_ r + a \_ i$ e $\beta$.
Note que esta expressão requer quatro números reais $ \{ a \_ r, a \_ i, \_ b, b \_ i $ para especificar, uma vez que cada número complexo pode ser expresso como a soma \} de uma parte real e imaginária.
Devido à fase global, no entanto, podemos escolher $a \_ i = 0$, de modo que só precisamos de três números reais para especificar um estado de um único qubit.

Assim, precisamos de especificar três afirmações que são independentes umas das outras para afirmar o estado que esperamos.
Fazemos isso encontrando a probabilidade de observar `Zero` para cada medida Pauli dado $\alpha$ e $\beta$, e afirmando cada um de forma independente.
Deixe $x$, $y$, e $z$ sejam `Result` valores para as medições de Pauli $X$, $Y$e $Z$ respectivamente.
Em seguida, utilizando a função de probabilidade para medições quânticas, \begin{align} \Pr(x = \texttt{Zero} | \alpha, \beta) & = \frac12 + a \_ r b r + a i b \_ \_ \_ \\ \\ \Pr(y = \texttt{Zero} | \alpha, \beta) & = \frac12 + a r b i - a i b \_ \_ \_ \_ \\ \\ \Pr(z = \texttt{Zero} | \alpha, \beta) & = \frac12\left( 1 + a \_ r^2 + a \_ i^2 + b \_ r^2 + b \_ i^2 \direita).
\end{align}

A <xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance> operação implementa estas afirmações dadas representações de $\alpha$ e $\beta$ como valores do tipo <xref:Microsoft.Quantum.Math.Complex> .
Isto é útil quando o estado esperado pode ser calculado matematicamente.

### <a name="asserting-equality-of-quantum-operations"></a>Afirmação da Igualdade das Operações Quânticas ###

Até agora, temos estado preocupado com as operações de ensaio que se destinam a preparar determinados Estados.
Muitas vezes, porém, estamos interessados em como uma operação age para inputs arbitrários e não para uma única entrada fixa.
Por exemplo, suponhamos que implementámos uma operação `U : ((Double, Qubit[]) => () : Adjoint)` correspondente a uma família de operadores unitários $U(t)$, e fornecemos um bloco explícito em vez de utilizar `adjoint` `adjoint auto` .
Podemos estar interessados em afirmar que $U^\dagger(t) = U(-t)$, como esperado se $t$ representar um tempo de evolução.

Em termos gerais, existem duas estratégias diferentes que podemos seguir para afirmar que duas operações `U` e agir de forma `V` idêntica.
Primeiro, podemos verificar se `U(target); (Adjoint V)(target);` preserva cada estado numa determinada base.
Segundo, podemos verificar se `U(target); (Adjoint V)(target);` agir em metade de um estado emaranhado preserva esse emaranhado.
Estas estratégias são implementadas pelas operações canónicas <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> e, respectivamente.

> [!NOTE]
> A afirmação referida discutida acima de obras baseadas no [isomorfismo Choi-Jamiłkowski](https://en.wikipedia.org/wiki/Channel-state_duality), um quadro matemático que relaciona operações em $n$ qubits a estados emaranhados em qubits de $2n$
> Em particular, a operação de identidade em $n$ qubits é representada por cópias $n$ do estado emaranhado $\ket{\beta_ {00} } \mathrel{:=} (\ket {00} + \ket) {11} / \sqrt {2} $.
> A operação <xref:Microsoft.Quantum.Preparation.PrepareChoiState> implementa este isomorfismo, preparando um estado que representa uma determinada operação.

Grosso modo, estas estratégias distinguem-se por uma troca temporal.
A iteração através de cada estado de entrada leva tempo adicional, enquanto a utilização do emaranhado como referência requer o armazenamento de qubits adicionais.
Nos casos em que uma operação implementa uma operação clássica reversível, de tal forma que só estamos interessados no seu comportamento em estados computacionais, <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis> testa a igualdade neste restrito conjunto de entradas.

> [!TIP]
> A iteração sobre os estados de entrada é tratada pelas operações de enumeração <xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct> e <xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower> .
> Estas operações são úteis de forma mais geral para a aplicação de uma operação a cada elemento do produto Cartesiano entre dois ou mais conjuntos.

No entanto, mais criticamente, as duas abordagens testam diferentes propriedades das operações em análise.
Uma vez que a afirmação no local chama cada operação várias vezes, uma vez para cada estado de entrada, quaisquer escolhas aleatórias e resultados de medição podem mudar entre chamadas.
Em contrapartida, a afirmação referenciada chama a cada operação exatamente uma vez, de modo a verificar se as operações são iguais *num único tiro*.
Ambos os testes são úteis para garantir a correção dos programas quânticos.


## <a name="further-reading"></a>Ler Mais ##

- <xref:microsoft.quantum.guide.testingdebugging>
- <xref:Microsoft.Quantum.Diagnostics>
