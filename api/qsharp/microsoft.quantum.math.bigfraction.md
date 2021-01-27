---
uid: Microsoft.Quantum.Math.BigFraction
title: Tipo definido pelo utilizador bigFraction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: bfbf49e7a3d060417e506a1977c20adc08b81f0e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846907"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="79896-102">Tipo definido pelo utilizador bigFraction</span><span class="sxs-lookup"><span data-stu-id="79896-102">BigFraction user defined type</span></span>

<span data-ttu-id="79896-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="79896-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="79896-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="79896-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="79896-105">Representa um número racional do `p/q` formulário.</span><span class="sxs-lookup"><span data-stu-id="79896-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="79896-106">O inteiro `p` é o primeiro elemento da tuple e é o segundo elemento da `q` tuple.</span><span class="sxs-lookup"><span data-stu-id="79896-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="79896-107">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="79896-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="79896-108">Numerador : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="79896-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="79896-109">Numerador da fração.</span><span class="sxs-lookup"><span data-stu-id="79896-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="79896-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="79896-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="79896-111">Denominador da fração/</span><span class="sxs-lookup"><span data-stu-id="79896-111">Denominator of the fraction/</span></span>