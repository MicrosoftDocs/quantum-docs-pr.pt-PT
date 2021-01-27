---
uid: Microsoft.Quantum.Canon.Fst
title: Função Fst
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840522"
---
# <a name="fst-function"></a><span data-ttu-id="95c91-102">Função Fst</span><span class="sxs-lookup"><span data-stu-id="95c91-102">Fst function</span></span>

<span data-ttu-id="95c91-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="95c91-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="95c91-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="95c91-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="95c91-105">Dado um par, devolve o seu primeiro elemento.</span><span class="sxs-lookup"><span data-stu-id="95c91-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="95c91-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="95c91-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="95c91-107">par : ('T,'U)</span><span class="sxs-lookup"><span data-stu-id="95c91-107">pair : ('T,'U)</span></span>

<span data-ttu-id="95c91-108">Uma tuple com dois elementos.</span><span class="sxs-lookup"><span data-stu-id="95c91-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="95c91-109">Saída : 'T</span><span class="sxs-lookup"><span data-stu-id="95c91-109">Output : 'T</span></span>

<span data-ttu-id="95c91-110">O primeiro elemento `pair` de.</span><span class="sxs-lookup"><span data-stu-id="95c91-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="95c91-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="95c91-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="95c91-112">'T</span><span class="sxs-lookup"><span data-stu-id="95c91-112">'T</span></span>

<span data-ttu-id="95c91-113">O tipo do primeiro membro do par.</span><span class="sxs-lookup"><span data-stu-id="95c91-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="95c91-114">'U</span><span class="sxs-lookup"><span data-stu-id="95c91-114">'U</span></span>

<span data-ttu-id="95c91-115">O tipo do segundo membro do par.</span><span class="sxs-lookup"><span data-stu-id="95c91-115">The type of the pair's second member.</span></span>