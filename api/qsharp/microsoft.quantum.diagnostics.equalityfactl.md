---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: b7d37b5115c51596c1b3ed93c53a29e9f36b811d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829150"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="767e5-102">EqualityFactL</span><span class="sxs-lookup"><span data-stu-id="767e5-102">EqualityFactL function</span></span>

<span data-ttu-id="767e5-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="767e5-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="767e5-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="767e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="767e5-105">Afirma que uma variável clássica bigint tem o valor esperado.</span><span class="sxs-lookup"><span data-stu-id="767e5-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="767e5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="767e5-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="767e5-107">real : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="767e5-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="767e5-108">O número a ser verificado.</span><span class="sxs-lookup"><span data-stu-id="767e5-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="767e5-109">esperado : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="767e5-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="767e5-110">O valor esperado.</span><span class="sxs-lookup"><span data-stu-id="767e5-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="767e5-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="767e5-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="767e5-112">Cadeia de mensagem de falha a ser utilizada quando a afirmação é desencadeada.</span><span class="sxs-lookup"><span data-stu-id="767e5-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="767e5-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="767e5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

