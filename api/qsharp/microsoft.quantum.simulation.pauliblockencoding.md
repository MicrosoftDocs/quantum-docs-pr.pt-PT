---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: Função PauliBlockEncoding
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: b1df6d239e6ef061cf0a4784c652e9dd126991d5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230434"
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

A norma única dos coeficientes $\alpha=\sum_{j}[alpha_j

## <a name="second-parameter"></a>Segundo parâmetro

Um `BlockEncodingReflection` $U de dólar unitário do Hamiltonian $H dólares. Como este unitário satisfaz $U^2 = I$, é também uma reflexão.

## <a name="remarks"></a>Observações

Isto obtém-se preparando e despreparando o estado $\sum_{j}sqrt{\alpha_j/\alpha}\ket{j}$, e construindo uma unidade unitária controlada por multiplicássi <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> e <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .