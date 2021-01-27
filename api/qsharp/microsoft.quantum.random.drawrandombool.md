---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Operação DrawRandomBool
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853681"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="3704e-102">Operação DrawRandomBool</span><span class="sxs-lookup"><span data-stu-id="3704e-102">DrawRandomBool operation</span></span>

<span data-ttu-id="3704e-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3704e-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3704e-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3704e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3704e-105">Dada a probabilidade de sucesso, devolve um único ensaio de Bernoulli que é verdade com a probabilidade dada.</span><span class="sxs-lookup"><span data-stu-id="3704e-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="3704e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3704e-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="3704e-107">sucessoProbabilidade : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3704e-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3704e-108">A probabilidade com que `true` deve ser devolvida.</span><span class="sxs-lookup"><span data-stu-id="3704e-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3704e-109">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3704e-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3704e-110">`true` com probabilidade `successProbability` e `false` com `1.0 - successProbability` probabilidade.</span><span class="sxs-lookup"><span data-stu-id="3704e-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>

## <a name="example"></a><span data-ttu-id="3704e-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3704e-111">Example</span></span>

<span data-ttu-id="3704e-112">As seguintes amostras de corte Q# lançam-se de uma moeda tendenciosa:</span><span class="sxs-lookup"><span data-stu-id="3704e-112">The following Q# snippet samples flips from a biased coin:</span></span>

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```