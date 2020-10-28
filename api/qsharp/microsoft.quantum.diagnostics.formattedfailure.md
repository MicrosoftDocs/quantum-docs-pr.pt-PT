---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: Função formatadaFilure
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712680"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="47d9a-102">Função formatadaFilure</span><span class="sxs-lookup"><span data-stu-id="47d9a-102">FormattedFailure function</span></span>

<span data-ttu-id="47d9a-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="47d9a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="47d9a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47d9a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47d9a-105">Função interna usada para falhar com mensagens de erro significativas.</span><span class="sxs-lookup"><span data-stu-id="47d9a-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="47d9a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="47d9a-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="47d9a-107">real : 'T</span><span class="sxs-lookup"><span data-stu-id="47d9a-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="47d9a-108">esperado : 'T</span><span class="sxs-lookup"><span data-stu-id="47d9a-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="47d9a-109">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="47d9a-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="47d9a-110">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47d9a-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="47d9a-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="47d9a-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="47d9a-112">'T</span><span class="sxs-lookup"><span data-stu-id="47d9a-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="47d9a-113">Observações</span><span class="sxs-lookup"><span data-stu-id="47d9a-113">Remarks</span></span>

<span data-ttu-id="47d9a-114">Esta função destina-se a ser emulsionada por tempos de simulação, de modo a permitir o encaminhamento de contradições formatadas.</span><span class="sxs-lookup"><span data-stu-id="47d9a-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>