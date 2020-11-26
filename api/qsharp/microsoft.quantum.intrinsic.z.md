---
uid: Microsoft.Quantum.Intrinsic.Z
title: Operação Z
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Z
qsharp.summary: >-
  Applies the Pauli $Z$ gate.

  \begin{align} \sigma_z \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}. \end{align}
ms.openlocfilehash: 5bfb435a1e7a7b90da807e7c6edb8358fb006e34
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198440"
---
# <a name="z-operation"></a><span data-ttu-id="62e7b-102">Operação Z</span><span class="sxs-lookup"><span data-stu-id="62e7b-102">Z operation</span></span>

<span data-ttu-id="62e7b-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="62e7b-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="62e7b-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="62e7b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="62e7b-105">Aplica o portão pauli $Z$.</span><span class="sxs-lookup"><span data-stu-id="62e7b-105">Applies the Pauli $Z$ gate.</span></span>

<span data-ttu-id="62e7b-106">\start{align} \sigma_z \mathrel{:=} \start{bmatrix} 1 & \\ \\ 0 0 & -1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="62e7b-106">\begin{align} \sigma_z \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="62e7b-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="62e7b-107">\end{align}</span></span>

```qsharp
operation Z (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="62e7b-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="62e7b-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="62e7b-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="62e7b-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="62e7b-110">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="62e7b-110">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="62e7b-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62e7b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

