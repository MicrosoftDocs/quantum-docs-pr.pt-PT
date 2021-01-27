---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: Aplicar operaçãoPauliFromBitString
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: e0edd8420127339116e525421ba23e246dcf0a45
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841578"
---
# <a name="applypaulifrombitstring-operation"></a><span data-ttu-id="dfbfb-102">Aplicar operaçãoPauliFromBitString</span><span class="sxs-lookup"><span data-stu-id="dfbfb-102">ApplyPauliFromBitString operation</span></span>

<span data-ttu-id="dfbfb-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dfbfb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dfbfb-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dfbfb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dfbfb-105">Aplica um operador Pauli em cada qubit numa matriz se a parte correspondente de uma matriz Boolean corresponder a uma determinada entrada.</span><span class="sxs-lookup"><span data-stu-id="dfbfb-105">Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.</span></span>

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dfbfb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="dfbfb-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="dfbfb-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="dfbfb-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="dfbfb-108">Operador Pauli para aplicar a `qubits[idx]` onde `bitsApply == bits[idx]`</span><span class="sxs-lookup"><span data-stu-id="dfbfb-108">Pauli operator to apply to `qubits[idx]` where `bitsApply == bits[idx]`</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="dfbfb-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dfbfb-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dfbfb-110">aplicar Pauli se bit é este valor</span><span class="sxs-lookup"><span data-stu-id="dfbfb-110">apply Pauli if bit is this value</span></span>


### <a name="bits--bool"></a><span data-ttu-id="dfbfb-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="dfbfb-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="dfbfb-112">Registo booleano especificando qual o qubit correspondente `qubits` em deve ser operado em</span><span class="sxs-lookup"><span data-stu-id="dfbfb-112">Boolean register specifying which corresponding qubit in `qubits` should be operated on</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="dfbfb-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dfbfb-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dfbfb-114">Registo quântico no qual aplicar seletivamente o operador pauli especificado</span><span class="sxs-lookup"><span data-stu-id="dfbfb-114">Quantum register on which to selectively apply the specified Pauli operator</span></span>



## <a name="output--unit"></a><span data-ttu-id="dfbfb-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dfbfb-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dfbfb-116">Observações</span><span class="sxs-lookup"><span data-stu-id="dfbfb-116">Remarks</span></span>

<span data-ttu-id="dfbfb-117">A matriz booleana e o registo quântico devem ter o mesmo comprimento.</span><span class="sxs-lookup"><span data-stu-id="dfbfb-117">The Boolean array and the quantum register must be of equal length.</span></span>