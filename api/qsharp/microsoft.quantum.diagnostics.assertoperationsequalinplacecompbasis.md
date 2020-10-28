---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis
title: AssertOperationsEqualInPlaceCompBabasis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis. This is a necessary, but not sufficient, condition for the equality of two unitaries.
ms.openlocfilehash: 3275680f86ca2a178c7f044b97d226fe41c3186c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712963"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a><span data-ttu-id="d1dc3-102">AssertOperationsEqualInPlaceCompBabasis</span><span class="sxs-lookup"><span data-stu-id="d1dc3-102">AssertOperationsEqualInPlaceCompBasis operation</span></span>

<span data-ttu-id="d1dc3-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d1dc3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d1dc3-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d1dc3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d1dc3-105">Verifica se a operação `givenU` é igual à operação no tamanho de entrada `expectedU` dado, verificando a ação das operações apenas nos vetores a partir da base computacional.</span><span class="sxs-lookup"><span data-stu-id="d1dc3-105">Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis.</span></span>
<span data-ttu-id="d1dc3-106">Esta é uma condição necessária, mas não suficiente, para a igualdade de duas unitárias.</span><span class="sxs-lookup"><span data-stu-id="d1dc3-106">This is a necessary, but not sufficient, condition for the equality of two unitaries.</span></span>

```qsharp
operation AssertOperationsEqualInPlaceCompBasis (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="d1dc3-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="d1dc3-107">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="d1dc3-108">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d1dc3-108">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d1dc3-109">O número de qubits $n$ que as operações `givenU` e `expectedU` operam.</span><span class="sxs-lookup"><span data-stu-id="d1dc3-109">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="d1dc3-110">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="d1dc3-110">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d1dc3-111">Operação a $n dólares qubits a serem verificados.</span><span class="sxs-lookup"><span data-stu-id="d1dc3-111">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="d1dc3-112">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="d1dc3-112">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="d1dc3-113">Operação de referência em $n$ qubits que `givenU` devem ser comparados.</span><span class="sxs-lookup"><span data-stu-id="d1dc3-113">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d1dc3-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d1dc3-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

