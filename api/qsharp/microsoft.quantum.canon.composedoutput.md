---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: Função Compostaoutput
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 7e361a62679ab93e9a0ebc04fa52be193805c78d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207467"
---
# <a name="composedoutput-function"></a><span data-ttu-id="3bb8e-102">Função Compostaoutput</span><span class="sxs-lookup"><span data-stu-id="3bb8e-102">ComposedOutput function</span></span>

<span data-ttu-id="3bb8e-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3bb8e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3bb8e-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3bb8e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3bb8e-105">Devolve a saída da composição `inner` de e para uma dada `outer` entrada.</span><span class="sxs-lookup"><span data-stu-id="3bb8e-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="3bb8e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3bb8e-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="3bb8e-107">exterior : 'U -> 'V</span><span class="sxs-lookup"><span data-stu-id="3bb8e-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="3bb8e-108">interior : 'T-> 'U</span><span class="sxs-lookup"><span data-stu-id="3bb8e-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="3bb8e-109">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="3bb8e-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="3bb8e-110">Saída : 'V</span><span class="sxs-lookup"><span data-stu-id="3bb8e-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3bb8e-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="3bb8e-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3bb8e-112">'T</span><span class="sxs-lookup"><span data-stu-id="3bb8e-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="3bb8e-113">'U</span><span class="sxs-lookup"><span data-stu-id="3bb8e-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="3bb8e-114">'V</span><span class="sxs-lookup"><span data-stu-id="3bb8e-114">'V</span></span>

