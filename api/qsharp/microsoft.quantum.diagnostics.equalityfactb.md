---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: a87d6690e701eb1530be3134d24884a8c19357e9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201925"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="6f9e1-102">EqualityFactB</span><span class="sxs-lookup"><span data-stu-id="6f9e1-102">EqualityFactB function</span></span>

<span data-ttu-id="6f9e1-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6f9e1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6f9e1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f9e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f9e1-105">Afirma que uma variável bool clássica tem o valor esperado.</span><span class="sxs-lookup"><span data-stu-id="6f9e1-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="6f9e1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6f9e1-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="6f9e1-107">real : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6f9e1-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6f9e1-108">A variável a ser verificada.</span><span class="sxs-lookup"><span data-stu-id="6f9e1-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="6f9e1-109">esperado : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6f9e1-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6f9e1-110">O valor esperado.</span><span class="sxs-lookup"><span data-stu-id="6f9e1-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="6f9e1-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6f9e1-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="6f9e1-112">Cadeia de mensagem de falha a ser utilizada quando a afirmação é desencadeada.</span><span class="sxs-lookup"><span data-stu-id="6f9e1-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6f9e1-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6f9e1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

