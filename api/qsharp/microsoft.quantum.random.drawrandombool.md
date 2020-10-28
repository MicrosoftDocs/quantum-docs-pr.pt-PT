---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Operação DrawRandomBool
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720275"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="6f4b0-102">Operação DrawRandomBool</span><span class="sxs-lookup"><span data-stu-id="6f4b0-102">DrawRandomBool operation</span></span>

<span data-ttu-id="6f4b0-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="6f4b0-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="6f4b0-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6f4b0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6f4b0-105">Dada a probabilidade de sucesso, devolve um único ensaio de Bernoulli que é verdade com a probabilidade dada.</span><span class="sxs-lookup"><span data-stu-id="6f4b0-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="6f4b0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6f4b0-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="6f4b0-107">sucessoProbabilidade : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6f4b0-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6f4b0-108">A probabilidade com que `true` deve ser devolvida.</span><span class="sxs-lookup"><span data-stu-id="6f4b0-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6f4b0-109">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6f4b0-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6f4b0-110">`true` com probabilidade `successProbability` e `false` com `1.0 - successProbability` probabilidade.</span><span class="sxs-lookup"><span data-stu-id="6f4b0-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>