---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: Função QuantumROMQubitCount
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 0ec1e042b9f675505f73bfcdcc6706d0bc0367df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210408"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="a766d-102">Função QuantumROMQubitCount</span><span class="sxs-lookup"><span data-stu-id="a766d-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="a766d-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="a766d-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="a766d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a766d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="a766d-105">QuantumROMQubitCount foi depreciado.</span><span class="sxs-lookup"><span data-stu-id="a766d-105">QuantumROMQubitCount has been deprecated.</span></span> <span data-ttu-id="a766d-106">Por favor, use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="a766d-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.</span></span>

<span data-ttu-id="a766d-107">Devolve o número total de qubits que devem ser atribuídos à operação devolvido por `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="a766d-107">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="a766d-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="a766d-108">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="a766d-109">targetError : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a766d-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a766d-110">O erro do alvo $\epsilon$.</span><span class="sxs-lookup"><span data-stu-id="a766d-110">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="a766d-111">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a766d-111">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a766d-112">Número de coeficientes especificados em `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="a766d-112">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="a766d-113">Saída : ([Int](xref:microsoft.quantum.lang-ref.int)[(Int](xref:microsoft.quantum.lang-ref.int),[Int))](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a766d-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="a766d-114">Primeiro parâmetro</span><span class="sxs-lookup"><span data-stu-id="a766d-114">First parameter</span></span>

<span data-ttu-id="a766d-115">Um tuple `(x,(y,z))` onde está o número total de `x = y + z` qubits atribuídos, `y` é o número de qubits para o `LittleEndian` registo, e é o número de `z` qubits de lixo.</span><span class="sxs-lookup"><span data-stu-id="a766d-115">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>