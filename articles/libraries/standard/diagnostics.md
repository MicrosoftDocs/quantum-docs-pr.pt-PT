---
title: 'P # bibliotecas padrão-diagnóstico | Microsoft Docs'
description: 'P # bibliotecas padrão-diagnóstico'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: b59f91b660281167eab182529b415b6d379e3d63
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184496"
---
# <a name="diagnostics"></a>Diagnósticos #

Assim como no desenvolvimento clássico, é importante poder diagnosticar erros e erros em programas Quantum.
As bibliotecas padrão de Q # fornecem uma variedade de diferentes maneiras para garantir a exatidão dos programas Quantum, conforme detalhado em <xref:microsoft.quantum.techniques.testing-and-debugging>.
Em grande parte, esse suporte vem na forma de funções e operações que instruem o computador de destino a fornecer informações adicionais de diagnóstico para o programa ou desenvolvedor do host, ou impõem a exatidão das condições e invariáveis expressas pela chamada de função ou operação.

## <a name="machine-diagnostics"></a>Diagnóstico de máquina ##

O diagnóstico sobre valores clássicos pode ser obtido usando a função <xref:microsoft.quantum.intrinsic.message> para registrar uma mensagem de forma dependente do computador.
Por padrão, isso grava a cadeia de caracteres no console.
Usado junto com cadeias de caracteres interpoladas, <xref:microsoft.quantum.intrinsic.message> facilita o relatório de informações de diagnóstico sobre valores clássicos:

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message` tem `(String -> Unit)`de assinatura, novamente representando que a emissão de uma mensagem de log de depuração não pode ser observada em Q #.

Os <xref:microsoft.quantum.diagnostics.dumpmachine> e <xref:microsoft.quantum.diagnostics.dumpregister> que podem ser chamados instruem os computadores de destino a fornecer informações de diagnóstico sobre todos os qubits atualmente alocados ou sobre um registro específico do qubits, respectivamente.
Cada computador de destino varia de acordo com as informações de diagnóstico fornecidas em resposta a uma instrução de despejo.
A máquina de destino do [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator) , por exemplo, fornece o programa de host com o vetor de estado que ele usa internamente para representar um registro de qubits.
Por comparação, a máquina de destino do [Toffoli Simulator](xref:microsoft.quantum.machines.toffoli-simulator) fornece um único bit clássico para cada qubit.

 Para saber mais sobre a saída [do `DumpMachine` do simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator) , dê uma olhada na seção de funções de despejo do nosso [artigo de teste e depuração](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions).


## <a name="facts-and-assertions"></a>Fatos e asserções ##

Conforme discutido em [testando e Depurando](xref:microsoft.quantum.techniques.testing-and-debugging), uma função ou operação com assinatura `Unit -> Unit` ou `Unit => Unit`, respectivamente, pode ser chamada como um *teste de unidade*.
Cada teste de unidade geralmente consiste em um pequeno programa Quantum, juntamente com uma ou mais condições que verificam a exatidão desse programa.
Essas condições podem vir na forma de _fatos_, que verificam os valores de suas entradas ou _asserções_, que verificam os Estados de um ou mais qubits passados como entrada.

Por exemplo, `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` representa o fato matemático que $1 + 1 = $2, enquanto `AssertQubit(One, qubit)` representa a condição que mede `qubit` retornará uma `One` com certeza.
No primeiro caso, podemos verificar a exatidão da condição, dado apenas seus valores, enquanto, no último, devemos saber algo sobre o estado do qubit para avaliar a asserção.

As bibliotecas padrão de Q # fornecem várias funções diferentes para representar fatos, incluindo:

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfact>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a>Testando Estados de qubit ###

Na prática, as asserções dependem do fato de que as simulações clássicas da mecânica quantum não precisam obedecer à [teorema no-Cloning](https://arxiv.org/abs/quant-ph/9607018), de modo que podemos fazer medidas e asserções não físicas ao usar um simulador para o nosso computador de destino.
Portanto, podemos testar operações individuais em um simulador clássico antes de implantar em hardware.
Em computadores de destino que não permitem a avaliação de asserções, chamadas para <xref:microsoft.quantum.intrinsic.assert> podem ser ignoradas com segurança.

Em geral, a operação de <xref:microsoft.quantum.intrinsic.assert> declara que medir o determinado qubits na base de Pauli especificada sempre terá o resultado especificado.
Se a asserção falhar, a execução terminará chamando `fail` com a mensagem determinada.
Por padrão, essa operação não é implementada; os simuladores que podem oferecer suporte a ele devem fornecer uma implementação que executa a verificação de tempo de execução.
`Assert` tem `((Pauli[], Qubit[], Result, String) -> ())`de assinatura.
Como `Assert` é uma função com uma tupla vazia como seu tipo de saída, nenhum efeito de ter chamado `Assert` é observável em um programa Q #.

A função de operação <xref:microsoft.quantum.intrinsic.assertprob> declara que medir o qubits fornecido na base Pauli especificada terá o resultado fornecido com a probabilidade determinada, dentro de certa tolerância.
A tolerância é aditiva (por exemplo, `abs(expected-actual) < tol`).
Se a asserção falhar, a execução terminará chamando `fail` com a mensagem determinada.
Por padrão, essa operação não é implementada; os simuladores que podem oferecer suporte a ele devem fornecer uma implementação que executa a verificação de tempo de execução.
`AssertProb` tem `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`de assinatura. O primeiro dos `Double` parâmetros fornece a probabilidade desejada do resultado e o segundo a tolerância.

Podemos fazer mais do que declarar uma única medida, usando que as informações clássicas usadas por um simulador para representar o estado interno de um qubit é receptivos para copiar, de modo que não precisamos realmente executar uma medida para testar nossa declaração.
Em particular, isso nos permite motivos sobre medidas *incompatíveis* que seriam impossíveis em hardware real.

Suponha que `P : Qubit => Unit` seja uma operação destinada a preparar o estado $ \ket{\psi} $ quando sua entrada estiver no estado $ \ket{0}$.
Deixe que $ \ket{\psi '} $ seja o estado real preparado pelo `P`.
Em seguida, $ \ket{\psi} = \ket{\psi '} $ If e only if mediing $ \ket{\psi '} $ no eixo descrito por $ \ket{\psi} $ sempre retorna `Zero`.
Ou seja, \begin{align} \ket{\psi} = \ket{\psi '} \Text{If e only if} \braket{\psi | \psi '} = 1.
\end{align} usando as operações primitivas definidas no prelúdio, podemos executar diretamente uma medida que retorna `Zero` se $ \ket{\psi} $ for um eigenstate de um dos operadores Pauli.


A operação <xref:microsoft.quantum.diagnostics.assertqubit> fornece uma abreviação particularmente útil para fazer isso, caso queiramos testar a asserção $ \ket{\psi} = \ket{0}$.
Isso é comum, por exemplo, quando não computamos para retornar ancilla qubits a $ \ket{0}$ antes de liberá-los.
A declaração em relação a $ \ket{0}$ também é útil quando desejamos declarar que a preparação de dois Estados `P` e `Q` operações preparam o mesmo estado e quando `Q` dá suporte a `Adjoint`.
Em particular,

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

No entanto, em geral, talvez não tenhamos acesso a asserções sobre Estados que não coincidem com eigenstates de operadores Pauli.
Por exemplo, $ \ket{\psi} = (\ket{0} + e ^ {i \pi/8} \ket{1})/\sqrt{2}$ não é um eigenstate de nenhum operador Pauli, de modo que não podemos usar <xref:microsoft.quantum.intrinsic.assertprob> para determinar exclusivamente que um estado $ \ket{\psi '} $ é igual a $ \ket{\psi} $.
Em vez disso, devemos decompor a asserção $ \ket{\psi '} = \ket{\psi} $ em suposições que podem ser diretamente testadas usando os primitivos suportados pelo nosso simulador.
Para fazer isso, permita que $ \ket{\psi} = \alpha \ket{0} + \beta \ket{1}$ para números complexos $ \alpha = a\_r + a\_i $ e $ \beta $.
Observe que essa expressão requer quatro números reais de $\{um\_r, a\_i, b\_r, b\_i\}$ para especificar, pois cada número complexo pode ser expresso como a soma de uma parte imagináa e real.
No entanto, devido à fase global, podemos escolher $a\_i = $0, de modo que precisamos apenas de três números reais para especificar exclusivamente um estado de qubit único.

Portanto, precisamos especificar três asserções que são independentes umas das outras para declarar o estado esperado.
Fazemos isso encontrando a probabilidade de observar `Zero` para cada medição de Pauli, dada $ \alpha $ e $ \beta $, e declarando cada uma independentemente.
Permita que $x $, $y $ e $z $ sejam `Result` valores para as medidas Pauli $X $, $Y $ e $Z $, respectivamente.
Em seguida, usando a função probabilidade para medições Quantum, \begin{align} \Pr (x = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_r + a\_i b\_i \\\\ \Pr (y = \texttt{Zero} | \alpha , \beta) & = \frac12 + a\_r b\_i-a\_i b\_r \\\\ \Pr (z = \texttt{Zero} | \alpha, \beta) & = \frac12\left (1 + a\_r ^ 2 + a\_i ^ 2 + b\_r ^ 2 + b\_i ^ 2 \right).
\end{align}

A operação <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> implementa essas asserções dadas as representações de $ \alpha $ e $ \beta $ como valores do tipo <xref:microsoft.quantum.math.complex>.
Isso é útil quando o estado esperado pode ser calculado matematicamente.

### <a name="asserting-equality-of-quantum-operations"></a>Declarando a igualdade de operações Quantum ###

Até agora, estamos preocupados com as operações de teste que destinam-se a preparar Estados específicos.
No entanto, muitas vezes estamos interessados em como uma operação atua para entradas arbitrárias em vez de uma única entrada fixa.
Por exemplo, suponha que implementamos uma operação `U : ((Double, Qubit[]) => () : Adjoint)` correspondente a uma família de operadores unitários $U (t) $ e fornecemos um bloco de `adjoint` explícito em vez de usar `adjoint auto`.
Talvez esteja interessado em afirmar que $U ^ \dagger (t) = U (-t) $, conforme esperado se $t $ representa um tempo de evolução.

Em geral, há duas estratégias diferentes que podemos seguir para fazer a asserção de que duas operações `U` e `V` agir de forma idêntica.
Primeiro, podemos verificar se `U(target); (Adjoint V)(target);` preserva cada Estado em uma determinada base.
Em segundo lugar, podemos verificar se `U(target); (Adjoint V)(target);` atuando na metade de um estado confusas preserva esse Entanglement.
Essas estratégias são implementadas pelas operações de Canon <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> e <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>, respectivamente.

> [!NOTE]
> A declaração referenciada mencionada acima funciona com base no [Choi – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality), uma estrutura matemática que relaciona as operações em $n $ qubits a confusas Estados em $2n $ qubits.
> Em particular, a operação de identidade em $n $ qubits é representada por $n as cópias do estado confusas $ \ket{\beta_{00}} \mathrel{: =} (\ket{00} + \ket{11})/\sqrt{2}$.
> A operação <xref:microsoft.quantum.preparation.preparechoistate> implementa esse isomorphism, preparando um estado que representa uma determinada operação.

Aproximadamente, essas estratégias são diferenciadas por uma compensação de espaço em tempo.
A iteração em cada Estado de entrada leva mais tempo, ao passo que o uso de Entanglement como referência requer o armazenamento de qubits adicionais.
Nos casos em que uma operação implementa uma operação clássica reversível, de modo que estamos interessados apenas em seu comportamento nos Estados de base computacional, <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> testar a igualdade nesse conjunto restrito de entradas.

> [!TIP]
> A iteração sobre Estados de entrada é tratada pelas operações de enumeração <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> e <xref:microsoft.quantum.canon.iteratethroughcartesianpower>.
> Essas operações são úteis mais geralmente para aplicar uma operação a cada elemento do produto cartesiano entre dois ou mais conjuntos.

Mais importante, no entanto, as duas abordagens testam diferentes propriedades das operações em exame.
Como a declaração in-loco chama cada operação várias vezes, uma vez para cada Estado de entrada, quaisquer escolhas aleatórias e resultados de medidas podem ser alterados entre as chamadas.
Por outro lado, a declaração referenciada chama cada operação exatamente uma vez, de modo que ela verifica se as operações são iguais *em uma única captura*.
Esses dois testes são úteis para garantir a exatidão dos programas Quantum.


## <a name="further-reading"></a>Leitura adicional ##

- <xref:microsoft.quantum.techniques.testing-and-debugging>
- <xref:microsoft.quantum.diagnostics>
