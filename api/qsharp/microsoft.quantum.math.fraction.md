---
uid: Microsoft.Quantum.Math.Fraction
title: Tipo definido pelo utilizador de fração
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723660"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="2a624-102">Tipo definido pelo utilizador de fração</span><span class="sxs-lookup"><span data-stu-id="2a624-102">Fraction user defined type</span></span>

<span data-ttu-id="2a624-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2a624-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2a624-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a624-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a624-105">Representa um número racional do `p/q` formulário.</span><span class="sxs-lookup"><span data-stu-id="2a624-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="2a624-106">O inteiro `p` é o primeiro elemento da tuple e é o segundo elemento da `q` tuple.</span><span class="sxs-lookup"><span data-stu-id="2a624-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="2a624-107">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="2a624-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="2a624-108">Numerador : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a624-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a624-109">Numerador da fração.</span><span class="sxs-lookup"><span data-stu-id="2a624-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="2a624-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a624-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a624-111">Denominador da fração/</span><span class="sxs-lookup"><span data-stu-id="2a624-111">Denominator of the fraction/</span></span>