---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliGenIdx_
title: _Função PQandPQQRTermToPauliGenIdx_
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: c4de9593927b12b2387ae0b46513970308f59c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839329"
---
# <a name="_pqandpqqrtermtopauligenidx_-function"></a><span data-ttu-id="dfc30-102">_Função PQandPQQRTermToPauliGenIdx_</span><span class="sxs-lookup"><span data-stu-id="dfc30-102">_PQandPQQRTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="dfc30-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="dfc30-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="dfc30-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="dfc30-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="dfc30-105">Converte um GeneratorIndex descrevendo um termo PQ ou PQQR para uma expressão 'GeneratorIndex[]' em termos de Paulis</span><span class="sxs-lookup"><span data-stu-id="dfc30-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="dfc30-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="dfc30-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="dfc30-107">termo : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="dfc30-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="dfc30-108">`GeneratorIndex` representando um termo PQ ou PQQR.</span><span class="sxs-lookup"><span data-stu-id="dfc30-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="dfc30-109">Saída : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="dfc30-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="dfc30-110">'GeneratorIndex[]' expressando o termo PQ ou PQQR como termos Pauli.</span><span class="sxs-lookup"><span data-stu-id="dfc30-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>