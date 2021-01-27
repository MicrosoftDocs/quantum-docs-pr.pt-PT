---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Função de contradição
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829370"
---
# <a name="contradiction-function"></a><span data-ttu-id="16422-102">Função de contradição</span><span class="sxs-lookup"><span data-stu-id="16422-102">Contradiction function</span></span>

<span data-ttu-id="16422-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="16422-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="16422-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="16422-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="16422-105">Declara que uma condição clássica é falsa.</span><span class="sxs-lookup"><span data-stu-id="16422-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="16422-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="16422-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="16422-107">real : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="16422-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="16422-108">A condição a ser declarada.</span><span class="sxs-lookup"><span data-stu-id="16422-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="16422-109">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="16422-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="16422-110">Cadeia de mensagens de falha a ser impressa no caso de a condição clássica ser verdadeira.</span><span class="sxs-lookup"><span data-stu-id="16422-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="16422-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16422-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="16422-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="16422-112">Example</span></span>

<span data-ttu-id="16422-113">O seguinte código Q# imprimirá "Olá, mundo":</span><span class="sxs-lookup"><span data-stu-id="16422-113">The following Q# code will print "Hello, world":</span></span>

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a><span data-ttu-id="16422-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="16422-114">See Also</span></span>

- [<span data-ttu-id="16422-115">Microsoft.Quantum.Diagnostics.Fact</span><span class="sxs-lookup"><span data-stu-id="16422-115">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)