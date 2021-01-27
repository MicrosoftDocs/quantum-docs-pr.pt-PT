---
uid: Microsoft.Quantum.Canon.HY
title: Operação HY
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: HY
qsharp.summary: >-
  Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.

  The Y Hadamard transformation $H_Y = S H$ on a single qubit is:

  \begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}. \end{align}
ms.openlocfilehash: 119d78c4cd8d5e5d92cb54ff652b082a1b99ae06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840448"
---
# <a name="hy-operation"></a><span data-ttu-id="ae073-102">Operação HY</span><span class="sxs-lookup"><span data-stu-id="ae073-102">HY operation</span></span>

<span data-ttu-id="ae073-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ae073-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ae073-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ae073-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ae073-105">Aplica o analógico y-base à transformação Hadamard que troca os eixos Z e Y.</span><span class="sxs-lookup"><span data-stu-id="ae073-105">Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.</span></span>

<span data-ttu-id="ae073-106">A transformação Y Hadamard $H_Y = S H$ num único qubit é:</span><span class="sxs-lookup"><span data-stu-id="ae073-106">The Y Hadamard transformation $H_Y = S H$ on a single qubit is:</span></span>

<span data-ttu-id="ae073-107">\start{align} H_Y \mathrel{:=} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ i & -i \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="ae073-107">\begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}.</span></span>
<span data-ttu-id="ae073-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="ae073-108">\end{align}</span></span>

```qsharp
operation HY (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ae073-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="ae073-109">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="ae073-110">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ae073-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ae073-111">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="ae073-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ae073-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ae073-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ae073-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ae073-113">See Also</span></span>

- [<span data-ttu-id="ae073-114">Microsoft.Quantum.Intrínseco.H</span><span class="sxs-lookup"><span data-stu-id="ae073-114">Microsoft.Quantum.Intrinsic.H</span></span>](xref:Microsoft.Quantum.Intrinsic.H)