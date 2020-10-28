---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712753"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="35fdc-102">EqualityFactL</span><span class="sxs-lookup"><span data-stu-id="35fdc-102">EqualityFactL function</span></span>

<span data-ttu-id="35fdc-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="35fdc-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="35fdc-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="35fdc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="35fdc-105">Afirma que uma variável clássica bigint tem o valor esperado.</span><span class="sxs-lookup"><span data-stu-id="35fdc-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="35fdc-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="35fdc-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="35fdc-107">real : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="35fdc-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="35fdc-108">O número a ser verificado.</span><span class="sxs-lookup"><span data-stu-id="35fdc-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="35fdc-109">esperado : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="35fdc-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="35fdc-110">O valor esperado.</span><span class="sxs-lookup"><span data-stu-id="35fdc-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="35fdc-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="35fdc-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="35fdc-112">Cadeia de mensagem de falha a ser utilizada quando a afirmação é desencadeada.</span><span class="sxs-lookup"><span data-stu-id="35fdc-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="35fdc-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="35fdc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

