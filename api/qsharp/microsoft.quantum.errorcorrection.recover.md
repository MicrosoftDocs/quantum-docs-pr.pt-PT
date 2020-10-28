---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: Operação de recuperação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: a659399f51794a4edc1d2ff43da84e46797103fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712207"
---
# <a name="recover-operation"></a><span data-ttu-id="e98fb-102">Operação de recuperação</span><span class="sxs-lookup"><span data-stu-id="e98fb-102">Recover operation</span></span>

<span data-ttu-id="e98fb-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e98fb-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e98fb-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e98fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e98fb-105">Executa uma única ronda de correção de erros por um código quântico descrito por um `QECC` tipo.</span><span class="sxs-lookup"><span data-stu-id="e98fb-105">Performs a single round of error correction by a quantum code described by a `QECC` type.</span></span>

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="e98fb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e98fb-106">Input</span></span>

### <a name="code--qecc"></a><span data-ttu-id="e98fb-107">código : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="e98fb-107">code : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="e98fb-108">Um código de correção de erros quânticos embalado como um `QECC` tipo descreve a codificação e descodificação dos dados quânticos e como as síndromes de erro devem ser medidas.</span><span class="sxs-lookup"><span data-stu-id="e98fb-108">A quantum error-correcting code packaged as a `QECC` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fn--recoveryfn"></a><span data-ttu-id="e98fb-109">fn : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="e98fb-109">fn : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="e98fb-110">A `RecoveryFn` que mapeia cada síndrome de erro para as `Pauli[]` operações que corrigem o erro detetado.</span><span class="sxs-lookup"><span data-stu-id="e98fb-110">A `RecoveryFn` that maps each error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="e98fb-111">LogicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="e98fb-111">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="e98fb-112">Uma matriz de qubits onde o código estabilizador é definido.</span><span class="sxs-lookup"><span data-stu-id="e98fb-112">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e98fb-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e98fb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e98fb-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e98fb-114">See Also</span></span>

- [<span data-ttu-id="e98fb-115">Microsoft.Quantum.ErrorCorrection.QECC</span><span class="sxs-lookup"><span data-stu-id="e98fb-115">Microsoft.Quantum.ErrorCorrection.QECC</span></span>](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [<span data-ttu-id="e98fb-116">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="e98fb-116">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="e98fb-117">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="e98fb-117">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)