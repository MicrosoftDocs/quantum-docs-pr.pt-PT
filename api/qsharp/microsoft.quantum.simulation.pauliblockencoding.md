---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: Função PauliBlockEncoding
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 2e37b40c60d19aa747114de988dddc19f0d7c50b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848011"
---
# <a name="pauliblockencoding-function"></a>Função PauliBlockEncoding

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Cria uma unidade de codificação de blocos para um Hamiltonian.

O hamiltoniano $H=\sum_{j}\alpha_j P_j$ é descrito por uma soma de termos Pauli $P_j$, cada um com coeficiente real $\alpha_j$.

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Entrada

### <a name="generatorsystem--generatorsystem"></a>sistema gerador : [Sistema gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Um `GeneratorSystem` que descreve $H$ como uma soma de termos Pauli



## <a name="output--doubleblockencodingreflection"></a>Saída : ([Duplo,](xref:microsoft.quantum.lang-ref.double)[BlockEncodingReflection)](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

## <a name="first-parameter"></a>Primeiro parâmetro

A norma única dos coeficientes $\alpha=\sum_{j}|\alpha_j|$.

## <a name="second-parameter"></a>Segundo parâmetro

Um `BlockEncodingReflection` $U de dólar unitário do Hamiltonian $H dólares. Como este unitário satisfaz $U^2 = I$, é também uma reflexão.

## <a name="remarks"></a>Observações

Isto obtém-se preparando e despreparando o estado $\sum_{j}sqrt{\alpha_j/\alpha}\ket{j}$, e construindo uma unidade unitária controlada por multiplicássi <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> e <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .