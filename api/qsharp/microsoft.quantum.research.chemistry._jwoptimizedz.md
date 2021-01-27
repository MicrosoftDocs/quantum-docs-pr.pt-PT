---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZ
title: operação _JWOptimizedZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZ
qsharp.summary: Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.
ms.openlocfilehash: 76c96153b6baf8b593e0770a44b6190c075c8f53
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854238"
---
# <a name="_jwoptimizedz-operation"></a>operação _JWOptimizedZ

Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Pacote: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Aplica uma rotação Rz, com um truque C-NOT para dobrar fase na estimativa de fase.

```qsharp
operation _JWOptimizedZ (angle : Double, parityQubit : Qubit, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="angle--double"></a>ângulo : [Duplo](xref:microsoft.quantum.lang-ref.double)

Ângulo de rotação Rz.


### <a name="parityqubit--qubit"></a>parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit que determina o sinal da evolução do tempo.


### <a name="qubit--qubit"></a>qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

