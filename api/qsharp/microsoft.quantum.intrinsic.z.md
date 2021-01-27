---
uid: Microsoft.Quantum.Intrinsic.Z
title: Operação Z
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Z
qsharp.summary: >-
  Applies the Pauli $Z$ gate.

  \begin{align} \sigma_z \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}. \end{align}
ms.openlocfilehash: 02c7cb4dfd13fb5be12e81188b4f388b70fb3241
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817318"
---
# <a name="z-operation"></a><span data-ttu-id="cb064-102">Operação Z</span><span class="sxs-lookup"><span data-stu-id="cb064-102">Z operation</span></span>

<span data-ttu-id="cb064-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="cb064-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="cb064-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cb064-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cb064-105">Aplica o portão pauli $Z$.</span><span class="sxs-lookup"><span data-stu-id="cb064-105">Applies the Pauli $Z$ gate.</span></span>

<span data-ttu-id="cb064-106">\start{align} \sigma_z \mathrel{:=} \start{bmatrix} 1 & \\ \\ 0 0 & -1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="cb064-106">\begin{align} \sigma_z \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="cb064-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="cb064-107">\end{align}</span></span>

```qsharp
operation Z (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cb064-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="cb064-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="cb064-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cb064-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cb064-110">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="cb064-110">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cb064-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb064-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

