---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: função _PauliBlockEncoding
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: ba30a7e87bd970961dc87f048aa586ff5c512e2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710664"
---
# <a name="_pauliblockencoding-function"></a>função _PauliBlockEncoding

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [](https://nuget.org/packages/)


Cria uma unidade de codificação de blocos para um Hamiltonian.

O hamiltoniano $H=\sum_{j}\alpha_j P_j$ é descrito por uma soma de termos Pauli $P_j$, cada um com coeficiente real $\alpha_j$.

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Entrada

### <a name="generatorsystem--generatorsystem"></a>sistema gerador : [Sistema gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Um `GeneratorSystem` que descreve $H$ como uma soma de termos Pauli


### <a name="stateprepunitary--double---littleendian--unit-adj--ctl"></a>EstadoPrepUnitário : [Duplo](xref:microsoft.quantum.lang-ref.double)[] -> [Unidade LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl

Uma operação unitária $V$ que aplica o $V_j$ unitário controlado no índice $\ket{j}$, dada uma função $f: j\rightarrow V_j$.


### <a name="multiplexer--intint---qubit--unit-adj--ctl---littleendianqubit--unit-adj--ctl"></a>multiplexer :[(Int,](xref:microsoft.quantum.lang-ref.int)[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl) ->[(LittleEndian,](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = unidade> Adj + [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl





## <a name="output--doubleblockencodingreflection"></a>Saída : ([Duplo,](xref:microsoft.quantum.lang-ref.double)[BlockEncodingReflection)](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

## <a name="first-parameter"></a>Primeiro parâmetro

A norma única dos coeficientes $\alpha=\sum_{j}[alpha_j

## <a name="second-parameter"></a>Segundo parâmetro

Um `BlockEncodingReflection` $U de dólares unitários do Hamiltonian $U dólares. Como este unitário satisfaz $U^2 = I$, é também uma reflexão.

## <a name="remarks"></a>Observações

Operações de exemplo a preparar e despreparar o estado $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, e construir uma unidade unitária controlada por multiplierinas são <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> e <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .