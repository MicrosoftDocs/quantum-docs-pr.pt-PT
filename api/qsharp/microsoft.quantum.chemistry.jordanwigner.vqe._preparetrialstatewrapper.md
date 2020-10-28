---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: operação _prepareTrialStateWrapper
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: bfd7b9ce8e8b2c8f322d676c640f8c2488655516
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713761"
---
# <a name="_preparetrialstatewrapper-operation"></a><span data-ttu-id="1b748-102">operação _prepareTrialStateWrapper</span><span class="sxs-lookup"><span data-stu-id="1b748-102">_prepareTrialStateWrapper operation</span></span>

<span data-ttu-id="1b748-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="1b748-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="1b748-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b748-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b748-105">Invólucro privado em torno do PrepareTrialState para torná-lo compatível com EstimateFrequencyA definindo um adjacente.</span><span class="sxs-lookup"><span data-stu-id="1b748-105">Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint.</span></span>
<span data-ttu-id="1b748-106">Estima-se Quea tem uma característica de emulação incorporada ao visar o QuantumSimulator, que acelera a sua execução.</span><span class="sxs-lookup"><span data-stu-id="1b748-106">EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.</span></span>

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1b748-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="1b748-107">Input</span></span>

### <a name="inputstate--intjordanwignerinputstate"></a><span data-ttu-id="1b748-108">inputState :[(Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span><span class="sxs-lookup"><span data-stu-id="1b748-108">inputState : ([Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span></span>

<span data-ttu-id="1b748-109">A entrada Jordan-Wigner necessária para que o PrepareTrialState possa ser executado.</span><span class="sxs-lookup"><span data-stu-id="1b748-109">The Jordan-Wigner input required for PrepareTrialState to run.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="1b748-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1b748-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1b748-111">Um registo de qubits.</span><span class="sxs-lookup"><span data-stu-id="1b748-111">A qubit register.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1b748-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1b748-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

