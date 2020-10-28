---
uid: Microsoft.Quantum.Math.ArgComplex
title: Função ArgComplex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 629aa32ad80e5aa3d6f5ff75ac65df9b1a96fc15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723268"
---
# <a name="argcomplex-function"></a><span data-ttu-id="29299-102">Função ArgComplex</span><span class="sxs-lookup"><span data-stu-id="29299-102">ArgComplex function</span></span>

<span data-ttu-id="29299-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="29299-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="29299-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="29299-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="29299-105">Devolve a fase de um número complexo de tipos `Complex` .</span><span class="sxs-lookup"><span data-stu-id="29299-105">Returns the phase of a complex number of type `Complex`.</span></span>

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="29299-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="29299-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="29299-107">entrada : [Complexo](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="29299-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="29299-108">Número complexo $c = x + i y$.</span><span class="sxs-lookup"><span data-stu-id="29299-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="29299-109">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="29299-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="29299-110">Fase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (\pi,\pi]$.</span><span class="sxs-lookup"><span data-stu-id="29299-110">Phase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (-\pi,\pi]$.</span></span>