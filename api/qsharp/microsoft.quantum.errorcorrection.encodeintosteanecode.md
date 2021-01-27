---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: Operação EncodeIntoSteaneCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 2f65423a17dafadd1f9f10a07335150dfc8bf886
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826194"
---
# <a name="encodeintosteanecode-operation"></a><span data-ttu-id="c5d40-102">Operação EncodeIntoSteaneCode</span><span class="sxs-lookup"><span data-stu-id="c5d40-102">EncodeIntoSteaneCode operation</span></span>

<span data-ttu-id="c5d40-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c5d40-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c5d40-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5d40-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5d40-105">Uma operação de codificação que mapeia um registo quântico não codificado para um registo quântico codificado sob o código quântico de 1, 3 ⟧ ⟦.</span><span class="sxs-lookup"><span data-stu-id="c5d40-105">An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="c5d40-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c5d40-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="c5d40-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c5d40-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c5d40-108">Um registo qubit que detém um estado quântico não codificado</span><span class="sxs-lookup"><span data-stu-id="c5d40-108">A qubit register which holds the an unencoded quantum state</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="c5d40-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c5d40-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c5d40-110">Um registo qubit que é inicialmente zero e que é adicionado ao sistema quântico para que uma operação de codificação possa ser realizada</span><span class="sxs-lookup"><span data-stu-id="c5d40-110">A qubit register which is initially zero and which gets added to the quantum system so that an encoding operation can be performed</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="c5d40-111">Saída : [Registo Lógico](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="c5d40-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="c5d40-112">Um registo quântico que mantém o estado após a aplicação do codificar Steane</span><span class="sxs-lookup"><span data-stu-id="c5d40-112">A quantum register holding the state after the Steane encoder has been applied</span></span>

## <a name="see-also"></a><span data-ttu-id="c5d40-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c5d40-113">See Also</span></span>

- [<span data-ttu-id="c5d40-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="c5d40-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="c5d40-115">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="c5d40-115">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)