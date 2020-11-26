---
uid: Microsoft.Quantum.Canon.HY
title: Operação HY
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: HY
qsharp.summary: >-
  Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.

  The Y Hadamard transformation $H_Y = S H$ on a single qubit is:

  \begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}. \end{align}
ms.openlocfilehash: ceca8eab8cb8f16333cd7a1e3c24e6cebe4ec8d7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206838"
---
# <a name="hy-operation"></a><span data-ttu-id="2c007-102">Operação HY</span><span class="sxs-lookup"><span data-stu-id="2c007-102">HY operation</span></span>

<span data-ttu-id="2c007-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2c007-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2c007-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2c007-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2c007-105">Aplica o analógico y-base à transformação Hadamard que troca os eixos Z e Y.</span><span class="sxs-lookup"><span data-stu-id="2c007-105">Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.</span></span>

<span data-ttu-id="2c007-106">A transformação Y Hadamard $H_Y = S H$ num único qubit é:</span><span class="sxs-lookup"><span data-stu-id="2c007-106">The Y Hadamard transformation $H_Y = S H$ on a single qubit is:</span></span>

<span data-ttu-id="2c007-107">\start{align} H_Y \mathrel{:=} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ i & -i \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="2c007-107">\begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}.</span></span>
<span data-ttu-id="2c007-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2c007-108">\end{align}</span></span>

```qsharp
operation HY (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2c007-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="2c007-109">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="2c007-110">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2c007-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2c007-111">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="2c007-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2c007-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c007-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2c007-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2c007-113">See Also</span></span>

- [<span data-ttu-id="2c007-114">Microsoft.Quantum.Intrínseco.H</span><span class="sxs-lookup"><span data-stu-id="2c007-114">Microsoft.Quantum.Intrinsic.H</span></span>](xref:Microsoft.Quantum.Intrinsic.H)