---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: AssertAllZeroWithinTolerance
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 5e401904086323fabef7914d34463f50e4c38862
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713044"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="ff9ec-102">AssertAllZeroWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="ff9ec-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="ff9ec-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ff9ec-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ff9ec-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ff9ec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ff9ec-105">Afirma que os qubits dados estão todos em estado de $\ket {0} $ até uma certa tolerância.</span><span class="sxs-lookup"><span data-stu-id="ff9ec-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="ff9ec-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ff9ec-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="ff9ec-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ff9ec-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ff9ec-108">Qubits que são afirmados como em estado de $\ket$ {0}</span><span class="sxs-lookup"><span data-stu-id="ff9ec-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="ff9ec-109">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ff9ec-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ff9ec-110">Precisão com que o estado deve estar em estado de $\ket {0} $</span><span class="sxs-lookup"><span data-stu-id="ff9ec-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="ff9ec-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff9ec-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ff9ec-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ff9ec-112">See Also</span></span>

- [<span data-ttu-id="ff9ec-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="ff9ec-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)