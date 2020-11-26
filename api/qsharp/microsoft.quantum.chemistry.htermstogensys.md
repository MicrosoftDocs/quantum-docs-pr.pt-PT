---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: Função HTermsToGenSys
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 936e1bcc58b2f1af3bdb606884128c38d2f58867
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204118"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="a511f-102">Função HTermsToGenSys</span><span class="sxs-lookup"><span data-stu-id="a511f-102">HTermsToGenSys function</span></span>

<span data-ttu-id="a511f-103">Espaço de nome: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a511f-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="a511f-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a511f-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="a511f-105">Converte um Hamiltonian em `HTerm[]` formato de dados para um GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="a511f-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="a511f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a511f-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="a511f-107">dados : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="a511f-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="a511f-108">Inserir dados em `HTerm[]` formato.</span><span class="sxs-lookup"><span data-stu-id="a511f-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="a511f-109">termoType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a511f-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a511f-110">Informação adicional adicionada ao GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="a511f-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="a511f-111">Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a511f-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a511f-112">Um Sistema Gerador representando um Hamiltonian representado pela entrada `data` .</span><span class="sxs-lookup"><span data-stu-id="a511f-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>