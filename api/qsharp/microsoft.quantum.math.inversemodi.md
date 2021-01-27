---
uid: Microsoft.Quantum.Math.InverseModI
title: Função InverseModI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 474146e644bcd042e85b917bc43135a674bedce1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846894"
---
# <a name="inversemodi-function"></a><span data-ttu-id="e42a2-102">Função InverseModI</span><span class="sxs-lookup"><span data-stu-id="e42a2-102">InverseModI function</span></span>

<span data-ttu-id="e42a2-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e42a2-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e42a2-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e42a2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e42a2-105">Devoluções $b$ de modo que $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span><span class="sxs-lookup"><span data-stu-id="e42a2-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="e42a2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e42a2-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="e42a2-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e42a2-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e42a2-108">O número invertido</span><span class="sxs-lookup"><span data-stu-id="e42a2-108">The number being inverted</span></span>


### <a name="modulus--int"></a><span data-ttu-id="e42a2-109">módulo : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e42a2-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e42a2-110">O módulo segundo o qual os números são invertidos</span><span class="sxs-lookup"><span data-stu-id="e42a2-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--int"></a><span data-ttu-id="e42a2-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e42a2-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e42a2-112">Inteiro $b$ tal que $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span><span class="sxs-lookup"><span data-stu-id="e42a2-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>