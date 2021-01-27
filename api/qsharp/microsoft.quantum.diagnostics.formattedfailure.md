---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: Função formatadaFilure
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828267"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="29211-102">Função formatadaFilure</span><span class="sxs-lookup"><span data-stu-id="29211-102">FormattedFailure function</span></span>

<span data-ttu-id="29211-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="29211-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="29211-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="29211-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="29211-105">Função interna usada para falhar com mensagens de erro significativas.</span><span class="sxs-lookup"><span data-stu-id="29211-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="29211-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="29211-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="29211-107">real : 'T</span><span class="sxs-lookup"><span data-stu-id="29211-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="29211-108">esperado : 'T</span><span class="sxs-lookup"><span data-stu-id="29211-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="29211-109">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="29211-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="29211-110">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="29211-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="29211-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="29211-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="29211-112">'T</span><span class="sxs-lookup"><span data-stu-id="29211-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="29211-113">Observações</span><span class="sxs-lookup"><span data-stu-id="29211-113">Remarks</span></span>

<span data-ttu-id="29211-114">Esta função destina-se a ser emulsionada por tempos de simulação, de modo a permitir o encaminhamento de contradições formatadas.</span><span class="sxs-lookup"><span data-stu-id="29211-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>