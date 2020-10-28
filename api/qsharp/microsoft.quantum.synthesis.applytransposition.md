---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Aplicação Operação Deposição
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725259"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="6c90e-102">Aplicação Operação Deposição</span><span class="sxs-lookup"><span data-stu-id="6c90e-102">ApplyTransposition operation</span></span>

<span data-ttu-id="6c90e-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="6c90e-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="6c90e-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6c90e-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="6c90e-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="6c90e-105">Description</span></span>

<span data-ttu-id="6c90e-106">Esta operação troca a amplitude em índice `a` com a amplitude no índice no dado `b` estado-vector `register` de comprimento $n$.</span><span class="sxs-lookup"><span data-stu-id="6c90e-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="6c90e-107">Se `a` for `b` igual, o vetor do estado não é alterado.</span><span class="sxs-lookup"><span data-stu-id="6c90e-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="6c90e-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="6c90e-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="6c90e-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6c90e-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6c90e-110">Primeiro índice (deve ser um valor de 0 a $2^n - 1$)</span><span class="sxs-lookup"><span data-stu-id="6c90e-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="6c90e-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6c90e-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6c90e-112">Segundo índice (deve ser um valor de 0 a $2^n - 1$)</span><span class="sxs-lookup"><span data-stu-id="6c90e-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="6c90e-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6c90e-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6c90e-114">Uma lista de $n$ qubits aos quais a transposição é aplicada.</span><span class="sxs-lookup"><span data-stu-id="6c90e-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6c90e-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6c90e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

