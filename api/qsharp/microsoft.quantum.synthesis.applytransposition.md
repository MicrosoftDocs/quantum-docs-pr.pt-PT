---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Aplicação Operação Deposição
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 46cf8c2c891aa02b0d8a1397e6c2b7a4b8618048
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855567"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="fc1b7-102">Aplicação Operação Deposição</span><span class="sxs-lookup"><span data-stu-id="fc1b7-102">ApplyTransposition operation</span></span>

<span data-ttu-id="fc1b7-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="fc1b7-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="fc1b7-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc1b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="fc1b7-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="fc1b7-105">Description</span></span>

<span data-ttu-id="fc1b7-106">Esta operação troca a amplitude em índice `a` com a amplitude no índice no dado `b` estado-vector `register` de comprimento $n$.</span><span class="sxs-lookup"><span data-stu-id="fc1b7-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="fc1b7-107">Se `a` for `b` igual, o vetor do estado não é alterado.</span><span class="sxs-lookup"><span data-stu-id="fc1b7-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="fc1b7-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="fc1b7-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="fc1b7-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fc1b7-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fc1b7-110">Primeiro índice (deve ser um valor de 0 a $2^n - 1$)</span><span class="sxs-lookup"><span data-stu-id="fc1b7-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="fc1b7-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fc1b7-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fc1b7-112">Segundo índice (deve ser um valor de 0 a $2^n - 1$)</span><span class="sxs-lookup"><span data-stu-id="fc1b7-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="fc1b7-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fc1b7-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fc1b7-114">Uma lista de $n$ qubits aos quais a transposição é aplicada.</span><span class="sxs-lookup"><span data-stu-id="fc1b7-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fc1b7-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc1b7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="fc1b7-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="fc1b7-116">Example</span></span>

<span data-ttu-id="fc1b7-117">Prepare uma superposição uniforme dos estados de número $|1\rangle$, $|2\rangle$, e $|3\rangle$ em 2 qubits.</span><span class="sxs-lookup"><span data-stu-id="fc1b7-117">Prepare a uniform superposition of number states $|1\rangle$, $|2\rangle$, and $|3\rangle$ on 2 qubits.</span></span>

```qsharp
using (qubits = Qubit[2]) {
  let register = LittleEndian(qubits);
  PrepareUniformSuperposition(3, register);
  ApplyTransposition(0, 3, register);
}
```