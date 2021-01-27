---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: Função WeightOnePaulis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 8aeea795ef5409339e8a1b39c3ffcfaf29d675b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851974"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="f2351-102">Função WeightOnePaulis</span><span class="sxs-lookup"><span data-stu-id="f2351-102">WeightOnePaulis function</span></span>

<span data-ttu-id="f2351-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f2351-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f2351-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2351-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2351-105">Devolve uma série de todos os operadores de Peso-1 Pauli num dado número de qubits.</span><span class="sxs-lookup"><span data-stu-id="f2351-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="f2351-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f2351-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="f2351-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f2351-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f2351-108">O número de qubits em que os operadores pauli devolvidos são definidos.</span><span class="sxs-lookup"><span data-stu-id="f2351-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="f2351-109">Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][ ]</span><span class="sxs-lookup"><span data-stu-id="f2351-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="f2351-110">Uma matriz de operadores pauli multi-qubit, cada um dos quais é representado como uma matriz com comprimento `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="f2351-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>