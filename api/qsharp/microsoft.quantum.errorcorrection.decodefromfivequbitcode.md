---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromFiveQubitCode
title: Descodificar OperaçãoFromFiveQubitCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromFiveQubitCode
qsharp.summary: Decodes the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 9b4580cb88f03a16e3c9c55511d0ec5968cc636f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853160"
---
# <a name="decodefromfivequbitcode-operation"></a><span data-ttu-id="2d989-102">Descodificar OperaçãoFromFiveQubitCode</span><span class="sxs-lookup"><span data-stu-id="2d989-102">DecodeFromFiveQubitCode operation</span></span>

<span data-ttu-id="2d989-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="2d989-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="2d989-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d989-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d989-105">Descodifica o código quântico ⟦5, 1, 3⟧.</span><span class="sxs-lookup"><span data-stu-id="2d989-105">Decodes the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation DecodeFromFiveQubitCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="2d989-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2d989-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="2d989-107">LogicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="2d989-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="2d989-108">Uma série de qubits que representam o estado lógico codificado do código 5-qubit.</span><span class="sxs-lookup"><span data-stu-id="2d989-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="2d989-109">Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="2d989-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="2d989-110">Uma matriz qubit de comprimento 1 representando o estado não codificado no primeiro parâmetro, juntamente com qubits auxiliares no segundo parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2d989-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d989-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2d989-111">See Also</span></span>

- [<span data-ttu-id="2d989-112">Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="2d989-112">Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder)
- [<span data-ttu-id="2d989-113">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="2d989-113">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)