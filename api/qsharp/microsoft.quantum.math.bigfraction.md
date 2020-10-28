---
uid: Microsoft.Quantum.Math.BigFraction
title: Tipo definido pelo utilizador bigFraction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723212"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="32f5b-102">Tipo definido pelo utilizador bigFraction</span><span class="sxs-lookup"><span data-stu-id="32f5b-102">BigFraction user defined type</span></span>

<span data-ttu-id="32f5b-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="32f5b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="32f5b-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="32f5b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="32f5b-105">Representa um número racional do `p/q` formulário.</span><span class="sxs-lookup"><span data-stu-id="32f5b-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="32f5b-106">O inteiro `p` é o primeiro elemento da tuple e é o segundo elemento da `q` tuple.</span><span class="sxs-lookup"><span data-stu-id="32f5b-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="32f5b-107">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="32f5b-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="32f5b-108">Numerador : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="32f5b-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="32f5b-109">Numerador da fração.</span><span class="sxs-lookup"><span data-stu-id="32f5b-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="32f5b-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="32f5b-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="32f5b-111">Denominador da fração/</span><span class="sxs-lookup"><span data-stu-id="32f5b-111">Denominator of the fraction/</span></span>