---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: Talvez a funçãoBigIntAsInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: b91912f6f669afad888e71174fef6e2e6f8e7156
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713436"
---
# <a name="maybebigintasint-function"></a><span data-ttu-id="f8631-102">Talvez a funçãoBigIntAsInt</span><span class="sxs-lookup"><span data-stu-id="f8631-102">MaybeBigIntAsInt function</span></span>

<span data-ttu-id="f8631-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="f8631-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="f8631-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f8631-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f8631-105">Converte um dado grande inteiro para um inteiro equivalente, se possível.</span><span class="sxs-lookup"><span data-stu-id="f8631-105">Converts a given big integer to an equivalent integer, if possible.</span></span>
<span data-ttu-id="f8631-106">A função devolve um par do inteiro resultante e uma bandeira booleana que é verdade, se e somente se a conversão for possível.</span><span class="sxs-lookup"><span data-stu-id="f8631-106">The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.</span></span>

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a><span data-ttu-id="f8631-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="f8631-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="f8631-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f8631-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--intbool"></a><span data-ttu-id="f8631-109">Saída : ([Int,](xref:microsoft.quantum.lang-ref.int)[Bool)](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f8631-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool))</span></span>



## <a name="remarks"></a><span data-ttu-id="f8631-110">Observações</span><span class="sxs-lookup"><span data-stu-id="f8631-110">Remarks</span></span>

<span data-ttu-id="f8631-111">Consulte [c# Grande Construtor de BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="f8631-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>