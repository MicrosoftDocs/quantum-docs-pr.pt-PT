---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpC
title: AplicarOperação Funcionar
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpC
qsharp.summary: ''
ms.openlocfilehash: faca9b3f6d9a132b591a532c9e2ce54af1f0b182
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218942"
---
# <a name="applycurriedopc-operation"></a><span data-ttu-id="9c714-102">AplicarOperação Funcionar</span><span class="sxs-lookup"><span data-stu-id="9c714-102">ApplyCurriedOpC operation</span></span>

<span data-ttu-id="9c714-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9c714-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9c714-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9c714-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl)), first : 'T, second : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="9c714-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="9c714-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="9c714-106">curriedOp : 'T-> 'U = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL</span><span class="sxs-lookup"><span data-stu-id="9c714-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="9c714-107">primeiro : 'T</span><span class="sxs-lookup"><span data-stu-id="9c714-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="9c714-108">segundo : 'U</span><span class="sxs-lookup"><span data-stu-id="9c714-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="9c714-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c714-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9c714-110">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="9c714-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9c714-111">'T</span><span class="sxs-lookup"><span data-stu-id="9c714-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="9c714-112">'U</span><span class="sxs-lookup"><span data-stu-id="9c714-112">'U</span></span>

