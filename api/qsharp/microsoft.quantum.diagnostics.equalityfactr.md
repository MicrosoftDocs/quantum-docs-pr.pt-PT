---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: Função EqualityFactR
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 166dff211d6db9da5d39c607af1924ffd6d276dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201772"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="4215f-102">Função EqualityFactR</span><span class="sxs-lookup"><span data-stu-id="4215f-102">EqualityFactR function</span></span>

<span data-ttu-id="4215f-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4215f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4215f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4215f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4215f-105">Afirma que uma variável de Resultado clássico tem o valor esperado.</span><span class="sxs-lookup"><span data-stu-id="4215f-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="4215f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4215f-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="4215f-107">real : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="4215f-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="4215f-108">A variável a ser verificada.</span><span class="sxs-lookup"><span data-stu-id="4215f-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="4215f-109">esperado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="4215f-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="4215f-110">O valor esperado.</span><span class="sxs-lookup"><span data-stu-id="4215f-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="4215f-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="4215f-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="4215f-112">Cadeia de mensagem de falha a ser utilizada quando a afirmação é desencadeada.</span><span class="sxs-lookup"><span data-stu-id="4215f-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4215f-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4215f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

