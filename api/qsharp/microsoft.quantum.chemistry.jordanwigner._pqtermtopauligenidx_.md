---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliGenIdx_
title: _Função PQTermToPauliGenIdx_
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 046b3b7b78cee7f046607277896100e20c33a32d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839302"
---
# <a name="_pqtermtopauligenidx_-function"></a><span data-ttu-id="1fc32-102">_Função PQTermToPauliGenIdx_</span><span class="sxs-lookup"><span data-stu-id="1fc32-102">_PQTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="1fc32-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="1fc32-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="1fc32-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="1fc32-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="1fc32-105">Converte um GeneratorIndex descrevendo um termo PQ com uma expressão 'GeneratorIndex[]' em termos de Paulis</span><span class="sxs-lookup"><span data-stu-id="1fc32-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="1fc32-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1fc32-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="1fc32-107">termo : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="1fc32-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="1fc32-108">`GeneratorIndex` representando um termo PQ.</span><span class="sxs-lookup"><span data-stu-id="1fc32-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="1fc32-109">Saída : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="1fc32-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="1fc32-110">'GeneratorIndex[]' expressando o termo PQ como termos Pauli.</span><span class="sxs-lookup"><span data-stu-id="1fc32-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>