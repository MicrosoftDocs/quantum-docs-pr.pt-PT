---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Preparar Operação PrepareUniformSuperposition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 8b57a7a02e9f704cf9677574824dfdc93fff25b0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709460"
---
# <a name="prepareuniformsuperposition-operation"></a>Preparar Operação PrepareUniformSuperposition

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [](https://nuget.org/packages/)


Cria uma superposição uniforme sobre estados que codificam 0 a `nIndices - 1` .

Ou seja, este $U$ unitário cria uma superposição uniforme sobre todos os estados numerais $0$ a $M-1$, dado um estado de entrada $\ket{0\cdots 0}$. Por outras palavras, $$ \begin{align} U\ket {0} =\frac {1} {\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.
\end{align} $$.

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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