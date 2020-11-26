---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: Função LessThanLexographic
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 3b3ac3f9f8b70307099de60899c969abb2acad7c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197675"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="c4909-102">Função LessThanLexographic</span><span class="sxs-lookup"><span data-stu-id="c4909-102">LessThanLexographic function</span></span>

<span data-ttu-id="c4909-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c4909-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c4909-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c4909-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c4909-105">Usado para `LexographicComparison` implementar.</span><span class="sxs-lookup"><span data-stu-id="c4909-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="c4909-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c4909-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="c4909-107">comparação: ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c4909-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="c4909-108">esquerda : 'T[]</span><span class="sxs-lookup"><span data-stu-id="c4909-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="c4909-109">direito : 'T[]</span><span class="sxs-lookup"><span data-stu-id="c4909-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="c4909-110">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c4909-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c4909-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="c4909-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4909-112">'T</span><span class="sxs-lookup"><span data-stu-id="c4909-112">'T</span></span>

