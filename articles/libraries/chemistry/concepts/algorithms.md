---
title: Simulando o Hamiltonian Dynamics | Microsoft Docs
description: Simulando documentos conceituais do Hamiltonian Dynamics
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 4d1924386eadb427e8f53bc0a177453a341f185f
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864462"
---
# <a name="simulating-hamiltonian-dynamics"></a>Simulando o Hamiltonian Dynamics

Depois que o Hamiltonian tiver sido expresso como uma soma dos operadores elementares, o Dynamics poderá então ser compilado em operações fundamentais de portão usando uma série de técnicas bem conhecidas.
Três abordagens eficientes incluem as fórmulas Trotter – Suzuki, combinações lineares de unidades e qubitization.
Explicamos essas três abordagens abaixo e fornecemos exemplos concretos de Q # sobre como implementar esses métodos usando a biblioteca de simulação de Hamiltonian.


## <a name="trottersuzuki-formulas"></a>Trotter – fórmulas Suzuki
A ideia por trás das fórmulas Trotter – Suzuki é simples: expresse a Hamiltonian como uma soma de fácil de simular Hamiltonians e, em seguida, aproximar a evolução total como uma sequência dessas evoluções mais simples.
Em particular, permita que $H = \ sum_ {j = 1} ^ m H_j $ seja o Hamiltonian.
Em seguida, $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, que significa que, se $t \ll $1, o erro nessa aproximação se tornará insignificante.
Observe que se $e ^ {-i H} $ fosse um exponencial comum, o erro nessa aproximação não seria $O (m ^ 2 t ^ 2) $: ele seria zero.
Esse erro ocorre porque $e ^ {-iHt} $ é um exponencial de operador e, como resultado, há um erro incorrido ao usar essa fórmula devido ao fato de que os $H _j $ termos não são transformados (*ou seja*, $H _J H_k \ne H_k H_j $ em geral).

Se $t $ for grande, as fórmulas Trotter – Suzuki ainda poderão ser usadas para simular o Dynamics com precisão, dividindo-o em uma sequência de etapas curtas.
Deixe $r $ seja o número de etapas executadas na evolução do tempo.
Em seguida, temos o $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t ^ 2/r), $ $, que implica que, se $r $ for dimensionado como $m ^ 2 t ^ 2/\ épsilon $, o erro poderá ser feito no máximo $ \epsilon $ para qualquer $ \epsilon > 0 $.

As aproximações mais precisas podem ser criadas com a construção de uma sequência de exponenciais de operador, de modo que os termos de erro sejam cancelados.
A fórmula mais simples, a fórmula Trotter simétrica ou a divisão Strang, usa a forma $ $ U_1 (t) = \ prod_ {j = 1} ^ m e ^ {-iH_j t/2} \ prod_ {j = m} ^ 1 e ^ {-iH_j t} = e ^ {-iHt} + O (m ^ 3 t ^ 3), $ $ que pode ser feito com menos de $ \epsilon $ para qualquer $ \epsilon > 0 $ escolhendo $r $ para dimensionar como $m ^ {3/2} t ^ {3/2}/\sqrt {\ Épsilon} $.

As fórmulas Trotter de ordem superior podem ser construídas com base em $U _1 $.
A maneira mais simples é a quarta fórmula de ordem a seguir, introduzido originalmente por Suzuki: $ $ U_2 (t) = U_1 ^ 2 (s_1t) U_1 ([1-4s_1] t) U_1 ^ 2 (s_1 t) = e ^ {-iHt} + O (m ^ 5T ^ 5), $ $ em que $s _1 = (4-4 ^ {1/3}) ^{-1}$.
Em geral, as fórmulas de ordem superior arbitrariamente podem ser construídas de forma semelhante; no entanto, os custos incorridos com o uso de integradores mais complexos geralmente superam os benefícios além da quarta ordem para os problemas mais práticos.

