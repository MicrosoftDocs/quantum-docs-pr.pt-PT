---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 0fcfe553d7a0050a9ab35a43ac5fe2b1958514db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853366"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="5f5d0-102">EqualityFactC</span><span class="sxs-lookup"><span data-stu-id="5f5d0-102">EqualityFactC function</span></span>

<span data-ttu-id="5f5d0-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5f5d0-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5f5d0-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5f5d0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5f5d0-105">Afirma que um número complexo tem o valor esperado.</span><span class="sxs-lookup"><span data-stu-id="5f5d0-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="5f5d0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5f5d0-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="5f5d0-107">real : [Complexo](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="5f5d0-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="5f5d0-108">O valor a ser verificado.</span><span class="sxs-lookup"><span data-stu-id="5f5d0-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="5f5d0-109">esperado : [Complexo](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="5f5d0-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="5f5d0-110">O valor esperado.</span><span class="sxs-lookup"><span data-stu-id="5f5d0-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="5f5d0-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="5f5d0-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="5f5d0-112">Cadeia de mensagem de falha a ser utilizada quando a afirmação é desencadeada.</span><span class="sxs-lookup"><span data-stu-id="5f5d0-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5f5d0-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5f5d0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

