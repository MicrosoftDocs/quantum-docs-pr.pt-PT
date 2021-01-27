---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: AplicarMultiplyControlledAnd operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: ac3972287d55ed2df85e1d88510918cc5202c711
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844847"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="83a3d-102">AplicarMultiplyControlledAnd operação</span><span class="sxs-lookup"><span data-stu-id="83a3d-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="83a3d-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="83a3d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="83a3d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="83a3d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="83a3d-105">Implementa um portão Toffoli controlado por vários controlos, assumindo que o qubit alvo é inicializado 0.</span><span class="sxs-lookup"><span data-stu-id="83a3d-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="83a3d-106">A operação adjacente pressupõe que o qubit-alvo será reposto para 0.</span><span class="sxs-lookup"><span data-stu-id="83a3d-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="83a3d-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="83a3d-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="83a3d-108">controlos: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="83a3d-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="83a3d-109">Qubits de controlo</span><span class="sxs-lookup"><span data-stu-id="83a3d-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="83a3d-110">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="83a3d-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="83a3d-111">Qubit alvo</span><span class="sxs-lookup"><span data-stu-id="83a3d-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="83a3d-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="83a3d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

