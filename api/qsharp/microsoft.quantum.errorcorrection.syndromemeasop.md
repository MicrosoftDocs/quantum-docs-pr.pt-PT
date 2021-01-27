---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Tipo definido pelo utilizador SyndromeMeasOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 36336f9e47e5f360cf5e19ffb6e15b4af88b2580
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850042"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="59253-102">Tipo definido pelo utilizador SyndromeMeasOp</span><span class="sxs-lookup"><span data-stu-id="59253-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="59253-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="59253-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="59253-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59253-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59253-105">Representa uma operação que é usada para medir a síndrome de um bloco de código que corrige erros.</span><span class="sxs-lookup"><span data-stu-id="59253-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a><span data-ttu-id="59253-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="59253-106">Example</span></span>

<span data-ttu-id="59253-107">Medir as síndromes para o código bit-flip $S = \langle ZZI, IZZ \rangle$ usando qubits de risco de forma tolerante sem falhas:</span><span class="sxs-lookup"><span data-stu-id="59253-107">Measure syndromes for the bit-flip code $S = \langle ZZI, IZZ \rangle$ using scratch qubits in a non–fault tolerant manner:</span></span>

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a><span data-ttu-id="59253-108">Observações</span><span class="sxs-lookup"><span data-stu-id="59253-108">Remarks</span></span>

<span data-ttu-id="59253-109">A assinatura `(LogicalRegister => Syndrome)` representa uma operação que atua conjuntamente nos qubits `LogicalRegister` e alguns qubits auxiliares seguidos de uma medição dos qubits auxiliares para extrair um `Syndrome` valor que representa as `Result[]` destas medições.</span><span class="sxs-lookup"><span data-stu-id="59253-109">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="59253-110">Consulte também</span><span class="sxs-lookup"><span data-stu-id="59253-110">See Also</span></span>

- [<span data-ttu-id="59253-111">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="59253-111">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="59253-112">Microsoft.Quantum.ErrorCorrection.Syndrome</span><span class="sxs-lookup"><span data-stu-id="59253-112">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)