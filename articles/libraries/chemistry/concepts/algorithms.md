---
title: Simular a Dinâmica Hamiltoniana
description: Aprenda a usar fórmulas Trotter-Suzuki e qubitização para trabalhar com simulações hamiltonianas.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 5dad4e4a77eea99e72eb2efac52eec61ebbdb21c
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320721"
---
# <a name="simulating-hamiltonian-dynamics"></a>Simular a Dinâmica Hamiltoniana

Uma vez que o Hamiltonian tenha sido expresso como uma soma de operadores elementares, a dinâmica pode então ser compilada em operações fundamentais do portal utilizando uma série de técnicas bem conhecidas.
Três abordagens eficientes incluem fórmulas Trotter-Suzuki, combinações lineares de unitárias e qubitização.
Explicamos estas três abordagens abaixo e damos exemplos concretos de Q# de como implementar estes métodos usando a biblioteca de simulação Hamiltonian.


## <a name="trottersuzuki-formulas"></a>Fórmulas Trotter-Suzuki
A ideia por trás das fórmulas Trotter-Suzuki é simples: expressar o Hamiltonian como uma soma de fácil simular Hamiltonians e, em seguida, aproximar a evolução total como uma sequência destas evoluções mais simples.
Em particular, deixe $H=\sum_{j=1}^m H_j$ seja o Hamiltonian.
Em seguida, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O (m^2 t^2), $$ que é dizer que, se $t\ll 1$, então o erro nesta aproximação torna-se insignificante.
Note que se $e^{-i H t}$ fosse um exponencial comum, então o erro nesta aproximação não seria $O (m^2 t^2)$: seria zero.
Este erro ocorre porque $e^{-iHt}$ é um operador exponencial e, como resultado, há um erro incorrido ao utilizar esta fórmula devido ao facto de os termos $H_j$ não se deslocarem *(isto é,* $H_j H_k \ne H_k H_j$ em geral).

Se $t$ for grande, as fórmulas Trotter-Suzuki ainda podem ser usadas para simular a dinâmica com precisão, dividindo-a numa sequência de curtos passos de tempo.
Deixe $r$ seja o número de passos dados na evolução do tempo, para que cada passo corra pelo tempo $t/r$. Então, temos que $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\direita)^r + O(m^2 t^^2/r), $$ o que implica que se $r$ escalacomo $m^2/\epsilon$ então o erro pode ser cometido no máximo $\epsilon$ por qualquer $\epsilon>0$.

Aproximações mais precisas podem ser construídas construindo uma sequência de exponenciais do operador de modo a que os termos de erro cancelem.
A fórmula mais simples, a segunda encomenda fórmula Trotter-Suzuki, toma a forma $$ U_2(t) = \left(\prod_{j=1}^{m} e^-iH_j t/2r} \prod_{j=m}^1 e^{-iH_j t/2r}\right)^r = e^{-iHt} + O (m^t^t^t^t^t^t^t^t 3/r^2), $$ o erro do qual pode ser feito menos de $\epsilon$ por qualquer $\epsilon>0$, escolhendo $r$ para escalar como $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.

