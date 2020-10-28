---
uid: Microsoft.Quantum.Canon.Angle
title: Função de ângulo
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: da3ecdaf1b2c88180bd2a660fac0b6e87b2cafa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718487"
---
# <a name="angle-function"></a><span data-ttu-id="4c495-102">Função de ângulo</span><span class="sxs-lookup"><span data-stu-id="4c495-102">Angle function</span></span>

<span data-ttu-id="4c495-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4c495-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4c495-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4c495-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4c495-105">Devoluções 1, se `index` tiver um número ímpar de 1s e -1, se tiver um número par de `index` 1s.</span><span class="sxs-lookup"><span data-stu-id="4c495-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="4c495-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="4c495-106">Description</span></span>

<span data-ttu-id="4c495-107">O valor corresponde ao sinal do coeficiente do espectro Rademacher-Walsh da função n-variável E para uma determinada atribuição que decide o ângulo da rotação.</span><span class="sxs-lookup"><span data-stu-id="4c495-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="4c495-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="4c495-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="4c495-109">índice : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4c495-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4c495-110">Atribuição de entrada como inteiro (de 0 a 2^n - 1)</span><span class="sxs-lookup"><span data-stu-id="4c495-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="4c495-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4c495-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

