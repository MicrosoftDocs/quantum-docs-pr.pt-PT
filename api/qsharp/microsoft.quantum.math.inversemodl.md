---
uid: Microsoft.Quantum.Math.InverseModL
title: Função InverseModL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e09c9da500889dfcb514d0a02dec957bfaa70e1c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851396"
---
# <a name="inversemodl-function"></a><span data-ttu-id="16f08-102">Função InverseModL</span><span class="sxs-lookup"><span data-stu-id="16f08-102">InverseModL function</span></span>

<span data-ttu-id="16f08-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="16f08-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="16f08-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16f08-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="16f08-105">Devoluções $b$ de modo que $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span><span class="sxs-lookup"><span data-stu-id="16f08-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="16f08-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="16f08-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="16f08-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="16f08-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="16f08-108">O número invertido</span><span class="sxs-lookup"><span data-stu-id="16f08-108">The number being inverted</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="16f08-109">módulo : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="16f08-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="16f08-110">O módulo segundo o qual os números são invertidos</span><span class="sxs-lookup"><span data-stu-id="16f08-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--bigint"></a><span data-ttu-id="16f08-111">Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="16f08-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="16f08-112">Inteiro $b$ tal que $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span><span class="sxs-lookup"><span data-stu-id="16f08-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>