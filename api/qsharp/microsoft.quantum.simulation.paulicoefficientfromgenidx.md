---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: Função PauliCoefficientFromGenIdx
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 59ddadabb5c77cdb0d2e3620a09433992e85f663
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225062"
---
# <a name="paulicoefficientfromgenidx-function"></a><span data-ttu-id="58594-102">Função PauliCoefficientFromGenIdx</span><span class="sxs-lookup"><span data-stu-id="58594-102">PauliCoefficientFromGenIdx function</span></span>

<span data-ttu-id="58594-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="58594-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="58594-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="58594-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="58594-105">Extrai o coeficiente de um termo Pauli descrito por um `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="58594-105">Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a><span data-ttu-id="58594-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="58594-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="58594-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="58594-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="58594-108">`GeneratorIndex` tipo que codifica um termo Pauli.</span><span class="sxs-lookup"><span data-stu-id="58594-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--double"></a><span data-ttu-id="58594-109">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="58594-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="58594-110">O coeficiente do termo descrito por a `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="58594-110">The coefficient of the term described by a `GeneratorIndex`.</span></span>