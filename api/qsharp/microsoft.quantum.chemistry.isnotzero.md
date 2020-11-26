---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: Função IsNotZero
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204067"
---
# <a name="isnotzero-function"></a><span data-ttu-id="2f6ac-102">Função IsNotZero</span><span class="sxs-lookup"><span data-stu-id="2f6ac-102">IsNotZero function</span></span>

<span data-ttu-id="2f6ac-103">Espaço de nome: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="2f6ac-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="2f6ac-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="2f6ac-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="2f6ac-105">Verifica se um `Double` número não é aproximadamente zero.</span><span class="sxs-lookup"><span data-stu-id="2f6ac-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="2f6ac-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2f6ac-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="2f6ac-107">número : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2f6ac-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2f6ac-108">Número a ser verificado</span><span class="sxs-lookup"><span data-stu-id="2f6ac-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="2f6ac-109">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2f6ac-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2f6ac-110">Retorna verdadeira se `number` tiver um valor absoluto superior a `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="2f6ac-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>