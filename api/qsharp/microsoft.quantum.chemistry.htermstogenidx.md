---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: Função HTermsToGenIdx
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 84dc132528f8fd1c45fb2f7345111a05626ee686
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839636"
---
# <a name="htermstogenidx-function"></a><span data-ttu-id="fdb2b-102">Função HTermsToGenIdx</span><span class="sxs-lookup"><span data-stu-id="fdb2b-102">HTermsToGenIdx function</span></span>

<span data-ttu-id="fdb2b-103">Espaço de nome: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="fdb2b-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="fdb2b-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="fdb2b-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="fdb2b-105">Converte um índice para um termo Hamiltonian em `HTerm[]` formato de dados para um GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="fdb2b-105">Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="fdb2b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fdb2b-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="fdb2b-107">dados : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="fdb2b-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="fdb2b-108">Inserir dados em `HTerm[]` formato.</span><span class="sxs-lookup"><span data-stu-id="fdb2b-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="fdb2b-109">termoType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fdb2b-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fdb2b-110">Informação adicional adicionada ao GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="fdb2b-110">Additional information added to GeneratorIndex.</span></span>


### <a name="idx--int"></a><span data-ttu-id="fdb2b-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fdb2b-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fdb2b-112">Índice a um termo do Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="fdb2b-112">Index to a term of the Hamiltonian</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="fdb2b-113">Saída : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="fdb2b-113">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="fdb2b-114">Um GeneratorIndex que representa um termo Hamiltoniano representado `data[idx]` por, juntamente com informações adicionais adicionadas por `termType` .</span><span class="sxs-lookup"><span data-stu-id="fdb2b-114">A GeneratorIndex representing a Hamiltonian term represented by `data[idx]`, together with additional information added by `termType`.</span></span>