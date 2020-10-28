---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: Aplicação Operação TNOTChainWithTarget
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718366"
---
# <a name="applycnotchainwithtarget-operation"></a><span data-ttu-id="08340-102">Aplicação Operação TNOTChainWithTarget</span><span class="sxs-lookup"><span data-stu-id="08340-102">ApplyCNOTChainWithTarget operation</span></span>

<span data-ttu-id="08340-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="08340-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="08340-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="08340-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="08340-105">Calcula a paridade de uma matriz de qubits num qubit alvo.</span><span class="sxs-lookup"><span data-stu-id="08340-105">Computes the parity of an array of qubits into a target qubit.</span></span>

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="08340-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="08340-106">Description</span></span>

<span data-ttu-id="08340-107">Se a matriz estiver inicialmente no estado $\ket{q_0} \ket{q_1} \cdots \ket{{q_{text{target}}}$, o estado final é dado por $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{text{target}}}.}}..}$..} \oplus \cdots \oplus q_0 \oplus q_{text{target}}}..}..}.".</span><span class="sxs-lookup"><span data-stu-id="08340-107">If the array is initially in the state $\ket{q_0} \ket{q_1} \cdots \ket{q_{\text{target}}}$, the final state is given by $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{\text{target}}}$.</span></span>

## <a name="input"></a><span data-ttu-id="08340-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="08340-108">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="08340-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="08340-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="08340-110">Matriz de qubits em que a paridade é calculada.</span><span class="sxs-lookup"><span data-stu-id="08340-110">Array of qubits on which the parity is computed.</span></span>


### <a name="targetqubit--qubit"></a><span data-ttu-id="08340-111">targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="08340-111">targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="08340-112">Qubit final em que a paridade de 'qubits' é XORed.</span><span class="sxs-lookup"><span data-stu-id="08340-112">Final qubit into which the parity of 'qubits' is XORed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="08340-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="08340-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="08340-114">Observações</span><span class="sxs-lookup"><span data-stu-id="08340-114">Remarks</span></span>

<span data-ttu-id="08340-115">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="08340-115">The following are equivalent:</span></span>

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

<span data-ttu-id="08340-116">e</span><span class="sxs-lookup"><span data-stu-id="08340-116">and</span></span>

```qsharp
ApplyCNOTChain(qs);
```