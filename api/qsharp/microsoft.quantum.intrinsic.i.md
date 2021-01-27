---
uid: Microsoft.Quantum.Intrinsic.I
title: Eu operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 0af14a9aff20da493e95c7feba6afbb907d3d69f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849398"
---
# <a name="i-operation"></a><span data-ttu-id="888ea-102">Eu operação</span><span class="sxs-lookup"><span data-stu-id="888ea-102">I operation</span></span>

<span data-ttu-id="888ea-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="888ea-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="888ea-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="888ea-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="888ea-105">Executa a operação de identidade (no-op) num único qubit.</span><span class="sxs-lookup"><span data-stu-id="888ea-105">Performs the identity operation (no-op) on a single qubit.</span></span>

```qsharp
operation I (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="888ea-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="888ea-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="888ea-107">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="888ea-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="888ea-108">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="888ea-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="888ea-109">Observações</span><span class="sxs-lookup"><span data-stu-id="888ea-109">Remarks</span></span>

<span data-ttu-id="888ea-110">Isto é um não-op.</span><span class="sxs-lookup"><span data-stu-id="888ea-110">This is a no-op.</span></span> <span data-ttu-id="888ea-111">Está previsto para a completude e porque às vezes é útil chamar a identidade num algoritmo ou passá-la como parâmetro.</span><span class="sxs-lookup"><span data-stu-id="888ea-111">It is provided for completeness and because sometimes it is useful to call the identity in an algorithm or to pass it as a parameter.</span></span>