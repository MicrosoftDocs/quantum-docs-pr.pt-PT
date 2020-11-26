---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: Função formatadaFilure
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: da809c04059d4fd0f0ec92412a3094f5b582fd91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201704"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="7fd33-102">Função formatadaFilure</span><span class="sxs-lookup"><span data-stu-id="7fd33-102">FormattedFailure function</span></span>

<span data-ttu-id="7fd33-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7fd33-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7fd33-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7fd33-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7fd33-105">Função interna usada para falhar com mensagens de erro significativas.</span><span class="sxs-lookup"><span data-stu-id="7fd33-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="7fd33-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7fd33-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="7fd33-107">real : 'T</span><span class="sxs-lookup"><span data-stu-id="7fd33-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="7fd33-108">esperado : 'T</span><span class="sxs-lookup"><span data-stu-id="7fd33-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="7fd33-109">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="7fd33-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="7fd33-110">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7fd33-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7fd33-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="7fd33-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7fd33-112">'T</span><span class="sxs-lookup"><span data-stu-id="7fd33-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="7fd33-113">Observações</span><span class="sxs-lookup"><span data-stu-id="7fd33-113">Remarks</span></span>

<span data-ttu-id="7fd33-114">Esta função destina-se a ser emulsionada por tempos de simulação, de modo a permitir o encaminhamento de contradições formatadas.</span><span class="sxs-lookup"><span data-stu-id="7fd33-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>