---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedGeneratorSystem
title: Função JWOptimizedGeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 8e4c06b9447a2e5838cced876febee03d1af5315
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710779"
---
# <a name="jwoptimizedgeneratorsystem-function"></a><span data-ttu-id="756dc-102">Função JWOptimizedGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="756dc-102">JWOptimizedGeneratorSystem function</span></span>

<span data-ttu-id="756dc-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="756dc-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="756dc-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="756dc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="756dc-105">Converte um Hamiltonian descrito por `JWOptimizedHTerms` um expresso em termos da `GeneratorSystem` `GeneratorIndex` convenção definida neste ficheiro.</span><span class="sxs-lookup"><span data-stu-id="756dc-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JWOptimizedGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="756dc-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="756dc-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="756dc-107">dados : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="756dc-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="756dc-108">Descrição de Hamiltonian em `JWOptimizedHTerms` formato.</span><span class="sxs-lookup"><span data-stu-id="756dc-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="756dc-109">Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="756dc-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="756dc-110">Representação de Hamiltonian como `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="756dc-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>