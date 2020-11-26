---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZ
title: operação _JWOptimizedZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZ
qsharp.summary: Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.
ms.openlocfilehash: e0b442a7ac237525acdc80e8e79044ebb523f8a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225912"
---
# <a name="_jwoptimizedz-operation"></a><span data-ttu-id="15b35-102">operação _JWOptimizedZ</span><span class="sxs-lookup"><span data-stu-id="15b35-102">_JWOptimizedZ operation</span></span>

<span data-ttu-id="15b35-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="15b35-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="15b35-104">Pacote: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="15b35-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="15b35-105">Aplica uma rotação Rz, com um truque C-NOT para dobrar fase na estimativa de fase.</span><span class="sxs-lookup"><span data-stu-id="15b35-105">Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.</span></span>

```qsharp
operation _JWOptimizedZ (angle : Double, parityQubit : Qubit, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="15b35-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="15b35-106">Input</span></span>

### <a name="angle--double"></a><span data-ttu-id="15b35-107">ângulo : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="15b35-107">angle : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="15b35-108">Ângulo de rotação Rz.</span><span class="sxs-lookup"><span data-stu-id="15b35-108">Angle of Rz rotation.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="15b35-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="15b35-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="15b35-110">Qubit que determina o sinal da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="15b35-110">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="15b35-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="15b35-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="15b35-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15b35-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

