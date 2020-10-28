---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Função de contradição
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712865"
---
# <a name="contradiction-function"></a><span data-ttu-id="4719f-102">Função de contradição</span><span class="sxs-lookup"><span data-stu-id="4719f-102">Contradiction function</span></span>

<span data-ttu-id="4719f-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4719f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4719f-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4719f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4719f-105">Declara que uma condição clássica é falsa.</span><span class="sxs-lookup"><span data-stu-id="4719f-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="4719f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4719f-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="4719f-107">real : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4719f-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4719f-108">A condição a ser declarada.</span><span class="sxs-lookup"><span data-stu-id="4719f-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="4719f-109">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="4719f-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="4719f-110">Cadeia de mensagens de falha a ser impressa no caso de a condição clássica ser verdadeira.</span><span class="sxs-lookup"><span data-stu-id="4719f-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4719f-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4719f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="4719f-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4719f-112">See Also</span></span>

- [<span data-ttu-id="4719f-113">Microsoft.Quantum.Diagnostics.Fact</span><span class="sxs-lookup"><span data-stu-id="4719f-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)