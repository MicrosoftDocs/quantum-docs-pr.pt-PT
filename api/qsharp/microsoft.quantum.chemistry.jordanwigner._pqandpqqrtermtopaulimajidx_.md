---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliMajIdx_
title: _Função PQandPQQRTermToPauliMajIdx_
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 68a9aec7768269e2d5f295d5ea3cbb136ea1ef2c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851498"
---
# <a name="_pqandpqqrtermtopaulimajidx_-function"></a><span data-ttu-id="cfebb-102">_Função PQandPQQRTermToPauliMajIdx_</span><span class="sxs-lookup"><span data-stu-id="cfebb-102">_PQandPQQRTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="cfebb-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="cfebb-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="cfebb-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="cfebb-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="cfebb-105">Converte um GeneratorIndex descrevendo um termo PQ ou PQQR para uma expressão 'GeneratorIndex[]' em termos de Paulis</span><span class="sxs-lookup"><span data-stu-id="cfebb-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="cfebb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cfebb-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="cfebb-107">termo : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="cfebb-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="cfebb-108">`GeneratorIndex` representando um termo PQ ou PQQR.</span><span class="sxs-lookup"><span data-stu-id="cfebb-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="cfebb-109">Saída : [OtimizadoBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="cfebb-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="cfebb-110">'GeneratorIndex[]' expressando o termo PQ ou PQQR como termos Pauli.</span><span class="sxs-lookup"><span data-stu-id="cfebb-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>