---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: Função IsNotZero
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839605"
---
# <a name="isnotzero-function"></a><span data-ttu-id="7cd79-102">Função IsNotZero</span><span class="sxs-lookup"><span data-stu-id="7cd79-102">IsNotZero function</span></span>

<span data-ttu-id="7cd79-103">Espaço de nome: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7cd79-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="7cd79-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7cd79-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="7cd79-105">Verifica se um `Double` número não é aproximadamente zero.</span><span class="sxs-lookup"><span data-stu-id="7cd79-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="7cd79-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7cd79-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="7cd79-107">número : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7cd79-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7cd79-108">Número a ser verificado</span><span class="sxs-lookup"><span data-stu-id="7cd79-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="7cd79-109">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7cd79-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7cd79-110">Retorna verdadeira se `number` tiver um valor absoluto superior a `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="7cd79-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>