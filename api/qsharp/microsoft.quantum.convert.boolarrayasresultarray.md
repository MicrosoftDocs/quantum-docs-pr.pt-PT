---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: Função BoolArrayAsResultArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: b30da07272ee1a6c19ae13afa618ba5deb7aaa2d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834196"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="23415-102">Função BoolArrayAsResultArray</span><span class="sxs-lookup"><span data-stu-id="23415-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="23415-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="23415-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="23415-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="23415-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="23415-105">Converte um `Bool[]` tipo para um `Result[]` tipo, onde é `true` mapeado `One` e `false` mapeado para `Zero` .</span><span class="sxs-lookup"><span data-stu-id="23415-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="23415-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="23415-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="23415-107">entrada : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="23415-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="23415-108">`Bool[]` para ser convertido.</span><span class="sxs-lookup"><span data-stu-id="23415-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="23415-109">Saída: __<Result> inválido__[]</span><span class="sxs-lookup"><span data-stu-id="23415-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="23415-110">Um `Result[]` representante `input` do.</span><span class="sxs-lookup"><span data-stu-id="23415-110">A `Result[]` representing the `input`.</span></span>