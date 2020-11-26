---
uid: Microsoft.Quantum.Math.ModulusL
title: Função de módulol
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 5c9a8ceceac5d2cdac6b82f7f74a85e9443382a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194938"
---
# <a name="modulusl-function"></a><span data-ttu-id="ab85e-102">Função de módulol</span><span class="sxs-lookup"><span data-stu-id="ab85e-102">ModulusL function</span></span>

<span data-ttu-id="ab85e-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ab85e-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ab85e-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ab85e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ab85e-105">Calcula o resíduo canónico do `value` `modulus` modulo.</span><span class="sxs-lookup"><span data-stu-id="ab85e-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="ab85e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ab85e-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="ab85e-107">valor : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ab85e-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ab85e-108">O valor do qual o resíduo é calculado</span><span class="sxs-lookup"><span data-stu-id="ab85e-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="ab85e-109">módulo : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ab85e-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ab85e-110">O módulo pelo qual os resíduos são tomadas, deve ser positivo</span><span class="sxs-lookup"><span data-stu-id="ab85e-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="ab85e-111">Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ab85e-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ab85e-112">Inteiro $r$ entre 0 e `modulus - 1` tal que `value - r` é divisível por módulo</span><span class="sxs-lookup"><span data-stu-id="ab85e-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="ab85e-113">Observações</span><span class="sxs-lookup"><span data-stu-id="ab85e-113">Remarks</span></span>

<span data-ttu-id="ab85e-114">Esta função comporta-se de forma diferente da forma como o operador `%` se comporta em C# e Q# pois, no resultado, é sempre um número inteiro positivo entre 0 e , mesmo que o `modulus - 1` valor seja negativo.</span><span class="sxs-lookup"><span data-stu-id="ab85e-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>