---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: d3163281772bda392fbdd61ad58543e22022a600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712778"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="1c4ff-102">EqualityFactB</span><span class="sxs-lookup"><span data-stu-id="1c4ff-102">EqualityFactB function</span></span>

<span data-ttu-id="1c4ff-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1c4ff-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1c4ff-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1c4ff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1c4ff-105">Afirma que uma variável bool clássica tem o valor esperado.</span><span class="sxs-lookup"><span data-stu-id="1c4ff-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="1c4ff-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1c4ff-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="1c4ff-107">real : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1c4ff-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1c4ff-108">A variável a ser verificada.</span><span class="sxs-lookup"><span data-stu-id="1c4ff-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="1c4ff-109">esperado : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1c4ff-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1c4ff-110">O valor esperado.</span><span class="sxs-lookup"><span data-stu-id="1c4ff-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="1c4ff-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1c4ff-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1c4ff-112">Cadeia de mensagem de falha a ser utilizada quando a afirmação é desencadeada.</span><span class="sxs-lookup"><span data-stu-id="1c4ff-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1c4ff-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c4ff-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

