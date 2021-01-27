---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: AplicarMultiplyControlledLowDepth E operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 0ad4b6eabcbbb63751489dd92a13a6673c1ae6b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841665"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="f7fa9-102">AplicarMultiplyControlledLowDepth E operação</span><span class="sxs-lookup"><span data-stu-id="f7fa9-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="f7fa9-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f7fa9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f7fa9-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f7fa9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f7fa9-105">Implementa um portão Toffoli controlado por vários controlos, assumindo que o qubit alvo é inicializado 0.</span><span class="sxs-lookup"><span data-stu-id="f7fa9-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="f7fa9-106">A operação adjacente pressupõe que o qubit-alvo será reposto para 0.</span><span class="sxs-lookup"><span data-stu-id="f7fa9-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="f7fa9-107">Requer uma profundidade Rz de 1, enquanto o número de qubits do ajudante são exponencials no número de qubits.</span><span class="sxs-lookup"><span data-stu-id="f7fa9-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="f7fa9-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="f7fa9-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="f7fa9-109">controlos: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f7fa9-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f7fa9-110">Qubits de controlo</span><span class="sxs-lookup"><span data-stu-id="f7fa9-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f7fa9-111">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f7fa9-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f7fa9-112">Qubit alvo</span><span class="sxs-lookup"><span data-stu-id="f7fa9-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7fa9-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7fa9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

