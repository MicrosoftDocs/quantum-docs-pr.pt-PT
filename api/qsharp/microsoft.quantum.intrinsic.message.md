---
uid: Microsoft.Quantum.Intrinsic.Message
title: Função de mensagem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 0428a46bc639bc8a0697f5bd392f85b8b9f40ee5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711423"
---
# <a name="message-function"></a><span data-ttu-id="65a90-102">Função de mensagem</span><span class="sxs-lookup"><span data-stu-id="65a90-102">Message function</span></span>

<span data-ttu-id="65a90-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="65a90-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="65a90-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="65a90-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="65a90-105">Regista uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="65a90-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="65a90-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="65a90-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="65a90-107">msg : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="65a90-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="65a90-108">A mensagem a ser reportada.</span><span class="sxs-lookup"><span data-stu-id="65a90-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="65a90-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="65a90-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="65a90-110">Observações</span><span class="sxs-lookup"><span data-stu-id="65a90-110">Remarks</span></span>

<span data-ttu-id="65a90-111">O comportamento específico desta função é dependente do simulador, mas na maioria dos casos a mensagem dada será escrita para a consola.</span><span class="sxs-lookup"><span data-stu-id="65a90-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>