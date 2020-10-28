---
uid: Microsoft.Quantum.Math.ExpModI
title: Função ExpModI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723366"
---
# <a name="expmodi-function"></a><span data-ttu-id="4f4a9-102">Função ExpModI</span><span class="sxs-lookup"><span data-stu-id="4f4a9-102">ExpModI function</span></span>

<span data-ttu-id="4f4a9-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4f4a9-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4f4a9-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4f4a9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4f4a9-105">Devolve um inteiro elevado a um dado poder, no que diz respeito a um dado módulo.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="4f4a9-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="4f4a9-106">Description</span></span>

<span data-ttu-id="4f4a9-107">Vamos denotar expBase em $x$, poder de $p$ e modulus por $N$.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="4f4a9-108">A função devolve $x^p \operatorname{mod} N$.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="4f4a9-109">Assumimos que $N dólares, $x dólares são positivos e o poder não é negativo.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="4f4a9-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="4f4a9-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="4f4a9-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4f4a9-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="4f4a9-112">poder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4f4a9-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="4f4a9-113">módulo : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4f4a9-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="4f4a9-114">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4f4a9-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="4f4a9-115">Observações</span><span class="sxs-lookup"><span data-stu-id="4f4a9-115">Remarks</span></span>

<span data-ttu-id="4f4a9-116">Leva tempo proporcional ao número de bits `power` dentro , não o `power` próprio.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>