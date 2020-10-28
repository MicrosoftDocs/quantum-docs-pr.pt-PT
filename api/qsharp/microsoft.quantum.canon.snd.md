---
uid: Microsoft.Quantum.Canon.Snd
title: Função Snd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c05053b45d24c3398526d1269b90bb40d1e0ef27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715452"
---
# <a name="snd-function"></a><span data-ttu-id="5dbe6-102">Função Snd</span><span class="sxs-lookup"><span data-stu-id="5dbe6-102">Snd function</span></span>

<span data-ttu-id="5dbe6-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5dbe6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5dbe6-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5dbe6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5dbe6-105">Dado um par, devolve o seu segundo elemento.</span><span class="sxs-lookup"><span data-stu-id="5dbe6-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="5dbe6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5dbe6-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="5dbe6-107">par : ('T,'U)</span><span class="sxs-lookup"><span data-stu-id="5dbe6-107">pair : ('T,'U)</span></span>

<span data-ttu-id="5dbe6-108">Uma tuple com dois elementos.</span><span class="sxs-lookup"><span data-stu-id="5dbe6-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="5dbe6-109">Saída : 'U</span><span class="sxs-lookup"><span data-stu-id="5dbe6-109">Output : 'U</span></span>

<span data-ttu-id="5dbe6-110">O segundo elemento `pair` de.</span><span class="sxs-lookup"><span data-stu-id="5dbe6-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5dbe6-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="5dbe6-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5dbe6-112">'T</span><span class="sxs-lookup"><span data-stu-id="5dbe6-112">'T</span></span>

<span data-ttu-id="5dbe6-113">O tipo do primeiro membro do par.</span><span class="sxs-lookup"><span data-stu-id="5dbe6-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="5dbe6-114">'U</span><span class="sxs-lookup"><span data-stu-id="5dbe6-114">'U</span></span>

<span data-ttu-id="5dbe6-115">O tipo do segundo membro do par.</span><span class="sxs-lookup"><span data-stu-id="5dbe6-115">The type of the pair's second member.</span></span>