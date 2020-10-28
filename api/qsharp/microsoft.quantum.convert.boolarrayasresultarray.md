---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: Função BoolArrayAsResultArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 50a2bdb4a73ef9d67d3f5532493c142bb7f753cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713593"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="4fdf0-102">Função BoolArrayAsResultArray</span><span class="sxs-lookup"><span data-stu-id="4fdf0-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="4fdf0-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="4fdf0-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="4fdf0-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4fdf0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4fdf0-105">Converte um `Bool[]` tipo para um `Result[]` tipo, onde é `true` mapeado `One` e `false` mapeado para `Zero` .</span><span class="sxs-lookup"><span data-stu-id="4fdf0-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="4fdf0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4fdf0-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="4fdf0-107">entrada : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="4fdf0-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="4fdf0-108">`Bool[]` para ser convertido.</span><span class="sxs-lookup"><span data-stu-id="4fdf0-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="4fdf0-109">Saída: __<Result> inválido__ []</span><span class="sxs-lookup"><span data-stu-id="4fdf0-109">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="4fdf0-110">Um `Result[]` representante `input` do.</span><span class="sxs-lookup"><span data-stu-id="4fdf0-110">A `Result[]` representing the `input`.</span></span>