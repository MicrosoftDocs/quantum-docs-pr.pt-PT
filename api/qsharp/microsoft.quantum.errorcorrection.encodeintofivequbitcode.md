---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: Operação EncodeIntoFiveQubitCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: c9df4c5c98a78cae8b3af4597020d35469454153
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712400"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="1f67b-102">Operação EncodeIntoFiveQubitCode</span><span class="sxs-lookup"><span data-stu-id="1f67b-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="1f67b-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="1f67b-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="1f67b-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f67b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f67b-105">Codifica o código quântico ⟦5, 1, 3⟧.</span><span class="sxs-lookup"><span data-stu-id="1f67b-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="1f67b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1f67b-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="1f67b-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1f67b-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1f67b-108">Um qubit que representa um estado não codificado.</span><span class="sxs-lookup"><span data-stu-id="1f67b-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="1f67b-109">Esta matriz `Qubit[]` é de comprimento 1.</span><span class="sxs-lookup"><span data-stu-id="1f67b-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="1f67b-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1f67b-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1f67b-111">Um registo de qubits auxiliares que serão utilizados para representar o estado codificado.</span><span class="sxs-lookup"><span data-stu-id="1f67b-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="1f67b-112">Saída : [Registo Lógico](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="1f67b-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="1f67b-113">Uma variedade de qubits físicos do tipo `LogicalRegister` que armazenam o estado codificado.</span><span class="sxs-lookup"><span data-stu-id="1f67b-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f67b-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1f67b-114">See Also</span></span>

- [<span data-ttu-id="1f67b-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="1f67b-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)