Para fazer com que as estratégias acima funcionem, precisamos ter um método para simular uma ampla classe de $e ^ {-iH_j t} $.
A família mais simples de Hamiltonians e, possivelmente, mais útil, que poderíamos usar aqui são os operadores Pauli.
Os operadores Pauli podem ser facilmente simulados porque podem ser interdiagonals usando operações Clifford (que são Gates padrão na computação Quantum).
Além disso, depois de terem sido diagonais, seus eigenvalues podem ser encontrados computando a paridade do qubits em que eles atuam.

Por exemplo, $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ em que $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-IT} & 0 & 0 & 0 \\\
        0 & e ^ {i t} & 0 & 0 \\\
        0 & 0 & e ^ {IT} & 0 \\\
        0 & 0 & 0 & e ^ {-it} \end{bmatrix}.
$ $ Aqui, $e ^ {-iHt} \ket{00} = e ^ {it} \ket{00}$ e $e ^ {-iHt} \ket{01} = e ^ {-it} \ket{01}$, que pode ser visto diretamente como consequência do fato de que a paridade de $0 $ é $0 $ enquanto a paridade da cadeia de caracteres de bits $1 $ é $1 $.

Os exponencials dos operadores Pauli podem ser implementados diretamente em Q # usando a operação <xref:microsoft.quantum.primitive.exp>:
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies e^{- i X \otimes X t} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

Para Fermionic Hamiltonians, a [decomposição da Jordânia – Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) mapeia de forma conveniente o Hamiltonian para uma soma de operadores de Pauli.
Isso significa que a abordagem acima pode facilmente ser adaptada para simular a química.
Em vez de fazer um loop manual de todos os termos do Pauli na representação da Jordânia-Wigner, veja abaixo um exemplo simples de como a execução dessa simulação dentro do química seria semelhante.
Nosso ponto de partida é uma [codificação Jordânia – Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) do Fermionic Hamiltonian, expressa em código como uma instância da classe `JordanWignerEncoding`.

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

Esse formato da representação Jordânia – Wigner que é consumível pelos algoritmos de simulação do Q # é um tipo definido pelo usuário `JordanWignerEncodingData`.
Em Q #, esse formato é passado para uma função de conveniência `TrotterStepOracle` que retorna um operador aproximar a evolução do tempo usando o Trotter – Suzuki Integrator, além de outros parâmetros necessários para sua execução.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

