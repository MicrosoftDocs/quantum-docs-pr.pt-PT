---
uid: Microsoft.Quantum.Math.ExpModI
title: Função ExpModI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857040"
---
# <a name="expmodi-function"></a><span data-ttu-id="bae61-102">Função ExpModI</span><span class="sxs-lookup"><span data-stu-id="bae61-102">ExpModI function</span></span>

<span data-ttu-id="bae61-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="bae61-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="bae61-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bae61-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bae61-105">Devolve um inteiro elevado a um dado poder, no que diz respeito a um dado módulo.</span><span class="sxs-lookup"><span data-stu-id="bae61-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="bae61-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="bae61-106">Description</span></span>

<span data-ttu-id="bae61-107">Vamos denotar expBase em $x$, poder de $p$ e modulus por $N$.</span><span class="sxs-lookup"><span data-stu-id="bae61-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="bae61-108">A função devolve $x^p \operatorname{mod} N$.</span><span class="sxs-lookup"><span data-stu-id="bae61-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="bae61-109">Assumimos que $N dólares, $x dólares são positivos e o poder não é negativo.</span><span class="sxs-lookup"><span data-stu-id="bae61-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="bae61-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="bae61-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="bae61-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bae61-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="bae61-112">poder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bae61-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="bae61-113">módulo : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bae61-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="bae61-114">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bae61-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="bae61-115">Observações</span><span class="sxs-lookup"><span data-stu-id="bae61-115">Remarks</span></span>

<span data-ttu-id="bae61-116">Leva tempo proporcional ao número de bits `power` dentro , não o `power` próprio.</span><span class="sxs-lookup"><span data-stu-id="bae61-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>