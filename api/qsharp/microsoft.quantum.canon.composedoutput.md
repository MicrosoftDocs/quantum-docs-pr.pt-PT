---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: Função Compostaoutput
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716488"
---
# <a name="composedoutput-function"></a><span data-ttu-id="a5432-102">Função Compostaoutput</span><span class="sxs-lookup"><span data-stu-id="a5432-102">ComposedOutput function</span></span>

<span data-ttu-id="a5432-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a5432-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a5432-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5432-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5432-105">Devolve a saída da composição `inner` de e para uma dada `outer` entrada.</span><span class="sxs-lookup"><span data-stu-id="a5432-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="a5432-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a5432-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="a5432-107">exterior : 'U -> 'V</span><span class="sxs-lookup"><span data-stu-id="a5432-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="a5432-108">interior : 'T-> 'U</span><span class="sxs-lookup"><span data-stu-id="a5432-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="a5432-109">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="a5432-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="a5432-110">Saída : 'V</span><span class="sxs-lookup"><span data-stu-id="a5432-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a5432-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="a5432-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a5432-112">'T</span><span class="sxs-lookup"><span data-stu-id="a5432-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="a5432-113">'U</span><span class="sxs-lookup"><span data-stu-id="a5432-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="a5432-114">'V</span><span class="sxs-lookup"><span data-stu-id="a5432-114">'V</span></span>

