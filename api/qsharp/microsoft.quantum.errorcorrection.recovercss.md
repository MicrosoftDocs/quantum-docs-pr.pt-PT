---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: Operação RecoverCSS
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: 48d3cd3d5f6aea265fac2f50b913ab855a31accf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712204"
---
# <a name="recovercss-operation"></a><span data-ttu-id="5aa37-102">Operação RecoverCSS</span><span class="sxs-lookup"><span data-stu-id="5aa37-102">RecoverCSS operation</span></span>

<span data-ttu-id="5aa37-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="5aa37-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="5aa37-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5aa37-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5aa37-105">Executa uma única ronda de correção de erros por um código quântico descrito por um `CSS` tipo.</span><span class="sxs-lookup"><span data-stu-id="5aa37-105">Performs a single round of error correction by a quantum code described by a `CSS` type.</span></span>

```qsharp
operation RecoverCSS (code : Microsoft.Quantum.ErrorCorrection.CSS, fnX : Microsoft.Quantum.ErrorCorrection.RecoveryFn, fnZ : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="5aa37-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5aa37-106">Input</span></span>

### <a name="code--css"></a><span data-ttu-id="5aa37-107">código : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="5aa37-107">code : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="5aa37-108">Um código quântico de correção de erros CSS embalado como um `CSS` tipo descreve a codificação e descodificação dos dados quânticos e como as síndromes de erro devem ser medidas.</span><span class="sxs-lookup"><span data-stu-id="5aa37-108">A quantum CSS error-correcting code packaged as a `CSS` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fnx--recoveryfn"></a><span data-ttu-id="5aa37-109">fnX : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="5aa37-109">fnX : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="5aa37-110">A `RecoveryFn` que mapeia cada $X$ síndrome de erro para as `Pauli[]` operações que corrigem o erro detetado.</span><span class="sxs-lookup"><span data-stu-id="5aa37-110">A `RecoveryFn` that maps each $X$ error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="fnz--recoveryfn"></a><span data-ttu-id="5aa37-111">fnZ : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="5aa37-111">fnZ : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="5aa37-112">A `RecoveryFn` que mapeia cada $Z$ síndrome de erro para as `Pauli[]` operações que corrigem o erro detetado.</span><span class="sxs-lookup"><span data-stu-id="5aa37-112">A `RecoveryFn` that maps each $Z$ error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="5aa37-113">LogicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="5aa37-113">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="5aa37-114">Uma matriz de qubits onde o código estabilizador é definido.</span><span class="sxs-lookup"><span data-stu-id="5aa37-114">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5aa37-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5aa37-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="5aa37-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5aa37-116">See Also</span></span>

- [<span data-ttu-id="5aa37-117">Microsoft.Quantum.ErrorCorrection.CSS</span><span class="sxs-lookup"><span data-stu-id="5aa37-117">Microsoft.Quantum.ErrorCorrection.CSS</span></span>](xref:Microsoft.Quantum.ErrorCorrection.CSS)
- [<span data-ttu-id="5aa37-118">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="5aa37-118">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="5aa37-119">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="5aa37-119">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)