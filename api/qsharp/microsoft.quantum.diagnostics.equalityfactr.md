---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: Função EqualityFactR
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712739"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="2d227-102">Função EqualityFactR</span><span class="sxs-lookup"><span data-stu-id="2d227-102">EqualityFactR function</span></span>

<span data-ttu-id="2d227-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2d227-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2d227-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2d227-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2d227-105">Afirma que uma variável de Resultado clássico tem o valor esperado.</span><span class="sxs-lookup"><span data-stu-id="2d227-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2d227-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2d227-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="2d227-107">real : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="2d227-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="2d227-108">A variável a ser verificada.</span><span class="sxs-lookup"><span data-stu-id="2d227-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="2d227-109">esperado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="2d227-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="2d227-110">O valor esperado.</span><span class="sxs-lookup"><span data-stu-id="2d227-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="2d227-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2d227-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2d227-112">Cadeia de mensagem de falha a ser utilizada quando a afirmação é desencadeada.</span><span class="sxs-lookup"><span data-stu-id="2d227-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2d227-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2d227-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