Fórmulas ainda mais altas, especificamente ($2k$)th-order para $k>0$, pode ser construído de forma recursiva: $$ U_{2k}(t) = [U_{2k-2}(s_k\~ t)]^2 U_{2k-2}([1-4s_k]t) [U_{2k-2}(s_k\~ t)^2 = e^{-iHt} + O (m t)^{2k+1}/r^{2k}), $$ onde $s_k = (4-4^{1/(2k-1)}^{-1}$.

A fórmula seguinte é a quarta encomenda ($k=2$), originalmente introduzida pela Suzuki: $$ U_4(t) = [U_2(s_2\~ t)]^2 U_2([1-4s_2]t) [U_2(s_2\~ t)]^2 = e^{-iHt} +O(m^5t^5/r^4), $$ onde $s_2 = (4-4^{1/3){-1}^
Em geral, as fórmulas arbitrariamente de alta ordem podem ser construídas de forma semelhante; no entanto, os custos incorridos com a utilização de integradores mais complexos superam frequentemente os benefícios para além da quarta ordem para a maioria dos problemas práticos.

Para que as estratégias acima funcionassem, precisamos de ter um método para simular uma grande classe de $e^{-iH_j t}$.
A família mais simples de Hamiltonians, e indiscutivelmente mais útil, que poderíamos usar aqui são operadores Pauli.
Os operadores pauli podem ser facilmente simulados porque podem ser diagonalizados usando operações clifford (que são portões padrão na computação quântica).
Além disso, uma vez nadiagonaldos, os seus valores eigen podem ser encontrados calculando a paridade dos qubits em que agem.

Por exemplo, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ onde $$ e^{-i Z \otimes Z t} = \start{bmatrix} e{{-it} & 0 & 0 & 0 \\\
        0 & e^{i t} & 0 & 0 e 0 \\\
        0 & 0 & e^{it} & 0 \\\
        0 & 0 & 0 & e^{-it} \end{bmatrix}.
$$ Aqui, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ e $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, que pode ser visto diretamente como consequência do facto de que a paridade de $00$ é $0$ enquanto a paridade da cadeia bit $01$ é $1$1$1$.

Os exponencials dos operadores pauli podem ser implementados diretamente em Q# usando a operação <xref:microsoft.quantum.intrinsic.exp>:
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

Para os Hamiltonianos Fermiónicos, a [decomposição Jordan-Wigner mapeia](xref:microsoft.quantum.chemistry.concepts.jordanwigner) convenientemente o Hamiltoniano numa soma de operadores pauli.
Isto significa que a abordagem acima pode ser facilmente adaptada à simulação de química.
Em vez de circular manualmente sobre todos os termos de Pauli na representação Jordan-Wigner, abaixo está um simples exemplo de como executar tal simulação dentro da química seria.
O nosso ponto de partida é uma [codificação Jordan-Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) do Hamiltonian Fermionic, expressa em código como um exemplo da classe `JordanWignerEncoding`.

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

Este formato da representação Jordan-Wigner que é consumível pelos algoritmos de simulação Q# é um tipo definido pelo utilizador `JordanWignerEncodingData`.
Dentro do Q#, este formato é passado para uma função de conveniência `TrotterStepOracle` que devolve um operador aproximando a evolução do tempo usando o integrador Trotter-Suzuki, além de outros parâmetros necessários para a sua execução.

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

Importante, esta implementação aplica algumas otimizações discutidas na [Simulação de Estrutura Eletrónica Hamiltonians Usando Computadores Quânticos](https://arxiv.org/abs/1001.3855) e [Melhorando Algoritmos Quânticos para A Química Quântica](https://arxiv.org/abs/1403.1539) para minimizar o número de rotações de qubit único necessárias, bem como reduzir erros de simulação.

## <a name="qubitization"></a>Qubitização

Qubitização é uma abordagem alternativa à simulação que usa ideias de caminhadas quânticas para simular dinâmicas quânticas.
Embora a qubitização exija mais qubits do que as fórmulas Trotter, o método promete uma escala ideal com o tempo de evolução e a tolerância ao erro.
Por estas razões, tornou-se um método favorável para simular a dinâmica hamiltoniana em geral e para resolver o problema da estrutura electrónica em particular.

A um nível elevado, a qubitização consegue isso através dos seguintes passos.
Primeiro, deixe $H=\sum_j h_j H_j$ para $H_j$ unitário e hermitiano e $h_j\ge 0$.
Ao realizar um par de reflexões, a qubitização implementa um operador equivalente a $$W=e{\pm i \cos^{-1}(H/hh_1)},$$ onde $hh_1 = \sum_j h_j$.
O passo seguinte passa pela transformação dos valores eigen do operador ambulante de $e^{i\pm \cos^{-1}(E_k/h[h]_1)}$, onde $E_k$ são os valores eigen de $H$ para $e^{-iE_k t}$.
Isto pode ser conseguido usando uma variedade de métodos de transformação de valor singular quântico, incluindo [o processamento de sinal quântico.](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)

Alternativamente, se apenas forem desejadas quantidades estáticas (como a energia do estado terrestre do Hamiltonian), então basta aplicar a estimativa de [fase](xref:microsoft.quantum.libraries.characterization) diretamente para $W$ para estimar a energia do estado terrestre do resultado, tomando o cosine do resultado.
Isto é significativo porque permite que a transformação espectral seja realizada clássicamente em vez de usar um método de transformação de valor singular quântico.

Num nível mais detalhado, a implementação da qubitização requer duas subrotinas que fornecem as interfaces para o Hamiltonian.
Ao contrário dos métodos Trotter-Suzuki, estas subrotinas não são quânticas e não clássicas e a sua implementação exigirá a utilização de qubits logarithmicamente mais do que seria necessário para uma simulação baseada em Trotter.

A primeira subrotina quântica que a qubitização usa chama-se $\operatorname{Select}$ e promete-se que produz \start{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} onde cada $H_j$ é assumido como Hermitiano e unitário.
Embora isto possa parecer restritivo, lembre-se que os operadores pauli são hermitianos e unitários e, por isso, aplicações como a simulação de química quântica caem naturalmente nesta estrutura.
A operação $\operatorname{Select}$ operação, talvez surpreendentemente, é na verdade uma operação de reflexão.
Isto pode ser visto pelo facto de que $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} {{\psi}$ uma vez que cada $H_j$ é unitário e Hermitiano e, portanto, tem valores eigenvalues $\pm 1$.

A segunda subrotina chama-se $\operatorname {Prepare}$.
Enquanto a operação selecionada fornece um meio de aceder coerentemente a cada um dos termos Hamiltonianos $H_j$ a subrotina de preparação dá um método de acesso aos coeficientes $h_j$, \start{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{
\end{equation} Então, utilizando um portão de fase controlado multiplicado, vemos que $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 \\\
        \ket{x} & \text{otherwise} \end{cases}.
$$

O nome de $\operador{Prepare}$ não é usado diretamente na qubitização, mas é usado para implementar uma reflexão sobre o estado de que o nome de operador de $\{Prepare}$ cria $$ {start{ R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname {Prepare} \Lambda \operatorname{Prepare}{-1}}
\end{align} $$

O operador ambulante, $W$, pode ser expresso em termos do nome de $\operador{Select}$ e $R$ como $$ W = \operatorname{Select} R, $$ que novamente pode ser visto para implementar um operador equivalente (até um isometry) a $e^{\pm i \cos^{-1}(H/h__1)}}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}...}.}...}.}.}...}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.......}.}.}...}.}.}.}.}.}.}.....}.}.}.

