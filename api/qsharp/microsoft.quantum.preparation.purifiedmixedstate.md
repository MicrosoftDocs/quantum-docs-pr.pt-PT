---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: Função Do Estado-Metado Purificado
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 594a1d9fa674e457ab88072ade4198283b677af6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854294"
---
# <a name="purifiedmixedstate-function"></a>Função Do Estado-Metado Purificado

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve uma operação que prepara uma purificação de um dado estado misto.
Um "estado misto purificado" refere-se aos estados da forma |ψ⟩ = Σi √pi |i⟩ |garbagei⟩ especificado por um vetor de coeficientes {pi}. Os estados desta forma podem ser reduzidos a estados mistos ≔ pi |i⟩⟨i| rastreando o registo "lixo" (isto é, um estado misto que é diagonal na base computacional).

Veja https://arxiv.org/pdf/1805.03662.pdf?page=15 mais na discussão.

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Descrição

Usa a técnica de ROM quântica para representar uma determinada matriz de densidade, devolvendo essa representação como uma operação de preparação do estado.

Em particular, dada uma lista de coeficientes de $N$ $\alpha_j$, esta função devolve uma operação que utiliza a técnica de ROM quântica para preparar uma aproximação $$ \start{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \0Ket{j}\bra{j} \end{align} $$ do estado misto $$ \start{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|} {\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ onde cada $p_j$ é uma aproximação ao coeficiente dado $\alpha_j$ tal que $$ \start{align} \left| p_j - \frac{|\alpha_j| } { \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ por cada $j$.

Quando passou um registo de índices e um registo de qubits de lixo, inicialmente no estado {0} $\ket \ket {00\cdots 0}, a operação devolvida prepara ambos os registos na purificação de $\tilde \rho$, \$ \start{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}ket{\text{garbage}_j}, \end{align}

## <a name="input"></a>Entrada

### <a name="targeterror--double"></a>targetError : [Duplo](xref:microsoft.quantum.lang-ref.double)

O erro do alvo $\epsilon$.


### <a name="coefficients--double"></a>coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Conjunto de coeficientes de $N$ especificando a probabilidade dos estados de base.
Números negativos $-\alpha_j$ serão tratados como positivos $|alpha_j|$.



## <a name="output--mixedstatepreparation"></a>Saída : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

Uma operação que prepara $\tilde \rho$ como purificação para um índice conjunto e registo de lixo.

## <a name="example"></a>Exemplo

O seguinte corte de código prepara uma purificação do estado $\rho=\rho=\sum_{j=0}^ {4} \frac{|alpha_j|} {\sum_k |\alpha_k|} \ket{j}\bra{j}$, onde $\vec\alpha=(1.0, 2.0, 3.0, 4.0, 5.0)$, e o erro alvo é $10^ {-3} $:

```qsharp
let coefficients = [1.0, 2.0, 3.0, 4.0, 5.0];
let targetError = 1e-3;
let purifiedState = PurifiedMixedState(targetError, coefficients);
using (indexRegister = Qubit[purifiedState::Requirements::NIndexQubits]) {
    using (garbageRegister = Qubit[purifiedState::Requirements::NGarbageQubits]) {
        purifiedState::Prepare(LittleEndian(indexRegister), new Qubit[0], garbageRegister);
    }
}
```

## <a name="remarks"></a>Observações

Os coeficientes fornecidos a esta operação são normalizados seguindo a norma 1, de modo que os coeficientes são sempre considerados para descrever uma distribuição de probabilidades categóricas válida.

## <a name="references"></a>Referências

- Codificação de Espectros Eletrónicos em Circuitos Quânticos com Complexidade Linear T Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Preparation.PurifiedMixedStateWithData](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)