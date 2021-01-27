---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: Função BoolArrayAsPauli
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c11ca05ad8a939d704547c65a8e8a6537d0df4b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834237"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="b4044-102">Função BoolArrayAsPauli</span><span class="sxs-lookup"><span data-stu-id="b4044-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="b4044-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="b4044-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="b4044-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b4044-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b4044-105">Dado um pouco de corda, devolve um operador pauli multi-qubit representado como uma variedade de operadores pauli de um único qubit.</span><span class="sxs-lookup"><span data-stu-id="b4044-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="b4044-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b4044-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="b4044-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="b4044-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="b4044-108">Operador Pauli para aplicar aos qubits onde `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="b4044-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="b4044-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b4044-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b4044-110">aplicar Pauli se bit é este valor.</span><span class="sxs-lookup"><span data-stu-id="b4044-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="b4044-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b4044-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b4044-112">Matriz booleana.</span><span class="sxs-lookup"><span data-stu-id="b4044-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="b4044-113">Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="b4044-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="b4044-114">Observações</span><span class="sxs-lookup"><span data-stu-id="b4044-114">Remarks</span></span>

<span data-ttu-id="b4044-115">A matriz booleana e o registo quântico devem ter o mesmo comprimento.</span><span class="sxs-lookup"><span data-stu-id="b4044-115">The Boolean array and the quantum register must be of equal length.</span></span>