De forma importante, essa implementação aplica algumas otimizações discutidas em [simulação de estrutura eletrônica Hamiltonians usando computadores Quantum](https://arxiv.org/abs/1001.3855) e [aprimorando os algoritmos Quantum para química da Quantum](https://arxiv.org/abs/1403.1539) para minimizar o número de rotações de qubit simples necessárias, bem como reduzir erros de simulação.

## <a name="qubitization"></a>Qubitization

Qubitization é uma abordagem alternativa para a simulação que usa ideias de exames do Quantum para simular a dinâmica da Quantum.
Embora qubitization exija mais qubits do que as fórmulas do Trotter, o método promete o dimensionamento ideal com o tempo de evolução e a tolerância a erros.
Por esses motivos, ele se tornou um método favorecedo para simular o Hamiltonian Dynamics em geral e para resolver o problema de estrutura eletrônica em particular.

Em um alto nível, o qubitization realiza isso por meio das etapas a seguir.
Primeiro, permita que $H = \ sum_j h_j H_j $ para unitário e Hermitian $H _J $ e $h _j \ge $0.
Ao executar um par de reflexos, o qubitization implementa um operador equivalente a $ $W = e ^ {\pm i \cos ^{-1}(H/| h | _1)}, $ $, em que $ | H | _1 = \ sum_j | h_j | $.
A próxima etapa envolve transformar o eigenvalues do operador de passeio de $e ^ {i\pm \cos ^{-1}(E_k/| h | _1)} $, em que $E _k $ são os eigenvalues de $H $ para $e ^ {-iE_k t} $.
Isso pode ser feito usando uma variedade de métodos de transformação de valor singular de Quantum, incluindo [processamento de sinal de Quantum](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).

Como alternativa, se apenas as quantidades estáticas forem desejadas (como a energia de estado de aterramento do Hamiltonian), será suficiente aplicar a [estimativa de fase](xref:microsoft.quantum.libraries.characterization) diretamente a $W $ para estimar a energia de estado terrestre do resultado, tirando o cosseno do resultado.
Isso é significativo porque permite que a transformação Spectral seja executada de forma clássica em vez de usar um método de transformação de valor singular de Quantum.

Em um nível mais detalhado, a implementação de qubitization requer duas sub-rotinas que fornecem as interfaces para o Hamiltonian.
Ao contrário dos métodos Trotter – Suzuki, essas sub-rotinas são a Quantum não clássica e sua implementação precisará usar o logaritmicamente mais qubits do que seria necessário para uma simulação baseada em Trotter.

A primeira sub-rotina Quantum usada pelo qubitization é chamada de $ \operatorname{Select} $ e é prometida para produzir \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{Equation} em que cada $H _j $ é considerado Hermitian e unitário.
Embora isso pareça restritivo, lembre-se de que os operadores Pauli são Hermitian e unitário e, portanto, aplicativos como a simulação química da Quantum se enquadram naturalmente nessa estrutura.
A operação $ \operatorname{Select} $, talvez surpreendentemente, é, na verdade, uma operação de reflexão.
Isso pode ser visto do fato de que $ \operatorname{Select} ^ 2 \ ket {j} \ket{\psi} = \ket{j} \ket{\psi} $, já que cada $H _j $ é unitário e Hermitian e, portanto, tem eigenvalues $ \pm $1.

A segunda sub-rotina é chamada $ \operatorname{Prepare} $.
Enquanto a operação SELECT fornece um meio de acessar de forma coerente cada um dos termos de Hamiltonian $H _j $ a sub-rotina Prepare fornece um método para acessar os coeficientes $h _j $, \begin{Equation} \operatorname{Prepare}\ket{0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}.
\end{Equation} em seguida, usando um portão de fase controlado por multiplicação, vemos que $ $ \Lambda\ket{0}^ {\otimes n} = \begin{cases} \-\ket{x} & \Text{If} x = 0 \\\
        \ket{x} & \Text{otherwise} \end{cases}.
$$

A operação $ \operatorname{Prepare} $ não é usada diretamente em qubitization, mas, em vez disso, é usada para implementar uma reflexão sobre o estado em que $ \operatorname{Prepare} $ cria $ $ \begin{align} R &amp; = 1-2 \ OperatorName {Prepare} \ket{0}\bra{0} \operatorname{Prepare} ^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^{-1}.
\end{align} $ $

O operador de passeio, $W $, pode ser expresso em termos das operações $ \operatorname{Select} $ e $R $ como $ $ W = \operatorname{Select} R, $ $, que pode ser visto novamente para implementar um operador equivalente (até um isometry) a $e ^ {\pm i \cos ^{-1}(H/| h | _1)} $.

Essas sub-rotinas são fáceis de configurar em Q #.
Como exemplo, considere o simples qubit transversal-Ising Hamiltonian em que $H = X_1 + X_2 + Z_1 Z_2 $.
Nesse caso, o código de Q # que implementaria a operação $ \operatorname{Select} $ é invocado por <xref:microsoft.quantum.canon.multiplexoperations>, enquanto a operação $ \operatorname{Prepare} $ pode ser implementada usando <xref:microsoft.quantum.preparation.preparearbitrarystate>.
Um exemplo que envolve a simulação do modelo Hubbard pode ser encontrado como um [exemplo de Q #](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).

A especificação manual dessas etapas para problemas de química arbitrária exigiria muito esforço, o que é evitado com o uso da biblioteca química.
Da mesma forma que o algoritmo de simulação Trotter – Suzuki acima, o `JordanWignerEncodingData` é passado para a função de conveniência `QubitizationOracle` que retorna o operador de orientação, além de outros parâmetros necessários para sua execução.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

É importante que o <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> de implementação seja aplicável a Hamiltonians arbitrários especificado como uma combinação linear de cadeias de caracteres Pauli.
Uma versão otimizada para simulações de química é invocada usando <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.
Esta versão é otimizada para minimizar o número de T Gates usando técnicas discutidas na [codificação eletrônica de Spectra em circuitos Quantum com complexidade de T linear](https://arxiv.org/abs/1805.03662).
