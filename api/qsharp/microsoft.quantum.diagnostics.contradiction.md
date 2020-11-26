---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Função de contradição
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: f9ad9a7d67bda8e50c76f679f535ad55ba07698e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202146"
---
# <a name="contradiction-function"></a><span data-ttu-id="90553-102">Função de contradição</span><span class="sxs-lookup"><span data-stu-id="90553-102">Contradiction function</span></span>

<span data-ttu-id="90553-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="90553-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="90553-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="90553-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="90553-105">Declara que uma condição clássica é falsa.</span><span class="sxs-lookup"><span data-stu-id="90553-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="90553-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="90553-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="90553-107">real : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="90553-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="90553-108">A condição a ser declarada.</span><span class="sxs-lookup"><span data-stu-id="90553-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="90553-109">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="90553-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="90553-110">Cadeia de mensagens de falha a ser impressa no caso de a condição clássica ser verdadeira.</span><span class="sxs-lookup"><span data-stu-id="90553-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="90553-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="90553-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="90553-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="90553-112">See Also</span></span>

- [<span data-ttu-id="90553-113">Microsoft.Quantum.Diagnostics.Fact</span><span class="sxs-lookup"><span data-stu-id="90553-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)