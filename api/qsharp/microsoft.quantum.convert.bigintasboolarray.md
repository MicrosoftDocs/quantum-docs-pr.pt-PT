---
uid: Microsoft.Quantum.Convert.BigIntAsBoolArray
title: Função BigIntAsBoolArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BigIntAsBoolArray
qsharp.summary: Converts a given big integer to an array of Booleans. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 1ce83389f2ac3ce9ab2898f9d167941ca2973508
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834600"
---
# <a name="bigintasboolarray-function"></a><span data-ttu-id="ee1d7-102">Função BigIntAsBoolArray</span><span class="sxs-lookup"><span data-stu-id="ee1d7-102">BigIntAsBoolArray function</span></span>

<span data-ttu-id="ee1d7-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="ee1d7-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="ee1d7-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ee1d7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ee1d7-105">Converte um grande número de inteiros para uma variedade de Booleans.</span><span class="sxs-lookup"><span data-stu-id="ee1d7-105">Converts a given big integer to an array of Booleans.</span></span>
<span data-ttu-id="ee1d7-106">O elemento 0 da matriz é a parte menos significativa do grande número inteiro.</span><span class="sxs-lookup"><span data-stu-id="ee1d7-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BigIntAsBoolArray (a : BigInt) : Bool[]
```


## <a name="input"></a><span data-ttu-id="ee1d7-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="ee1d7-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="ee1d7-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ee1d7-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bool"></a><span data-ttu-id="ee1d7-109">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="ee1d7-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="ee1d7-110">Observações</span><span class="sxs-lookup"><span data-stu-id="ee1d7-110">Remarks</span></span>

<span data-ttu-id="ee1d7-111">Consulte [c# Grande Construtor de BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="ee1d7-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>