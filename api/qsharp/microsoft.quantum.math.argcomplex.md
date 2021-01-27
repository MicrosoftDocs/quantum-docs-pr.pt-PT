---
uid: Microsoft.Quantum.Math.ArgComplex
title: Função ArgComplex
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: e8ce73a43940ab0ed66338f962cc6f76fc2b694b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842761"
---
# <a name="argcomplex-function"></a><span data-ttu-id="0cbeb-102">Função ArgComplex</span><span class="sxs-lookup"><span data-stu-id="0cbeb-102">ArgComplex function</span></span>

<span data-ttu-id="0cbeb-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0cbeb-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0cbeb-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0cbeb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0cbeb-105">Devolve a fase de um número complexo de tipos `Complex` .</span><span class="sxs-lookup"><span data-stu-id="0cbeb-105">Returns the phase of a complex number of type `Complex`.</span></span>

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="0cbeb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0cbeb-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="0cbeb-107">entrada : [Complexo](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="0cbeb-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="0cbeb-108">Número complexo $c = x + i y$.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="0cbeb-109">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0cbeb-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0cbeb-110">Fase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (\pi,\pi]$.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-110">Phase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (-\pi,\pi]$.</span></span>