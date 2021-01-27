---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: AplicarMajorityInPlace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 10b512392b2098663c09b2e07a09c4025da90706
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843734"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="c0d4f-102">AplicarMajorityInPlace</span><span class="sxs-lookup"><span data-stu-id="c0d4f-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="c0d4f-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c0d4f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c0d4f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c0d4f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c0d4f-105">Aplica a operação por maioria de três qubits no local num registo de qubits.</span><span class="sxs-lookup"><span data-stu-id="c0d4f-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="c0d4f-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="c0d4f-106">Description</span></span>

<span data-ttu-id="c0d4f-107">Esta operação calcula a função maioritária no local em 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="c0d4f-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="c0d4f-108">Se denotarmos o qubit de saída como $z$ e qubits de entrada como $x$ e $y$, a operação executa a seguinte transformação: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}.</span><span class="sxs-lookup"><span data-stu-id="c0d4f-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="c0d4f-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="c0d4f-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="c0d4f-110">saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c0d4f-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c0d4f-111">Primeiro qubit de entrada.</span><span class="sxs-lookup"><span data-stu-id="c0d4f-111">First input qubit.</span></span> <span data-ttu-id="c0d4f-112">Note que a saída é calculada no local e armazenada neste qubit.</span><span class="sxs-lookup"><span data-stu-id="c0d4f-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="c0d4f-113">entrada : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c0d4f-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c0d4f-114">Segundo e terceiro qubits de entrada.</span><span class="sxs-lookup"><span data-stu-id="c0d4f-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c0d4f-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0d4f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

