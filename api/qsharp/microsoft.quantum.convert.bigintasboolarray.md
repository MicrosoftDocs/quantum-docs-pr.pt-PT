---
uid: Microsoft.Quantum.Convert.BigIntAsBoolArray
title: Função BigIntAsBoolArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BigIntAsBoolArray
qsharp.summary: Converts a given big integer to an array of Booleans. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 593fad99ef22d3c906b9f10adc07638bed227509
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224552"
---
# <a name="bigintasboolarray-function"></a><span data-ttu-id="62ccb-102">Função BigIntAsBoolArray</span><span class="sxs-lookup"><span data-stu-id="62ccb-102">BigIntAsBoolArray function</span></span>

<span data-ttu-id="62ccb-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="62ccb-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="62ccb-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="62ccb-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="62ccb-105">Converte um grande número de inteiros para uma variedade de Booleans.</span><span class="sxs-lookup"><span data-stu-id="62ccb-105">Converts a given big integer to an array of Booleans.</span></span>
<span data-ttu-id="62ccb-106">O elemento 0 da matriz é a parte menos significativa do grande número inteiro.</span><span class="sxs-lookup"><span data-stu-id="62ccb-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BigIntAsBoolArray (a : BigInt) : Bool[]
```


## <a name="input"></a><span data-ttu-id="62ccb-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="62ccb-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="62ccb-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="62ccb-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bool"></a><span data-ttu-id="62ccb-109">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="62ccb-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="62ccb-110">Observações</span><span class="sxs-lookup"><span data-stu-id="62ccb-110">Remarks</span></span>

<span data-ttu-id="62ccb-111">Consulte [c# Grande Construtor de BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="62ccb-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>