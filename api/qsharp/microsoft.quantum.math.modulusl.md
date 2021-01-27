---
uid: Microsoft.Quantum.Math.ModulusL
title: Função de módulol
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6be2edb052cf55f8e8465c76b5dcadeb61ff11ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842736"
---
# <a name="modulusl-function"></a><span data-ttu-id="3dbde-102">Função de módulol</span><span class="sxs-lookup"><span data-stu-id="3dbde-102">ModulusL function</span></span>

<span data-ttu-id="3dbde-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="3dbde-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="3dbde-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3dbde-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3dbde-105">Calcula o resíduo canónico do `value` `modulus` modulo.</span><span class="sxs-lookup"><span data-stu-id="3dbde-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="3dbde-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3dbde-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="3dbde-107">valor : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3dbde-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3dbde-108">O valor do qual o resíduo é calculado</span><span class="sxs-lookup"><span data-stu-id="3dbde-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="3dbde-109">módulo : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3dbde-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3dbde-110">O módulo pelo qual os resíduos são tomadas, deve ser positivo</span><span class="sxs-lookup"><span data-stu-id="3dbde-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="3dbde-111">Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3dbde-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3dbde-112">Inteiro $r$ entre 0 e `modulus - 1` tal que `value - r` é divisível por módulo</span><span class="sxs-lookup"><span data-stu-id="3dbde-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="3dbde-113">Observações</span><span class="sxs-lookup"><span data-stu-id="3dbde-113">Remarks</span></span>

<span data-ttu-id="3dbde-114">Esta função comporta-se de forma diferente da forma como o operador `%` se comporta em C# e Q# pois, no resultado, é sempre um número inteiro não negativo entre 0 e , mesmo que o `modulus - 1` valor seja negativo.</span><span class="sxs-lookup"><span data-stu-id="3dbde-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a non-negative integer between 0 and `modulus - 1`, even if value is negative.</span></span>