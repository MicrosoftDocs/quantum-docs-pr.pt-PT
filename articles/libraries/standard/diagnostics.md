---
title: Q# bibliotecas padrão - diagnósticos / Microsoft Docs
description: Q# bibliotecas padrão - diagnósticos
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 67ec6780d8cbbda7223d46026a9df97cebc92b33
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820985"
---
# <a name="diagnostics"></a>Diagnósticos #

Tal como no desenvolvimento clássico, é importante ser capaz de diagnosticar erros e erros em programas quânticos.
As bibliotecas padrão Q# fornecem uma variedade de maneiras diferentes para garantir a correção dos programas quânticos, conforme detalhado em <xref:microsoft.quantum.techniques.testing-and-debugging>.
Em grande parte, este suporte vem sob a forma de funções e operações que instruem a máquina-alvo a fornecer informações de diagnóstico adicionais ao programa de acolhimento ou programador, ou impor a correção das condições e invariantes expressas pela função ou operação.

## <a name="machine-diagnostics"></a>Diagnósticos de Máquinas ##

Os diagnósticos sobre valores clássicos podem ser obtidos utilizando a função <xref:microsoft.quantum.intrinsic.message> para registar uma mensagem de forma dependente da máquina.
Por padrão, isto escreve a corda para a consola.
Usado juntamente com cordas interpoladas, <xref:microsoft.quantum.intrinsic.message> facilita a reportagem de informações de diagnóstico sobre valores clássicos:

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message` tem assinatura `(String -> Unit)`, representando novamente que emitir uma mensagem de registo de depuração não pode ser observado a partir de Q#.

Os <xref:microsoft.quantum.diagnostics.dumpmachine> e <xref:microsoft.quantum.diagnostics.dumpregister> callables instruem as máquinas-alvo para fornecer informações de diagnóstico sobre todos os qubits atualmente atribuídos ou sobre um registo específico de qubits, respectivamente.
Cada máquina-alvo varia em que informações de diagnóstico são fornecidas em resposta a uma instrução de despejo.
A máquina-alvo [do simulador de estado completo,](xref:microsoft.quantum.machines.full-state-simulator) por exemplo, fornece o programa de acolhimento com o vetor de estado que usa internamente para representar um registo de qubits.
Em comparação, a máquina-alvo do [simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) fornece uma única broca clássica para cada qubit.

 Para saber mais sobre a produção de `DumpMachine` [do simulador de estado](xref:microsoft.quantum.machines.full-state-simulator) completo, dê uma olhada na secção de funções de despejo do nosso artigo de teste e [depuração.](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions)


## <a name="facts-and-assertions"></a>Factos e Afirmações ##

Tal como discutido em [Ensaios e Depuração,](xref:microsoft.quantum.techniques.testing-and-debugging)uma função ou operação com `Unit -> Unit` de assinatura ou `Unit => Unit`, respectivamente, pode ser marcada como um *teste de unidade*.
Cada teste de unidade consiste geralmente num pequeno programa quântico, juntamente com uma ou mais condições que verificam a correção desse programa.
Estas condições podem surgir sob a forma de _factos_, que verificam os valores das suas inputs, ou _afirmações_, que verificam os estados de um ou mais qubits aprovados como entrada.

Por exemplo, `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` representa o facto matemático de que $1 + 1 = 2$, enquanto `AssertQubit(One, qubit)` representa a condição de que a medição `qubit` devolverá uma `One` com certeza.
No primeiro caso, podemos verificar a correção da condição dada apenas os seus valores, enquanto neste último, temos de saber algo sobre o estado do qubit para avaliar a afirmação.

As bibliotecas padrão Q# fornecem várias funções diferentes para representar factos, incluindo:

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfactc>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a>Ensaio estados qubit ###

Na prática, as afirmações baseiam-se no facto de que as simulações clássicas da mecânica quântica não precisam de obedecer ao [teorema](https://arxiv.org/abs/quant-ph/9607018)de não clonagem , de modo a que possamos fazer medições e afirmações não físicas ao utilizar um simulador para a nossa máquina-alvo.
Assim, podemos testar operações individuais num simulador clássico antes de implantar em hardware.
Nas máquinas-alvo que não permitem a avaliação de afirmações, as chamadas para <xref:microsoft.quantum.intrinsic.assert> podem ser ignoradas com segurança.

De um modo mais geral, a operação <xref:microsoft.quantum.intrinsic.assert> afirma que medir os qubits dado na base pauli dada terá sempre o resultado dado.
Se a afirmação falhar, a execução termina chamando `fail` com a mensagem dada.
Por predefinição, esta operação não é implementada; simuladores que possam apoiá-lo devem fornecer uma implementação que execute a verificação do tempo de funcionamento.
`Assert` tem `((Pauli[], Qubit[], Result, String) -> ())`de assinatura.
Uma vez que `Assert` é uma função com um tuple vazio como o seu tipo de saída, nenhum efeito de ter chamado `Assert` são observáveis dentro de um programa Q#.

A função de funcionamento <xref:microsoft.quantum.intrinsic.assertprob> afirma que medir os qubits dado na base pauli dada terá o resultado dado com a probabilidade dada, dentro de alguma tolerância.
A tolerância é aditiva (por exemplo, `abs(expected-actual) < tol`).
Se a afirmação falhar, a execução termina chamando `fail` com a mensagem dada.
Por predefinição, esta operação não é implementada; simuladores que possam apoiá-lo devem fornecer uma implementação que execute a verificação do tempo de funcionamento.
`AssertProb` tem `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`de assinatura. O primeiro dos parâmetros `Double` dá a probabilidade desejada do resultado, e o segundo a tolerância.

Podemos fazer mais do que afirmar uma única medição, usando que a informação clássica utilizada por um simulador para representar o estado interno de um qubit é passível de copiar, de modo a que não precisemos realmente de efetuar uma medição para testar a nossa afirmação.
Em particular, isto permite-nos raciocinar sobre medições *incompatíveis* que seriam impossíveis no hardware real.

Suponha que `P : Qubit => Unit` é uma operação destinada a preparar o Estado $\ket{\psi}$ quando a sua entrada estiver no estado $\ket{0}$.
Deixe $\ket{\psi'}$ ser o estado real preparado por `P`.
Em seguida, $\ket{\psi} = \ket{\psi'}$ se e apenas se medir $\ket{\psi'}$ no eixo descrito por $\ket{\psi}$ sempre regressa `Zero`.
Ou seja, \start{align} \ket{\psi} = \ket{\psi'} \text{ se e apenas se } \braket{\psi / \psi'} = 1.
\end{align} Utilizando as operações primitivas definidas no prelúdio, podemos executar diretamente uma medição que retorna `Zero` se $\ket{\psi}$ for um eigenstate de um dos operadores Pauli.


A operação <xref:microsoft.quantum.diagnostics.assertqubit> fornece uma abreviatura particularmente útil para fazê-lo no caso de querermos testar a afirmação $\ket{\psi} = \ket{0}$.
Isto é comum, por exemplo, quando não temos computação para devolver qubits de oscilação a $\ket{0}$ antes de os lançar.
Afirmar contra $\ket{0}$ também é útil quando queremos afirmar que duas operações de preparação estatal `P` e `Q` preparam o mesmo estado, e quando `Q` apoia `Adjoint`.
Em particular,

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

De um modo mais geral, porém, podemos não ter acesso a afirmações sobre Estados que não coincidem com os eigenstates dos operadores pauli.
Por exemplo, $\ket{\psi} = (\ket{0} + e^{i \pi / 8} \ket{1}) / \sqrt{2}$ não é um eigenstate de qualquer operador pauli, de tal forma que não podemos usar <xref:microsoft.quantum.intrinsic.assertprob> para determinar de forma única que um estado $\ket{\psi'}$ é igual a $\ket{\psi}$.
Em vez disso, temos de decompor a afirmação $\ket{\psi'} = \ket{\psi}$ em pressupostos que podem ser testados diretamente usando os primitivos suportados pelo nosso simulador.
Para tal, deixe $\ket{\psi} = \alpha \ket{0} + \beta \ket{1}$ para números complexos $\alpha = um\_r + um\_i$ e $\beta$.
Note que esta expressão requer quatro números reais $\{um\_r, um\_i, b\_r, b\_i\}$ para especificar, uma vez que cada número complexo pode ser expresso como a soma de uma parte real e imaginária.
Devido à fase global, no entanto, podemos escolher $a\_i = 0$, de tal forma que só precisamos de três números reais para especificar de forma única um estado de qubit único.

Assim, precisamos de especificar três afirmações independentes umas das outras, a fim de afirmar o Estado que esperamos.
Fazemos isso encontrando a probabilidade de observar `Zero` para cada medição de Pauli dada $\alfa$ e $\beta$, e afirmando cada um de forma independente.
Que $x$, $y$, e $z$ sejam `Result` valores para as medições de Pauli $X$, $Y$e $Z$ respectivamente.
Em seguida, utilizando a função de probabilidade para medições quânticas, \start{align} \Pr(x = \texttt{Zero} / \alpha, \beta) & = \frac12 + a\_r b\_r + a\_i b\_i \\\\ \Pr(y = \texttt{Zero}  \alfa, \beta) & = \frac12 + um\_r b\_i - um\_i b\_r \\\\ \Pr(z = \texttt{Zero}  \alfa, \beta) & = \frac12\left( 1 + a\_r^2 + um\_i^2 + b\_r^2 + b\_i^2 \direita).
\fim{align}

A operação <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> implementa estas afirmações dadas representações de $\alpha$ e $\beta$ como valores de tipo <xref:microsoft.quantum.math.complex>.
Isto é útil quando o estado esperado pode ser calculado matematicamente.

### <a name="asserting-equality-of-quantum-operations"></a>Afirmando a Igualdade das Operações Quânticas ###

Até agora, temos estado preocupados com as operações de ensaio que se destinam a preparar determinados Estados.
Muitas vezes, porém, estamos interessados em saber como funciona uma operação para inputs arbitrários e não para uma única entrada fixa.
Por exemplo, suponha que implementámos uma operação `U : ((Double, Qubit[]) => () : Adjoint)` correspondente a uma família de operadores unitários $U(t)$, e fornecemos um bloco de `adjoint` explícito em vez de usar `adjoint auto`.
Podemos estar interessados em afirmar que $U^\dagger(t) = U(-t)$, como esperado se $t$ represente um tempo de evolução.

Em termos gerais, há duas estratégias diferentes que podemos seguir para afirmar que duas operações `U` e `V` agir de forma idêntica.
Primeiro, podemos verificar se `U(target); (Adjoint V)(target);` preserva cada Estado numa determinada base.
Segundo, podemos verificar que `U(target); (Adjoint V)(target);` agindo em metade de um estado emaranhado preserva esse emaranhado.
Estas estratégias são implementadas pelas operações canonias <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> e <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>, respectivamente.

> [!NOTE]
> A afirmação referenciada discutida acima de obras baseadas no [isomorfismo Choi-Jamiłkowski](https://en.wikipedia.org/wiki/Channel-state_duality), um quadro matemático que diz respeito a operações em qubits de $n$ a estados emaranhados em qubits de 2n$.
> Em particular, a operação de identidade em qubits de $n$ é representada por cópias $n$ do estado emaranhado $\ket {\beta_{00}} \mathrel{:=} (\ket{00} + \ket{11}) / \sqrt{2}$.
> A operação <xref:microsoft.quantum.preparation.preparechoistate> implementa este isomorfismo, preparando um estado que representa uma determinada operação.

Mais ou menos, estas estratégias distinguem-se por uma troca espaço-tempo.
Iterar através de cada estado de entrada leva tempo adicional, enquanto usar o emaranhado como referência requer armazenar qubits adicionais.
Nos casos em que uma operação implementa uma operação clássica reversível, de modo a que só estejamos interessados no seu comportamento em estados computacionais, <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> testa a igualdade neste conjunto restrito de inputs.

> [!TIP]
> A iteração sobre os estados de entrada é tratada pelas operações de enumeração <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> e <xref:microsoft.quantum.canon.iteratethroughcartesianpower>.
> Estas operações são mais úteis de uma forma mais geral para aplicar uma operação a cada elemento do produto cartesiano entre dois ou mais conjuntos.

No entanto, mais criticamente, as duas abordagens testam diferentes propriedades das operações em análise.
Uma vez que a afirmação no local chama várias vezes cada operação, uma vez para cada estado de entrada, quaisquer escolhas aleatórias e resultados de medição podem mudar entre chamadas.
Em contrapartida, a afirmação referenciada chama a cada operação exatamente uma vez, de modo a verificar se as operações são iguais *num único tiro.*
Ambos os testes são úteis para garantir a correção dos programas quânticos.


## <a name="further-reading"></a>Continuar a ler ##

- <xref:microsoft.quantum.techniques.testing-and-debugging>
- <xref:microsoft.quantum.diagnostics>
