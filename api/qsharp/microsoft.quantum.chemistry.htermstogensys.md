---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: Função HTermsToGenSys
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 3d5963b8751a22d7116d6c1cf094d89e1d6b556f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851770"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="9650e-102">Função HTermsToGenSys</span><span class="sxs-lookup"><span data-stu-id="9650e-102">HTermsToGenSys function</span></span>

<span data-ttu-id="9650e-103">Espaço de nome: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="9650e-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="9650e-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="9650e-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="9650e-105">Converte um Hamiltonian em `HTerm[]` formato de dados para um GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="9650e-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="9650e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9650e-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="9650e-107">dados : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="9650e-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="9650e-108">Inserir dados em `HTerm[]` formato.</span><span class="sxs-lookup"><span data-stu-id="9650e-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="9650e-109">termoType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9650e-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9650e-110">Informação adicional adicionada ao GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="9650e-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="9650e-111">Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="9650e-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="9650e-112">Um Sistema Gerador representando um Hamiltonian representado pela entrada `data` .</span><span class="sxs-lookup"><span data-stu-id="9650e-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>