---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: Aplicação OperaçãoCNOTChain
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: e237e4424661de816e73b0c78523180b41190cf9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219146"
---
# <a name="applycnotchain-operation"></a><span data-ttu-id="1d4df-102">Aplicação OperaçãoCNOTChain</span><span class="sxs-lookup"><span data-stu-id="1d4df-102">ApplyCNOTChain operation</span></span>

<span data-ttu-id="1d4df-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1d4df-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1d4df-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1d4df-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1d4df-105">Calcula a paridade de um registo de qubits no lugar.</span><span class="sxs-lookup"><span data-stu-id="1d4df-105">Computes the parity of a register of qubits in-place.</span></span>

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="1d4df-106">Description</span><span class="sxs-lookup"><span data-stu-id="1d4df-106">Description</span></span>

<span data-ttu-id="1d4df-107">Esta operação transforma o estado da sua entrada como $$ \start{align} \ket{q_0} \ket{q_1} \cdots \ket{q_{n - 1}} & \mapsto \ket{q_0} \000 {q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_{n - 1}}}</span><span class="sxs-lookup"><span data-stu-id="1d4df-107">This operation transforms the state of its input as $$ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_{n - 1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_{n - 1}}.</span></span>
<span data-ttu-id="1d4df-108">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="1d4df-108">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="1d4df-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="1d4df-109">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="1d4df-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1d4df-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1d4df-111">Matriz de qubits cuja paridade deve ser calculada e armazenada.</span><span class="sxs-lookup"><span data-stu-id="1d4df-111">Array of qubits whose parity is to be computed and stored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1d4df-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1d4df-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

