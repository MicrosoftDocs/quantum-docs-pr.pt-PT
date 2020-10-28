---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: Função QuantumROMQubitCount
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 988d5efa3e27cf5e9a276ab3ab443c10f88fe1ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722932"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="00090-102">Função QuantumROMQubitCount</span><span class="sxs-lookup"><span data-stu-id="00090-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="00090-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="00090-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="00090-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="00090-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="00090-105">Devolve o número total de qubits que devem ser atribuídos à operação devolvido por `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="00090-105">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="00090-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="00090-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="00090-107">targetError : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="00090-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="00090-108">O erro do alvo $\epsilon$.</span><span class="sxs-lookup"><span data-stu-id="00090-108">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="00090-109">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="00090-109">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="00090-110">Número de coeficientes especificados em `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="00090-110">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="00090-111">Saída : ([Int](xref:microsoft.quantum.lang-ref.int)[(Int](xref:microsoft.quantum.lang-ref.int),[Int))](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="00090-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="00090-112">Primeiro parâmetro</span><span class="sxs-lookup"><span data-stu-id="00090-112">First parameter</span></span>

<span data-ttu-id="00090-113">Um tuple `(x,(y,z))` onde está o número total de `x = y + z` qubits atribuídos, `y` é o número de qubits para o `LittleEndian` registo, e é o número de `z` qubits de lixo.</span><span class="sxs-lookup"><span data-stu-id="00090-113">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>