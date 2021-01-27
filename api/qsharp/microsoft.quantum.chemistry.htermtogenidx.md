---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: Função HTermToGenIdx
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 46745632e2f6bafad0d7359141522b84f48c039d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839606"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="75e2d-102">Função HTermToGenIdx</span><span class="sxs-lookup"><span data-stu-id="75e2d-102">HTermToGenIdx function</span></span>

<span data-ttu-id="75e2d-103">Espaço de nome: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="75e2d-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="75e2d-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="75e2d-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="75e2d-105">Converte um termo Hamiltonian em `HTerm` formato de dados para um GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="75e2d-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="75e2d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="75e2d-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="75e2d-107">termo : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="75e2d-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="75e2d-108">Inserir dados em `HTerm` formato.</span><span class="sxs-lookup"><span data-stu-id="75e2d-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="75e2d-109">termoType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="75e2d-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="75e2d-110">Informação adicional adicionada ao GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="75e2d-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="75e2d-111">Saída : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="75e2d-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="75e2d-112">Um GeneratorIndex que representa um termo Hamiltoniano representado `term` por, juntamente com informações adicionais adicionadas por `termType` .</span><span class="sxs-lookup"><span data-stu-id="75e2d-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>