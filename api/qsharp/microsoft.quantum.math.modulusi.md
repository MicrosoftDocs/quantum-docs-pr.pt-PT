---
uid: Microsoft.Quantum.Math.ModulusI
title: Função modulusi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 3f698a00b2c8d94b7cb3cca4f1721c659918f4a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723089"
---
# <a name="modulusi-function"></a><span data-ttu-id="21a29-102">Função modulusi</span><span class="sxs-lookup"><span data-stu-id="21a29-102">ModulusI function</span></span>

<span data-ttu-id="21a29-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="21a29-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="21a29-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="21a29-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="21a29-105">Calcula o resíduo canónico do `value` `modulus` modulo.</span><span class="sxs-lookup"><span data-stu-id="21a29-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="21a29-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="21a29-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="21a29-107">valor : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="21a29-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="21a29-108">O valor do qual o resíduo é calculado</span><span class="sxs-lookup"><span data-stu-id="21a29-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="21a29-109">módulo : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="21a29-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="21a29-110">O módulo pelo qual os resíduos são tomadas, deve ser positivo</span><span class="sxs-lookup"><span data-stu-id="21a29-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="21a29-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="21a29-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="21a29-112">Inteiro $r$ entre 0 e `modulus - 1` tal que `value - r` é divisível por módulo</span><span class="sxs-lookup"><span data-stu-id="21a29-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="21a29-113">Observações</span><span class="sxs-lookup"><span data-stu-id="21a29-113">Remarks</span></span>

<span data-ttu-id="21a29-114">Esta função comporta-se de forma diferente da forma como o operador `%` se comporta em C# e Q# pois, no resultado, é sempre um número inteiro positivo entre 0 e , mesmo que o `modulus - 1` valor seja negativo.</span><span class="sxs-lookup"><span data-stu-id="21a29-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>