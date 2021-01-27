---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: Função PurifiedMixedStateWithData
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: fc7bf8e6157af079ae4233ef45e67ce8ddfb8fe3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854286"
---
# <a name="purifiedmixedstatewithdata-function"></a>Função PurifiedMixedStateWithData

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve uma operação que prepara uma purificação de um dado estado misto, enredada num registo que representa uma determinada recolha de dados.
Um "estado misto purificado com dados" refere-se a um estado do formulário Σi √pi |i⟩ |xi⟩ |garbagei⟩, onde cada xi é um bitstring codificando dados adicionais associados ao registo |i⟩.

Veja https://arxiv.org/pdf/1805.03662.pdf?page=15 mais na discussão.

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Descrição

Usa a técnica de ROM quântica para representar uma determinada matriz de densidade, devolvendo essa representação como uma operação de preparação do estado.

Em particular, dada uma lista de coeficientes de $N$ $\alpha_j$, e um bitstring $\vec{x}_j$ associado a cada coeficiente, esta função devolve uma operação que usa a técnica de ROM quântica para preparar uma aproximação $$ \start{alinhar} \tilde\rho = \soma_{j = 0}^{N - 1} p_j \ket{j}bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j} \end{align} $$ do estado misto $$ \begin{align} \rho = \soma_{j = 0}^{N-1}\ frac{|alpha_j|} {\sum_k |\alpha_k|} \ket{j}\bra{j} \otimes \ket{\vec{x}_j}}\bra{\vec{x}_j, \end{align} $$ onde cada $p_j$ é uma aproximação ao coeficiente dado $\alpha_j$ tal que $$ start \{|{} p_j - \frac{|\alpha_j| } { \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ por cada $j$.

Quando passou um registo de índices e um registo de qubits de lixo, inicialmente no estado {0} $\ket \ket {00\cdots 0}, a operação devolvida prepara ambos os registos na purificação de $\tilde \rho$, \$ \start{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j} \ket{\vec{x}}_j} \ket{\text{garbage}_j}, \end{align} $$ tal que repor e negociar o lixo regista a preparação desejada para dentro do erro-alvo $\eps

## <a name="input"></a>Entrada

### <a name="targeterror--double"></a>targetError : [Duplo](xref:microsoft.quantum.lang-ref.double)

O erro do alvo $\epsilon$.


### <a name="coefficients--doublebool"></a>coeficientes :[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Bool](xref:microsoft.quantum.lang-ref.bool)[][].

Array de coeficientes de $N$ especificando a probabilidade de estados de base, juntamente com o bitstring $\vec{x}_j$ associado a cada coeficiente.
Números negativos $-\alpha_j$ serão tratados como positivos $|alpha_j|$.



## <a name="output--mixedstatepreparation"></a>Saída : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

Uma operação que prepara $\tilde \rho$ como purificação para um índice conjunto e registo de lixo.

## <a name="remarks"></a>Observações

Os coeficientes fornecidos a esta operação são normalizados seguindo a norma 1, de modo que os coeficientes são sempre considerados para descrever uma distribuição de probabilidades categóricas válida.

## <a name="references"></a>Referências

- Codificação de Espectros Eletrónicos em Circuitos Quânticos com Complexidade Linear T Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Preparation.PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)