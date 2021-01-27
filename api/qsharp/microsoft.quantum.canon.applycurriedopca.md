---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpCA
title: AplicarCorda OperaçãoOpCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpCA
qsharp.summary: ''
ms.openlocfilehash: acff5669c8d5d392a0032eaa49d279bff20a91f4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845075"
---
# <a name="applycurriedopca-operation"></a><span data-ttu-id="39d1e-102">AplicarCorda OperaçãoOpCA</span><span class="sxs-lookup"><span data-stu-id="39d1e-102">ApplyCurriedOpCA operation</span></span>

<span data-ttu-id="39d1e-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39d1e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39d1e-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39d1e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj)), first : 'T, second : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="39d1e-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="39d1e-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj--ctl"></a><span data-ttu-id="39d1e-106">curriedOp : 'T-> 'U = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="39d1e-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="39d1e-107">primeiro : 'T</span><span class="sxs-lookup"><span data-stu-id="39d1e-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="39d1e-108">segundo : 'U</span><span class="sxs-lookup"><span data-stu-id="39d1e-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="39d1e-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39d1e-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="39d1e-110">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="39d1e-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39d1e-111">'T</span><span class="sxs-lookup"><span data-stu-id="39d1e-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="39d1e-112">'U</span><span class="sxs-lookup"><span data-stu-id="39d1e-112">'U</span></span>

