---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: Preparar Operação Do Estado-ParparseMultiConfigurational
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 4d39be70c48ed49a1eec410ed6f8e5081dc1e8ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224773"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a><span data-ttu-id="7eb56-102">Preparar Operação Do Estado-ParparseMultiConfigurational</span><span class="sxs-lookup"><span data-stu-id="7eb56-102">PrepareSparseMultiConfigurationalState operation</span></span>

<span data-ttu-id="7eb56-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="7eb56-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="7eb56-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7eb56-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="7eb56-105">Preparação estatal multi-configuracional escassa do estado experimental adicionando excitações ao estado experimental inicial.</span><span class="sxs-lookup"><span data-stu-id="7eb56-105">Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.</span></span>

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7eb56-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7eb56-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="7eb56-107">prescrição inicial: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="7eb56-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7eb56-108">Unitário para preparar o estado inicial do julgamento.</span><span class="sxs-lookup"><span data-stu-id="7eb56-108">Unitary to prepare initial trial state.</span></span>


### <a name="excitations--jordanwignerinputstate"></a><span data-ttu-id="7eb56-109">excitações : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="7eb56-109">excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="7eb56-110">Excitações do estado experimental inicial representadas pela amplitude da excitação e os índices qubit sobre os atos de excitação.</span><span class="sxs-lookup"><span data-stu-id="7eb56-110">Excitations of initial trial state represented by the amplitude of the excitation and the qubit indices the excitation acts on.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="7eb56-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7eb56-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7eb56-112">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="7eb56-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7eb56-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7eb56-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

