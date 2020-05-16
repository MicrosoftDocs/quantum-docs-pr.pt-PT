---
title: Diagnósticos nas bibliotecas padrão Q#
description: Conheça as funções e operações de diagnóstico nas bibliotecas padrão Q# usadas para capturar erros ou erros em programas quânticos.
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: fa5173f710dd9e0b0b2c110e45aa0bf019111aca
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426316"
---
# <a name="diagnostics"></a>Diagnóstico #

Tal como no desenvolvimento clássico, é importante ser capaz de diagnosticar erros e erros em programas quânticos.
As bibliotecas padrão Q# fornecem uma variedade de maneiras diferentes para garantir a correção dos programas quânticos, conforme detalhado em <xref:microsoft.quantum.guide.testingdebugging> .
Em grande parte, este suporte vem sob a forma de funções e operações que instruem a máquina-alvo a fornecer informações de diagnóstico adicionais ao programa de acolhimento ou programador, ou a impor a correção das condições e invariantes expressas pela função ou chamada de operação.

## <a name="machine-diagnostics"></a>Diagnósticos de Máquinas ##

Os diagnósticos sobre valores clássicos podem ser obtidos utilizando a <xref:microsoft.quantum.intrinsic.message> função para registar uma mensagem de forma dependente da máquina.
Por padrão, isto escreve a corda para a consola.
Usado juntamente com cordas interpoladas, <xref:microsoft.quantum.intrinsic.message> facilita a reportagem de informações de diagnóstico sobre valores clássicos:

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message`tem assinatura , mais uma vez representando que emitir uma mensagem de `(String -> Unit)` registo de depuração não pode ser observado a partir de Q#.

Os <xref:microsoft.quantum.diagnostics.dumpmachine> <xref:microsoft.quantum.diagnostics.dumpregister> e callables instruem as máquinas-alvo para fornecer informações de diagnóstico sobre todos os qubits atualmente atribuídos ou sobre um registo específico de qubits, respectivamente.
Cada máquina-alvo varia em que informações de diagnóstico são fornecidas em resposta a uma instrução de despejo.
A máquina-alvo [do simulador de estado completo,](xref:microsoft.quantum.machines.full-state-simulator) por exemplo, fornece o programa de acolhimento com o vetor de estado que usa internamente para representar um registo de qubits.
Em comparação, a máquina-alvo do [simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) fornece uma única broca clássica para cada qubit.

 Para saber mais sobre a produção [do simulador de estado completo,](xref:microsoft.quantum.machines.full-state-simulator) dê uma olhada na secção de funções de despejo do nosso artigo de teste e `DumpMachine` [depuração.](xref:microsoft.quantum.guide.testingdebugging#dump-functions)


## <a name="facts-and-assertions"></a>Factos e Afirmações ##

Conforme discutido em [Testes e Depuração,](xref:microsoft.quantum.guide.testingdebugging)uma função ou operação com assinatura `Unit -> Unit` `Unit => Unit` ou, respectivamente, pode ser marcado como um *teste de unidade*.
Cada teste de unidade consiste geralmente num pequeno programa quântico, juntamente com uma ou mais condições que verificam a correção desse programa.
Estas condições podem surgir sob a forma de _factos_, que verificam os valores das suas inputs, ou _afirmações_, que verificam os estados de um ou mais qubits aprovados como entrada.

Por exemplo, `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` representa o facto matemático de que $1 + 1 = 2$, enquanto representa a condição de que a `AssertQubit(One, qubit)` medição `qubit` devolverá um com `One` certeza.
No primeiro caso, podemos verificar a correção da condição dada apenas os seus valores, enquanto neste último, temos de saber algo sobre o estado do qubit para avaliar a afirmação.

As bibliotecas padrão Q# fornecem várias funções diferentes para representar factos, incluindo:

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfactc>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a>Ensaio estados qubit ###

Na prática, as afirmações baseiam-se no facto de que as simulações clássicas da mecânica quântica não precisam de obedecer ao [teorema](https://arxiv.org/abs/quant-ph/9607018)de não clonagem , de modo a que possamos fazer medições e afirmações não físicas ao utilizar um simulador para a nossa máquina-alvo.
Assim, podemos testar operações individuais num simulador clássico antes de implantar em hardware.
Nas máquinas-alvo que não permitem a avaliação de afirmações, as chamadas <xref:microsoft.quantum.intrinsic.assert> podem ser ignoradas com segurança.

De um modo mais geral, a <xref:microsoft.quantum.intrinsic.assert> operação afirma que medir os qubits dado na base pauli dada terá sempre o resultado dado.
Se a afirmação falhar, a execução termina ligando `fail` com a mensagem dada.
Por predefinição, esta operação não é implementada; simuladores que possam apoiá-lo devem fornecer uma implementação que execute a verificação do tempo de funcionamento.
`Assert`tem `((Pauli[], Qubit[], Result, String) -> ())` assinatura.
Uma vez `Assert` que é uma função com um tuple vazio como o seu tipo de saída, nenhum efeito de ter chamado são observáveis dentro de `Assert` um programa Q#.

A <xref:microsoft.quantum.intrinsic.assertprob> função de operação afirma que medir os qubits dado na base Pauli dada terá o resultado dado com a probabilidade dada, dentro de alguma tolerância.
A tolerância é aditiva (por `abs(expected-actual) < tol` exemplo).
Se a afirmação falhar, a execução termina ligando `fail` com a mensagem dada.
Por predefinição, esta operação não é implementada; simuladores que possam apoiá-lo devem fornecer uma implementação que execute a verificação do tempo de funcionamento.
`AssertProb`tem `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)` assinatura. O primeiro dos `Double` parâmetros dá a probabilidade desejada do resultado, e o segundo a tolerância.

Podemos fazer mais do que afirmar uma única medição, usando que a informação clássica utilizada por um simulador para representar o estado interno de um qubit é passível de copiar, de modo a que não precisemos realmente de efetuar uma medição para testar a nossa afirmação.
Em particular, isto permite-nos raciocinar sobre medições *incompatíveis* que seriam impossíveis no hardware real.

Suponha que `P : Qubit => Unit` seja uma operação destinada a preparar o Estado $\ket{\psi}$ quando a sua entrada estiver no estado {0} $\ket $.
Deixe $\ket{\psi'}$ ser o estado real preparado por `P` .
Em seguida, $\ket{\psi} = \ket{\psi'}$ se e apenas se medir $\ket{\psi'}$ no eixo descrito por $\ket{\psi}$ sempre devolve `Zero` .
Ou seja, \start{align} \ket{\psi} = \ket{\psi'} \text{ se e apenas se } \braket{\psi / \psi'} = 1.
\end{align} Utilizando as operações primitivas definidas no prelúdio, podemos executar diretamente uma medição que retorna `Zero` se $\ket{\psi}$ for um eigenstate de um dos operadores Pauli.


A operação <xref:microsoft.quantum.diagnostics.assertqubit> fornece uma abreviatura particularmente útil para fazê-lo no caso de querermos testar a afirmação $\ket{\psi} = \ket {0} $.
Isto é comum, por exemplo, quando não temos computação para devolver qubits de oscilação a $\ket $ antes de {0} os libertar.
Afirmar contra $\ket $ também é útil quando queremos afirmar que dois estados {0} preparam `P` e `Q` operações tanto para preparar o mesmo estado, como quando `Q` apoia `Adjoint` .
Em particular,

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

De um modo mais geral, porém, podemos não ter acesso a afirmações sobre Estados que não coincidem com os eigenstates dos operadores pauli.
Por exemplo, $\ket{\psi} = (\ket {0} + e^{i \pi / 8} \ket {1} ) / \sqrt {2} $ não é um eigenstate de qualquer operador pauli, de tal forma que não podemos usar <xref:microsoft.quantum.intrinsic.assertprob> para determinar de forma única que um estado $\ket{\psi'}$ é igual a $\ket{\psi}$.
Em vez disso, temos de decompor a afirmação $\ket{\psi'} = \ket{\psi}$ em pressupostos que podem ser testados diretamente usando os primitivos suportados pelo nosso simulador.
Para tal, deixe $\ket{\psi} = \alpha \ket {0} + \beta \ket {1} $ para números complexos $\alpha = um \_ r + a \_ i$ e $\beta$.
Note que esta expressão requer quatro números reais $ \{ a \_ r, \_ a i, b, b i $ para especificar, uma vez que cada número complexo pode ser expresso como a soma de uma parte real \_ e \_ \} imaginária.
Devido à fase global, no entanto, podemos escolher $a \_ i = 0$, de tal forma que só precisamos de três números reais para especificar de forma única um estado de qubit único.

Assim, precisamos de especificar três afirmações independentes umas das outras, a fim de afirmar o Estado que esperamos.
Fazemos isso encontrando a probabilidade de observar cada medição de `Zero` Pauli dada $\alfa$ e $\beta$, e afirmando cada um de forma independente.
Que $x$, $y$e $z$ sejam `Result` valores para as medições de Pauli $X$, $Y$e $Z$, respectivamente.
Em seguida, utilizando a função de probabilidade para medições quânticas, \start{align} \Pr(x = \texttt{Zero} [ \alpha, \beta) & = \frac12 + a r b + a \_ \_ i b \_ \_ \\ \\ \Pr(y = \texttt{Zero} [ \alfa, \beta) & = \frac12 + a r b i - a i b \_ r \_ \_ \_ \\ \\ \Pr(z = \texttt{Zero} [ \alpha, \beta) & = \frac12\left( 1 + a r^2 + a \_ \_ i^2+ \_ b^2. \_
\fim{align}

A <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> operação implementa estas afirmações dadas representações de $\alpha$ e $\beta$ como valores de tipo <xref:microsoft.quantum.math.complex> .
Isto é útil quando o estado esperado pode ser calculado matematicamente.

### <a name="asserting-equality-of-quantum-operations"></a>Afirmando a Igualdade das Operações Quânticas ###

Até agora, temos estado preocupados com as operações de ensaio que se destinam a preparar determinados Estados.
Muitas vezes, porém, estamos interessados em saber como funciona uma operação para inputs arbitrários e não para uma única entrada fixa.
Por exemplo, suponha que implementámos uma operação `U : ((Double, Qubit[]) => () : Adjoint)` correspondente a uma família de operadores unitários $U(t)$, e fornecemos um bloco explícito em vez de usar `adjoint` `adjoint auto` .
Podemos estar interessados em afirmar que $U^\dagger(t) = U(-t)$, como esperado se $t$ represente um tempo de evolução.

Em termos gerais, há duas estratégias diferentes que podemos seguir para afirmar que duas operações `U` e agir de forma `V` idêntica.
Primeiro, podemos verificar se `U(target); (Adjoint V)(target);` preserva cada estado numa dada base.
Segundo, podemos verificar se `U(target); (Adjoint V)(target);` agir em metade de um estado emaranhado preserva esse emaranhado.
Estas estratégias são implementadas pelas operações canoneais <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced> e, respectivamente.

> [!NOTE]
> A afirmação referenciada discutida acima de obras baseadas no [isomorfismo Choi-Jamiłkowski](https://en.wikipedia.org/wiki/Channel-state_duality), um quadro matemático que diz respeito a operações em qubits de $n$ a estados emaranhados em qubits de 2n$.
> Em particular, a operação de identidade em qubits $n$ é representada por cópias $n$ do estado emaranhado $\ket{\beta_ {00} } \mathrel{:=} {00} (\ket + \ket {11} ) / \sqrt {2} $.
> A operação <xref:microsoft.quantum.preparation.preparechoistate> implementa este isomorfismo, preparando um estado que representa uma determinada operação.

Mais ou menos, estas estratégias distinguem-se por uma troca espaço-tempo.
Iterar através de cada estado de entrada leva tempo adicional, enquanto usar o emaranhado como referência requer armazenar qubits adicionais.
Nos casos em que uma operação implementa uma operação clássica reversível, de modo a que só estejamos interessados no seu comportamento em estados computacionais, testa a <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> igualdade neste conjunto restrito de inputs.

> [!TIP]
> A iteração sobre os estados de entrada é tratada pelas operações de enumeração <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> e <xref:microsoft.quantum.canon.iteratethroughcartesianpower> .
> Estas operações são mais úteis de uma forma mais geral para aplicar uma operação a cada elemento do produto cartesiano entre dois ou mais conjuntos.

No entanto, mais criticamente, as duas abordagens testam diferentes propriedades das operações em análise.
Uma vez que a afirmação no local chama várias vezes cada operação, uma vez para cada estado de entrada, quaisquer escolhas aleatórias e resultados de medição podem mudar entre chamadas.
Em contrapartida, a afirmação referenciada chama a cada operação exatamente uma vez, de modo a verificar se as operações são iguais *num único tiro.*
Ambos os testes são úteis para garantir a correção dos programas quânticos.


## <a name="further-reading"></a>Ler Mais ##

- <xref:microsoft.quantum.guide.testingdebugging>
- <xref:microsoft.quantum.diagnostics>
