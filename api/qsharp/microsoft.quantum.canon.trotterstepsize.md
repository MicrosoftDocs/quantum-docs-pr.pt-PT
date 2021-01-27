---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: Função TrotterStepSize
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840076"
---
# <a name="trotterstepsize-function"></a>Função TrotterStepSize

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Computes Trotter tamanho do passo na implementação recursiva do algoritmo de simulação Trotter.

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>Entrada

### <a name="order--int"></a>ordem : [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Observações

Esta operação utiliza uma convenção de indexação diferente da de [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139). Em particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponde ao escalão $p_2(\lambda)$ em quant-ph/0508139.