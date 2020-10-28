---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: Função LessThanLexographic
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 360088e31a47a7bb114bc0527edf600cd78740f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709964"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="34df3-102">Função LessThanLexographic</span><span class="sxs-lookup"><span data-stu-id="34df3-102">LessThanLexographic function</span></span>

<span data-ttu-id="34df3-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="34df3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="34df3-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="34df3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="34df3-105">Usado para `LexographicComparison` implementar.</span><span class="sxs-lookup"><span data-stu-id="34df3-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="34df3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="34df3-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="34df3-107">comparação: ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="34df3-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="34df3-108">esquerda : 'T[]</span><span class="sxs-lookup"><span data-stu-id="34df3-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="34df3-109">direito : 'T[]</span><span class="sxs-lookup"><span data-stu-id="34df3-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="34df3-110">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="34df3-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="34df3-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="34df3-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="34df3-112">'T</span><span class="sxs-lookup"><span data-stu-id="34df3-112">'T</span></span>

