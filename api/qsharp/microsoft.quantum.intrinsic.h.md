---
uid: Microsoft.Quantum.Intrinsic.H
title: Operação H
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: H
qsharp.summary: >-
  Applies the Hadamard transformation to a single qubit.

  \begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}. \end{align}
ms.openlocfilehash: 6fa712b00a2745d8c0d8d3198cc9c5e6af3e2400
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818990"
---
# <a name="h-operation"></a><span data-ttu-id="04ca6-102">Operação H</span><span class="sxs-lookup"><span data-stu-id="04ca6-102">H operation</span></span>

<span data-ttu-id="04ca6-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="04ca6-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="04ca6-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="04ca6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="04ca6-105">Aplica a transformação hadamard a um único qubit.</span><span class="sxs-lookup"><span data-stu-id="04ca6-105">Applies the Hadamard transformation to a single qubit.</span></span>

<span data-ttu-id="04ca6-106">\start{align} H \mathrel{:=} \frac {1} {\sqrt {2} } \start{bmatrix} 1 & \\ \\ 1 1 & -1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="04ca6-106">\begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="04ca6-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="04ca6-107">\end{align}</span></span>

```qsharp
operation H (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="04ca6-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="04ca6-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="04ca6-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="04ca6-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="04ca6-110">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="04ca6-110">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="04ca6-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="04ca6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

