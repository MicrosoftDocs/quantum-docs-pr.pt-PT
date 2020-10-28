---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: Função BoolArrayAsPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c5ef71322dae248fc2c6b1db3adf891de7d72488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713604"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="07ecc-102">Função BoolArrayAsPauli</span><span class="sxs-lookup"><span data-stu-id="07ecc-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="07ecc-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="07ecc-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="07ecc-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07ecc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07ecc-105">Dado um pouco de corda, devolve um operador pauli multi-qubit representado como uma variedade de operadores pauli de um único qubit.</span><span class="sxs-lookup"><span data-stu-id="07ecc-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="07ecc-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="07ecc-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="07ecc-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="07ecc-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="07ecc-108">Operador Pauli para aplicar aos qubits onde `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="07ecc-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="07ecc-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="07ecc-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="07ecc-110">aplicar Pauli se bit é este valor.</span><span class="sxs-lookup"><span data-stu-id="07ecc-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="07ecc-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="07ecc-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="07ecc-112">Matriz booleana.</span><span class="sxs-lookup"><span data-stu-id="07ecc-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="07ecc-113">Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="07ecc-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="07ecc-114">Observações</span><span class="sxs-lookup"><span data-stu-id="07ecc-114">Remarks</span></span>

<span data-ttu-id="07ecc-115">A matriz booleana e o registo quântico devem ter o mesmo comprimento.</span><span class="sxs-lookup"><span data-stu-id="07ecc-115">The Boolean array and the quantum register must be of equal length.</span></span>