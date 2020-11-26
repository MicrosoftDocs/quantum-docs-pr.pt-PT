---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: Função BlockEncodingToReflection
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: 742d4f5623c7c26810998f6c96e2c7b05cc452d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225351"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="e563c-102">Função BlockEncodingToReflection</span><span class="sxs-lookup"><span data-stu-id="e563c-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="e563c-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e563c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e563c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e563c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e563c-105">Converte um `BlockEncoding` em `BLockEncodingReflection` equivalente.</span><span class="sxs-lookup"><span data-stu-id="e563c-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="e563c-106">Ou seja, dado um `BlockEncoding` $U$ unitário que codifica algum operador $H de juros, converte-o num `BlockEncodingReflection` $U'$ que codifica o mesmo operador, mas também satisfaz $U'^\dagger = U'$.</span><span class="sxs-lookup"><span data-stu-id="e563c-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="e563c-107">Isto aumenta o tamanho do registo auxiliar de $U$ por um qubit.</span><span class="sxs-lookup"><span data-stu-id="e563c-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="e563c-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="e563c-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="e563c-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="e563c-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="e563c-110">Um `BlockEncoding` $U unitário para ser convertido num reflexo.</span><span class="sxs-lookup"><span data-stu-id="e563c-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="e563c-111">Saída : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="e563c-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="e563c-112">Um $U unitário'$ agindo conjuntamente em registos `a` e `s` que codifica $H$, e satisfaz $U'^\dagger = U'$.</span><span class="sxs-lookup"><span data-stu-id="e563c-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="e563c-113">Observações</span><span class="sxs-lookup"><span data-stu-id="e563c-113">Remarks</span></span>

<span data-ttu-id="e563c-114">Isto aumenta o tamanho do registo auxiliar de $U$ por um qubit.</span><span class="sxs-lookup"><span data-stu-id="e563c-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="e563c-115">Referências</span><span class="sxs-lookup"><span data-stu-id="e563c-115">References</span></span>

- <span data-ttu-id="e563c-116">Simulação Hamiltonian por Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="e563c-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="e563c-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e563c-117">See Also</span></span>

- [<span data-ttu-id="e563c-118">Microsoft.Quantum.Simulation.BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="e563c-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="e563c-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="e563c-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)