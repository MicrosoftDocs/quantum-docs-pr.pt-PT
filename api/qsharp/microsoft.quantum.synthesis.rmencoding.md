---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: Função RMEncoding
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: f3c54d2e40511dacb21618b4eaf1eef9f4903f9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855334"
---
# <a name="rmencoding-function"></a><span data-ttu-id="9b0a9-102">Função RMEncoding</span><span class="sxs-lookup"><span data-stu-id="9b0a9-102">RMEncoding function</span></span>

<span data-ttu-id="9b0a9-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="9b0a9-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="9b0a9-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b0a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b0a9-105">{-1,1} codificação de um valor da verdade Boolean</span><span class="sxs-lookup"><span data-stu-id="9b0a9-105">{-1,1} coding of a Boolean truth value</span></span>

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a><span data-ttu-id="9b0a9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9b0a9-106">Input</span></span>

### <a name="b--bool"></a><span data-ttu-id="9b0a9-107">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9b0a9-107">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9b0a9-108">Valor booleano</span><span class="sxs-lookup"><span data-stu-id="9b0a9-108">Boolean value</span></span>



## <a name="output--int"></a><span data-ttu-id="9b0a9-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9b0a9-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9b0a9-110">1, se `b` for falso, caso contrário -1</span><span class="sxs-lookup"><span data-stu-id="9b0a9-110">1, if `b` is false, otherwise -1</span></span>