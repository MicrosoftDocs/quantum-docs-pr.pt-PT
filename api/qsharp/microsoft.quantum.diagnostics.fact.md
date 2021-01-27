---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Função de facto
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853311"
---
# <a name="fact-function"></a><span data-ttu-id="1d7a8-102">Função de facto</span><span class="sxs-lookup"><span data-stu-id="1d7a8-102">Fact function</span></span>

<span data-ttu-id="1d7a8-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1d7a8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1d7a8-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1d7a8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1d7a8-105">Declara que uma condição clássica é verdadeira.</span><span class="sxs-lookup"><span data-stu-id="1d7a8-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="1d7a8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1d7a8-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="1d7a8-107">real : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1d7a8-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1d7a8-108">A condição a ser declarada.</span><span class="sxs-lookup"><span data-stu-id="1d7a8-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="1d7a8-109">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1d7a8-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1d7a8-110">Cadeia de mensagens de falha a ser impressa no caso de a condição clássica ser falsa.</span><span class="sxs-lookup"><span data-stu-id="1d7a8-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1d7a8-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1d7a8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="1d7a8-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1d7a8-112">Example</span></span>

<span data-ttu-id="1d7a8-113">O seguinte corte Q# falhará:</span><span class="sxs-lookup"><span data-stu-id="1d7a8-113">The following Q# snippet will fail:</span></span>

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a><span data-ttu-id="1d7a8-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1d7a8-114">See Also</span></span>

- [<span data-ttu-id="1d7a8-115">Microsoft.Quantum.Diagnostics.Contradição</span><span class="sxs-lookup"><span data-stu-id="1d7a8-115">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)