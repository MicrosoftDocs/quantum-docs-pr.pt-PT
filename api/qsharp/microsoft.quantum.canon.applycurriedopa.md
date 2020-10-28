---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: AplicarCorriedOpA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: 2b0f86efe79654e1f886f0ccd0287e07225cbf83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718331"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="2e6cc-102">AplicarCorriedOpA</span><span class="sxs-lookup"><span data-stu-id="2e6cc-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="2e6cc-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2e6cc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2e6cc-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2e6cc-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="2e6cc-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="2e6cc-105">Input</span></span>

### <a name="curriedop--t---u--unit-adj"></a><span data-ttu-id="2e6cc-106">curriedOp : 'T-> 'U = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj</span><span class="sxs-lookup"><span data-stu-id="2e6cc-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="2e6cc-107">primeiro : 'T</span><span class="sxs-lookup"><span data-stu-id="2e6cc-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="2e6cc-108">segundo : 'U</span><span class="sxs-lookup"><span data-stu-id="2e6cc-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="2e6cc-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e6cc-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2e6cc-110">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="2e6cc-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2e6cc-111">'T</span><span class="sxs-lookup"><span data-stu-id="2e6cc-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="2e6cc-112">'U</span><span class="sxs-lookup"><span data-stu-id="2e6cc-112">'U</span></span>

