---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: Função BoolArrayAsBigInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 5a85fd9f81cec0f2de7e7807622aab9604a4db7c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214318"
---
# <a name="boolarrayasbigint-function"></a><span data-ttu-id="d0ac1-102">Função BoolArrayAsBigInt</span><span class="sxs-lookup"><span data-stu-id="d0ac1-102">BoolArrayAsBigInt function</span></span>

<span data-ttu-id="d0ac1-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="d0ac1-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="d0ac1-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d0ac1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d0ac1-105">Converte uma certa variedade de Booleans para um número inteiro equivalente.</span><span class="sxs-lookup"><span data-stu-id="d0ac1-105">Converts a given array of Booleans to an equivalent big integer.</span></span>
<span data-ttu-id="d0ac1-106">O elemento 0 da matriz é a parte menos significativa do grande número inteiro.</span><span class="sxs-lookup"><span data-stu-id="d0ac1-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a><span data-ttu-id="d0ac1-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="d0ac1-107">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="d0ac1-108">a : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="d0ac1-108">a : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>





## <a name="output--bigint"></a><span data-ttu-id="d0ac1-109">Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d0ac1-109">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="d0ac1-110">Observações</span><span class="sxs-lookup"><span data-stu-id="d0ac1-110">Remarks</span></span>

<span data-ttu-id="d0ac1-111">Consulte [c# Grande Construtor de BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="d0ac1-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>