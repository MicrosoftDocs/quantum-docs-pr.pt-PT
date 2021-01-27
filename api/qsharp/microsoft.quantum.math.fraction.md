---
uid: Microsoft.Quantum.Math.Fraction
title: Tipo definido pelo utilizador de fração
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857505"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="e72e7-102">Tipo definido pelo utilizador de fração</span><span class="sxs-lookup"><span data-stu-id="e72e7-102">Fraction user defined type</span></span>

<span data-ttu-id="e72e7-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e72e7-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e72e7-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e72e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e72e7-105">Representa um número racional do `p/q` formulário.</span><span class="sxs-lookup"><span data-stu-id="e72e7-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="e72e7-106">O inteiro `p` é o primeiro elemento da tuple e é o segundo elemento da `q` tuple.</span><span class="sxs-lookup"><span data-stu-id="e72e7-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="e72e7-107">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="e72e7-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="e72e7-108">Numerador : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e72e7-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e72e7-109">Numerador da fração.</span><span class="sxs-lookup"><span data-stu-id="e72e7-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="e72e7-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e72e7-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e72e7-111">Denominador da fração/</span><span class="sxs-lookup"><span data-stu-id="e72e7-111">Denominator of the fraction/</span></span>