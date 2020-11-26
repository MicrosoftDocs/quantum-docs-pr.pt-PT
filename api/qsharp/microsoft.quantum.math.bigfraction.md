---
uid: Microsoft.Quantum.Math.BigFraction
title: Tipo definido pelo utilizador bigFraction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211088"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="7b4fb-102">Tipo definido pelo utilizador bigFraction</span><span class="sxs-lookup"><span data-stu-id="7b4fb-102">BigFraction user defined type</span></span>

<span data-ttu-id="7b4fb-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="7b4fb-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="7b4fb-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7b4fb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7b4fb-105">Representa um número racional do `p/q` formulário.</span><span class="sxs-lookup"><span data-stu-id="7b4fb-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="7b4fb-106">O inteiro `p` é o primeiro elemento da tuple e é o segundo elemento da `q` tuple.</span><span class="sxs-lookup"><span data-stu-id="7b4fb-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="7b4fb-107">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="7b4fb-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="7b4fb-108">Numerador : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7b4fb-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7b4fb-109">Numerador da fração.</span><span class="sxs-lookup"><span data-stu-id="7b4fb-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="7b4fb-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7b4fb-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7b4fb-111">Denominador da fração/</span><span class="sxs-lookup"><span data-stu-id="7b4fb-111">Denominator of the fraction/</span></span>