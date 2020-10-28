---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: AplicarMultiplyControlledAnd operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: feca28d394e4af31eb4ffe737111d00ede45e27e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717958"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="0c44e-102">AplicarMultiplyControlledAnd operação</span><span class="sxs-lookup"><span data-stu-id="0c44e-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="0c44e-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0c44e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0c44e-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c44e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c44e-105">Implementa um portão Toffoli controlado por vários controlos, assumindo que o qubit alvo é inicializado 0.</span><span class="sxs-lookup"><span data-stu-id="0c44e-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="0c44e-106">A operação adjacente pressupõe que o qubit-alvo será reposto para 0.</span><span class="sxs-lookup"><span data-stu-id="0c44e-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="0c44e-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="0c44e-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="0c44e-108">controlos: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0c44e-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0c44e-109">Qubits de controlo</span><span class="sxs-lookup"><span data-stu-id="0c44e-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="0c44e-110">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0c44e-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0c44e-111">Qubit alvo</span><span class="sxs-lookup"><span data-stu-id="0c44e-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="0c44e-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0c44e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

