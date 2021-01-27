---
uid: Microsoft.Quantum.Arrays.Merged
title: Função fundida
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: 262e7450188370212a7e2a57bf15e9f8ab162814
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845614"
---
# <a name="merged-function"></a><span data-ttu-id="7d718-102">Função fundida</span><span class="sxs-lookup"><span data-stu-id="7d718-102">Merged function</span></span>

<span data-ttu-id="7d718-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7d718-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7d718-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d718-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d718-105">Tendo em conta duas matrizes ordenadas, devolve uma única matriz contendo os elementos de ambos em ordem ordenada.</span><span class="sxs-lookup"><span data-stu-id="7d718-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="7d718-106">Usado internamente por tipo de fusão.</span><span class="sxs-lookup"><span data-stu-id="7d718-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="7d718-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="7d718-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="7d718-108">comparação: ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7d718-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="7d718-109">esquerda : 'T[]</span><span class="sxs-lookup"><span data-stu-id="7d718-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="7d718-110">direito : 'T[]</span><span class="sxs-lookup"><span data-stu-id="7d718-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="7d718-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="7d718-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7d718-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="7d718-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7d718-113">'T</span><span class="sxs-lookup"><span data-stu-id="7d718-113">'T</span></span>

