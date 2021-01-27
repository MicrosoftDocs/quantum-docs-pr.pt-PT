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
# <a name="_jwoptimizedz-operation"></a><span data-ttu-id="f6aca-102">operação _JWOptimizedZ</span><span class="sxs-lookup"><span data-stu-id="f6aca-102">_JWOptimizedZ operation</span></span>

<span data-ttu-id="f6aca-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f6aca-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="f6aca-104">Pacote: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f6aca-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="f6aca-105">Aplica uma rotação Rz, com um truque C-NOT para dobrar fase na estimativa de fase.</span><span class="sxs-lookup"><span data-stu-id="f6aca-105">Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.</span></span>

```qsharp
operation _JWOptimizedZ (angle : Double, parityQubit : Qubit, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f6aca-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f6aca-106">Input</span></span>

### <a name="angle--double"></a><span data-ttu-id="f6aca-107">ângulo : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f6aca-107">angle : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f6aca-108">Ângulo de rotação Rz.</span><span class="sxs-lookup"><span data-stu-id="f6aca-108">Angle of Rz rotation.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="f6aca-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f6aca-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f6aca-110">Qubit que determina o sinal da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="f6aca-110">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="f6aca-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f6aca-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="f6aca-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f6aca-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

