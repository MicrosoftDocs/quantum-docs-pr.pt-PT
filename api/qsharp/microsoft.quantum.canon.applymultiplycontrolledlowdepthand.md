---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: AplicarMultiplyControlledLowDepth E operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 6900f9b0f014fba28ae73a70f180f3e4696900cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717947"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="56caa-102">AplicarMultiplyControlledLowDepth E operação</span><span class="sxs-lookup"><span data-stu-id="56caa-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="56caa-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="56caa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="56caa-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="56caa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="56caa-105">Implementa um portão Toffoli controlado por vários controlos, assumindo que o qubit alvo é inicializado 0.</span><span class="sxs-lookup"><span data-stu-id="56caa-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="56caa-106">A operação adjacente pressupõe que o qubit-alvo será reposto para 0.</span><span class="sxs-lookup"><span data-stu-id="56caa-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="56caa-107">Requer uma profundidade Rz de 1, enquanto o número de qubits do ajudante são exponencials no número de qubits.</span><span class="sxs-lookup"><span data-stu-id="56caa-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="56caa-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="56caa-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="56caa-109">controlos: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="56caa-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="56caa-110">Qubits de controlo</span><span class="sxs-lookup"><span data-stu-id="56caa-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="56caa-111">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="56caa-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="56caa-112">Qubit alvo</span><span class="sxs-lookup"><span data-stu-id="56caa-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="56caa-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56caa-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

