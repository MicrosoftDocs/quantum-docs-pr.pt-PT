---
uid: Microsoft.Quantum.Math.ExpModL
title: Função ExpModL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 07da113caeb9f6f3f3f3f92f13478f33021bfa14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210755"
---
# <a name="expmodl-function"></a><span data-ttu-id="22392-102">Função ExpModL</span><span class="sxs-lookup"><span data-stu-id="22392-102">ExpModL function</span></span>

<span data-ttu-id="22392-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="22392-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="22392-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="22392-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="22392-105">Devolve um inteiro elevado a um dado poder, no que diz respeito a um dado módulo.</span><span class="sxs-lookup"><span data-stu-id="22392-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="22392-106">Description</span><span class="sxs-lookup"><span data-stu-id="22392-106">Description</span></span>

<span data-ttu-id="22392-107">Vamos denotar expBase em $x$, poder de $p$ e modulus por $N$.</span><span class="sxs-lookup"><span data-stu-id="22392-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="22392-108">A função devolve $x^p \operatorname{mod} N$.</span><span class="sxs-lookup"><span data-stu-id="22392-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="22392-109">Assumimos que $N dólares, $x dólares são positivos e o poder não é negativo.</span><span class="sxs-lookup"><span data-stu-id="22392-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="22392-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="22392-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="22392-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="22392-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="22392-112">poder : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="22392-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="22392-113">módulo : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="22392-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="22392-114">Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="22392-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="22392-115">Observações</span><span class="sxs-lookup"><span data-stu-id="22392-115">Remarks</span></span>

<span data-ttu-id="22392-116">Leva tempo proporcional ao número de bits `power` dentro , não o `power` próprio.</span><span class="sxs-lookup"><span data-stu-id="22392-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>