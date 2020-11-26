---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliMajIdx_
title: _Função PQandPQQRTermToPauliMajIdx_
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 1a04f5f3b66e0dccb650b2d451a086a380b9810a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225011"
---
# <a name="_pqandpqqrtermtopaulimajidx_-function"></a><span data-ttu-id="98eba-102">_Função PQandPQQRTermToPauliMajIdx_</span><span class="sxs-lookup"><span data-stu-id="98eba-102">_PQandPQQRTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="98eba-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="98eba-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="98eba-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="98eba-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="98eba-105">Converte um GeneratorIndex descrevendo um termo PQ ou PQQR para uma expressão 'GeneratorIndex[]' em termos de Paulis</span><span class="sxs-lookup"><span data-stu-id="98eba-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="98eba-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="98eba-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="98eba-107">termo : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="98eba-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="98eba-108">`GeneratorIndex` representando um termo PQ ou PQQR.</span><span class="sxs-lookup"><span data-stu-id="98eba-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="98eba-109">Saída : [OtimizadoBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="98eba-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="98eba-110">'GeneratorIndex[]' expressando o termo PQ ou PQQR como termos Pauli.</span><span class="sxs-lookup"><span data-stu-id="98eba-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>