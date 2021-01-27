---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: Função EqualityFactR
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 86d2ddff79f0bca7badd95a2fe2156c558fa7f86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853335"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="112a3-102">Função EqualityFactR</span><span class="sxs-lookup"><span data-stu-id="112a3-102">EqualityFactR function</span></span>

<span data-ttu-id="112a3-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="112a3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="112a3-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="112a3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="112a3-105">Afirma que uma variável de Resultado clássico tem o valor esperado.</span><span class="sxs-lookup"><span data-stu-id="112a3-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="112a3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="112a3-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="112a3-107">real : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="112a3-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="112a3-108">A variável a ser verificada.</span><span class="sxs-lookup"><span data-stu-id="112a3-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="112a3-109">esperado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="112a3-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="112a3-110">O valor esperado.</span><span class="sxs-lookup"><span data-stu-id="112a3-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="112a3-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="112a3-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="112a3-112">Cadeia de mensagem de falha a ser utilizada quando a afirmação é desencadeada.</span><span class="sxs-lookup"><span data-stu-id="112a3-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="112a3-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="112a3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

