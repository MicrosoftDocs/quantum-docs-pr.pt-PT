---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: Talvez a funçãoBigIntAsInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: d0a598497e8a8f019bbd8da7db1c6cc4d7bde017
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224280"
---
# <a name="maybebigintasint-function"></a><span data-ttu-id="306dd-102">Talvez a funçãoBigIntAsInt</span><span class="sxs-lookup"><span data-stu-id="306dd-102">MaybeBigIntAsInt function</span></span>

<span data-ttu-id="306dd-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="306dd-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="306dd-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="306dd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="306dd-105">Converte um dado grande inteiro para um inteiro equivalente, se possível.</span><span class="sxs-lookup"><span data-stu-id="306dd-105">Converts a given big integer to an equivalent integer, if possible.</span></span>
<span data-ttu-id="306dd-106">A função devolve um par do inteiro resultante e uma bandeira booleana que é verdade, se e somente se a conversão for possível.</span><span class="sxs-lookup"><span data-stu-id="306dd-106">The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.</span></span>

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a><span data-ttu-id="306dd-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="306dd-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="306dd-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="306dd-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--intbool"></a><span data-ttu-id="306dd-109">Saída : ([Int,](xref:microsoft.quantum.lang-ref.int)[Bool)](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="306dd-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool))</span></span>



## <a name="remarks"></a><span data-ttu-id="306dd-110">Observações</span><span class="sxs-lookup"><span data-stu-id="306dd-110">Remarks</span></span>

<span data-ttu-id="306dd-111">Consulte [c# Grande Construtor de BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="306dd-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>