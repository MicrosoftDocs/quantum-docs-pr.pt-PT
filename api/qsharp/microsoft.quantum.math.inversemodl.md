---
uid: Microsoft.Quantum.Math.InverseModL
title: Função InverseModL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e7cb9e98cb0635c50162611f6a52c56027d4a5eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723632"
---
# <a name="inversemodl-function"></a><span data-ttu-id="c8597-102">Função InverseModL</span><span class="sxs-lookup"><span data-stu-id="c8597-102">InverseModL function</span></span>

<span data-ttu-id="c8597-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c8597-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c8597-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c8597-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c8597-105">Devoluções $b$ de modo que $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span><span class="sxs-lookup"><span data-stu-id="c8597-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="c8597-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c8597-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="c8597-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c8597-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c8597-108">O número invertido</span><span class="sxs-lookup"><span data-stu-id="c8597-108">The number being inverted</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="c8597-109">módulo : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c8597-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c8597-110">O módulo segundo o qual os números são invertidos</span><span class="sxs-lookup"><span data-stu-id="c8597-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--bigint"></a><span data-ttu-id="c8597-111">Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c8597-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c8597-112">Inteiro $b$ tal que $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span><span class="sxs-lookup"><span data-stu-id="c8597-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>