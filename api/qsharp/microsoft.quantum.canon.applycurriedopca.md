---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpCA
title: AplicarCorda OperaçãoOpCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpCA
qsharp.summary: ''
ms.openlocfilehash: 4e57772bc5440a473c28279ac125170caaa120f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718318"
---
# <a name="applycurriedopca-operation"></a><span data-ttu-id="138a1-102">AplicarCorda OperaçãoOpCA</span><span class="sxs-lookup"><span data-stu-id="138a1-102">ApplyCurriedOpCA operation</span></span>

<span data-ttu-id="138a1-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="138a1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="138a1-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="138a1-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="138a1-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="138a1-105">Input</span></span>

### <a name="curriedop--t---u--unit-ctl--adj"></a><span data-ttu-id="138a1-106">curriedOp : 'T-> 'U = [unidade](xref:microsoft.quantum.lang-ref.unit)> Ctl + Adj</span><span class="sxs-lookup"><span data-stu-id="138a1-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="138a1-107">primeiro : 'T</span><span class="sxs-lookup"><span data-stu-id="138a1-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="138a1-108">segundo : 'U</span><span class="sxs-lookup"><span data-stu-id="138a1-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="138a1-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="138a1-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="138a1-110">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="138a1-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="138a1-111">'T</span><span class="sxs-lookup"><span data-stu-id="138a1-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="138a1-112">'U</span><span class="sxs-lookup"><span data-stu-id="138a1-112">'U</span></span>

