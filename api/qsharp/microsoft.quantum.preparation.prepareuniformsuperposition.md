---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Preparar Operação PrepareUniformSuperposition
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 9b9f182ed7c1ea24ae74b8a2321a309042a17c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230094"
---
# <a name="prepareuniformsuperposition-operation"></a>Preparar Operação PrepareUniformSuperposition

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Cria uma superposição uniforme sobre estados que codificam 0 a `nIndices - 1` .

Ou seja, este $U$ unitário cria uma superposição uniforme sobre todos os estados numerais $0$ a $M-1$, dado um estado de entrada $\ket{0\cdots 0}$. Por outras palavras, $$ \begin{align} U\ket {0} =\frac {1} {\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.
\end{align} $$.

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="nindices--int"></a>nIndices : [Int](xref:microsoft.quantum.lang-ref.int)

O número desejado de estados $M$ na sobreposição uniforme.


### <a name="indexregister--littleendian"></a>indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

O registo qubit que armazena o número afirma em `LittleEndian` formato.
Este registo deve ser capaz de armazenar o número $M-1$, e é assumido como inicializado no estado $\ket{0\cdots 0}$.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

A operação é contígua, mas requer que `indexRegister` esteja numa superposição uniforme sobre os estados de primeira `nIndices` base nesse caso.