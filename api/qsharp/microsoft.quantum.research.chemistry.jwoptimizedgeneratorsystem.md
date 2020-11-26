---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedGeneratorSystem
title: Função JWOptimizedGeneratorSystem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 321b58ba4a458ad53579d2480258a92ba48de169
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225708"
---
# <a name="jwoptimizedgeneratorsystem-function"></a><span data-ttu-id="6601f-102">Função JWOptimizedGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="6601f-102">JWOptimizedGeneratorSystem function</span></span>

<span data-ttu-id="6601f-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6601f-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="6601f-104">Pacote: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6601f-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="6601f-105">Converte um Hamiltonian descrito por `JWOptimizedHTerms` um expresso em termos da `GeneratorSystem` `GeneratorIndex` convenção definida neste ficheiro.</span><span class="sxs-lookup"><span data-stu-id="6601f-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JWOptimizedGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="6601f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6601f-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="6601f-107">dados : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="6601f-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="6601f-108">Descrição de Hamiltonian em `JWOptimizedHTerms` formato.</span><span class="sxs-lookup"><span data-stu-id="6601f-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="6601f-109">Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="6601f-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="6601f-110">Representação de Hamiltonian como `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="6601f-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>