Estas subrotinas são fáceis de configurar em Q#.
Como exemplo, considere o simples qubit transversal-Ising Hamiltonian onde $H = X_1 + X_2 + Z_1 Z_2$.
Neste caso, o código Q# que implementaria o nome de $\operatorname{Select}$ é invocado por <xref:microsoft.quantum.canon.multiplexoperations>, enquanto que o nome de operador de $\operador{Prepare}$ pode ser implementado utilizando <xref:microsoft.quantum.preparation.preparearbitrarystate>.
Um exemplo que envolve simular o modelo Hubbard pode ser encontrado como uma [amostra Q#](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).

Especificar manualmente estes passos para problemas de química arbitrária exigiria muito esforço, o que é evitado usando a biblioteca de química.
À semelhança do algoritmo de simulação Trotter-Suzuki acima, o `JordanWignerEncodingData` é passado para a função de conveniência `QubitizationOracle` que devolve o walk-operator, além de outros parâmetros necessários para a sua execução.

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

Importante, a implementação <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> é aplicável aos hamiltonianos arbitrários especificados como uma combinação linear de cordas Pauli.
Uma versão otimizada para simulações de química é invocada usando <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.
Esta versão é otimizada para minimizar o número de portões T utilizando técnicas discutidas na [codificação de Espectros Eletrónicos em Circuitos Quânticos com Complexidade Linear T](https://arxiv.org/abs/1805.03662).
