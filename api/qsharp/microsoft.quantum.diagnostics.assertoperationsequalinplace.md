---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 407a139da816281346eb06849f81e91b83202653
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712974"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="53e93-102">AssertOperationsEqualInPlace</span><span class="sxs-lookup"><span data-stu-id="53e93-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="53e93-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="53e93-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="53e93-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53e93-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53e93-105">Tendo em conta duas operações, afirma que agem de forma idêntica para todos os estados de entrada.</span><span class="sxs-lookup"><span data-stu-id="53e93-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="53e93-106">Esta afirmação é implementada verificando a ação das operações em todos os estados do formulário $V_0 \otimes ... \otimes V_{n-1}$, onde $V_k$ é um dos estados $\ket {0} $,$ket {1} $, $\ket{+}$ e $\ket{i}$ (+1 eigenstate do operador Pauli Y).</span><span class="sxs-lookup"><span data-stu-id="53e93-106">This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).</span></span>

<span data-ttu-id="53e93-107">Esta afirmação utiliza $n$ qubits e requer múltiplas chamadas das operações a serem comparadas.</span><span class="sxs-lookup"><span data-stu-id="53e93-107">This assertion uses $n$ qubits and requires multiple calls of the operations being compared.</span></span>

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="53e93-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="53e93-108">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="53e93-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="53e93-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="53e93-110">O número de qubits $n$ que as operações `givenU` e `expectedU` operam.</span><span class="sxs-lookup"><span data-stu-id="53e93-110">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="53e93-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="53e93-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="53e93-112">Operação a $n dólares qubits a serem verificados.</span><span class="sxs-lookup"><span data-stu-id="53e93-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="53e93-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="53e93-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="53e93-114">Operação de referência em $n$ qubits que `givenU` devem ser comparados.</span><span class="sxs-lookup"><span data-stu-id="53e93-114">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="53e93-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="53e93-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="53e93-116">Referências</span><span class="sxs-lookup"><span data-stu-id="53e93-116">References</span></span>

<span data-ttu-id="53e93-117">A base dos estados $\ket {0} $, $\ket {1} $, $\ket{+}$ e $\ket{i}$ é a base Chuang-Nielsen, descrita em [ *I. L. Chuang, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).</span><span class="sxs-lookup"><span data-stu-id="53e93-117">The basis of states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ is the Chuang-Nielsen basis, described in [ *I. L. Chuang, M. A. Nielsen* ](https://arxiv.org/abs/quant-ph/9610001).</span></span>

## <a name="see-also"></a><span data-ttu-id="53e93-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="53e93-118">See Also</span></span>

- [<span data-ttu-id="53e93-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="53e93-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)