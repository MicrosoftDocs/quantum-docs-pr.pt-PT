---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: Função IsCoprimeL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: a48f056d138499607d32b38b1fa0970745732c41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851348"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="b5cb5-102">Função IsCoprimeL</span><span class="sxs-lookup"><span data-stu-id="b5cb5-102">IsCoprimeL function</span></span>

<span data-ttu-id="b5cb5-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b5cb5-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b5cb5-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5cb5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5cb5-105">Devoluções verdadeiras se $a$ e $b$ são co-prime e falso de outra forma.</span><span class="sxs-lookup"><span data-stu-id="b5cb5-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="b5cb5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b5cb5-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="b5cb5-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b5cb5-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b5cb5-108">o primeiro número de que a co-primalidade está a ser testada</span><span class="sxs-lookup"><span data-stu-id="b5cb5-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="b5cb5-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b5cb5-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b5cb5-110">o segundo número de que co-primalidade está a ser testada</span><span class="sxs-lookup"><span data-stu-id="b5cb5-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="b5cb5-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b5cb5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b5cb5-112">É verdade, se $a$ e $b$ são co-prime (por exemplo, o seu maior divisor comum é 1), e falso de outra forma</span><span class="sxs-lookup"><span data-stu-id="b5cb5-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>