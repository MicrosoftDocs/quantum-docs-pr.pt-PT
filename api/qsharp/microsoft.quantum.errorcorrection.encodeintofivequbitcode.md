---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: Operação EncodeIntoFiveQubitCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 1bccf46453ad34199dcebc5bcff693359fe2254c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826327"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="1c44b-102">Operação EncodeIntoFiveQubitCode</span><span class="sxs-lookup"><span data-stu-id="1c44b-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="1c44b-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="1c44b-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="1c44b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1c44b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1c44b-105">Codifica o código quântico ⟦5, 1, 3⟧.</span><span class="sxs-lookup"><span data-stu-id="1c44b-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="1c44b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1c44b-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="1c44b-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1c44b-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1c44b-108">Um qubit que representa um estado não codificado.</span><span class="sxs-lookup"><span data-stu-id="1c44b-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="1c44b-109">Esta matriz `Qubit[]` é de comprimento 1.</span><span class="sxs-lookup"><span data-stu-id="1c44b-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="1c44b-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1c44b-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1c44b-111">Um registo de qubits auxiliares que serão utilizados para representar o estado codificado.</span><span class="sxs-lookup"><span data-stu-id="1c44b-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="1c44b-112">Saída : [Registo Lógico](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="1c44b-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="1c44b-113">Uma variedade de qubits físicos do tipo `LogicalRegister` que armazenam o estado codificado.</span><span class="sxs-lookup"><span data-stu-id="1c44b-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c44b-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1c44b-114">See Also</span></span>

- [<span data-ttu-id="1c44b-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="1c44b-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)