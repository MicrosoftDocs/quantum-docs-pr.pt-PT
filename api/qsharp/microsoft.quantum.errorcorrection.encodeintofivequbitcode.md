---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: Operação EncodeIntoFiveQubitCode
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 70e52b7440dca1fa8761db13d6187cb6bf8c43c4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200990"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="a927f-102">Operação EncodeIntoFiveQubitCode</span><span class="sxs-lookup"><span data-stu-id="a927f-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="a927f-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="a927f-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="a927f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a927f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a927f-105">Codifica o código quântico ⟦5, 1, 3⟧.</span><span class="sxs-lookup"><span data-stu-id="a927f-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="a927f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a927f-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="a927f-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a927f-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a927f-108">Um qubit que representa um estado não codificado.</span><span class="sxs-lookup"><span data-stu-id="a927f-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="a927f-109">Esta matriz `Qubit[]` é de comprimento 1.</span><span class="sxs-lookup"><span data-stu-id="a927f-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="a927f-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a927f-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a927f-111">Um registo de qubits auxiliares que serão utilizados para representar o estado codificado.</span><span class="sxs-lookup"><span data-stu-id="a927f-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="a927f-112">Saída : [Registo Lógico](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="a927f-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="a927f-113">Uma variedade de qubits físicos do tipo `LogicalRegister` que armazenam o estado codificado.</span><span class="sxs-lookup"><span data-stu-id="a927f-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="a927f-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a927f-114">See Also</span></span>

- [<span data-ttu-id="a927f-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="a927f-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)