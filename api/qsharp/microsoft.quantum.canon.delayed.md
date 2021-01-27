---
uid: Microsoft.Quantum.Canon.Delayed
title: Função atrasada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 40fcc7d0a178fdb18437b4d6c96542db593347b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840577"
---
# <a name="delayed-function"></a><span data-ttu-id="6912e-102">Função atrasada</span><span class="sxs-lookup"><span data-stu-id="6912e-102">Delayed function</span></span>

<span data-ttu-id="6912e-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6912e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6912e-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6912e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6912e-105">Devolve uma operação que se aplica a uma determinada operação com um argumento dado.</span><span class="sxs-lookup"><span data-stu-id="6912e-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="6912e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6912e-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="6912e-107">op : 'T => 'U</span><span class="sxs-lookup"><span data-stu-id="6912e-107">op : 'T => 'U</span></span> 

<span data-ttu-id="6912e-108">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="6912e-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="6912e-109">arg : 'T</span><span class="sxs-lookup"><span data-stu-id="6912e-109">arg : 'T</span></span>

<span data-ttu-id="6912e-110">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="6912e-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="6912e-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit) => 'U</span><span class="sxs-lookup"><span data-stu-id="6912e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="6912e-112">Uma nova operação que se aplica `op` com a entrada `arg`</span><span class="sxs-lookup"><span data-stu-id="6912e-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6912e-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="6912e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6912e-114">'T</span><span class="sxs-lookup"><span data-stu-id="6912e-114">'T</span></span>

<span data-ttu-id="6912e-115">O tipo de entrada da operação a ser adiado.</span><span class="sxs-lookup"><span data-stu-id="6912e-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="6912e-116">'U</span><span class="sxs-lookup"><span data-stu-id="6912e-116">'U</span></span>

<span data-ttu-id="6912e-117">O tipo de retorno da operação a ser adiado.</span><span class="sxs-lookup"><span data-stu-id="6912e-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="6912e-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6912e-118">See Also</span></span>

- [<span data-ttu-id="6912e-119">Microsoft.Quantum.Canon.DelayedC</span><span class="sxs-lookup"><span data-stu-id="6912e-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="6912e-120">Microsoft.Quantum.Canon.Delayeda</span><span class="sxs-lookup"><span data-stu-id="6912e-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="6912e-121">Microsoft.Quantum.Canon.DelayedCA</span><span class="sxs-lookup"><span data-stu-id="6912e-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="6912e-122">Microsoft.Quantum.Canon.Delay</span><span class="sxs-lookup"><span data-stu-id="6912e-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)