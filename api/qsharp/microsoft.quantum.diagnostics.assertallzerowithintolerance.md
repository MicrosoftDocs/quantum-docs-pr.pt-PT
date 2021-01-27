---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: AssertAllZeroWithinTolerance
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 281855ec79d280c903ebb4d05614081767840778
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830852"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="c1ba7-102">AssertAllZeroWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="c1ba7-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="c1ba7-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c1ba7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c1ba7-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c1ba7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c1ba7-105">Afirma que os qubits dados estão todos em estado de $\ket {0} $ até uma certa tolerância.</span><span class="sxs-lookup"><span data-stu-id="c1ba7-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c1ba7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c1ba7-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="c1ba7-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c1ba7-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c1ba7-108">Qubits que são afirmados como em estado de $\ket$ {0}</span><span class="sxs-lookup"><span data-stu-id="c1ba7-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="c1ba7-109">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c1ba7-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c1ba7-110">Precisão com que o estado deve estar em estado de $\ket {0} $</span><span class="sxs-lookup"><span data-stu-id="c1ba7-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="c1ba7-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c1ba7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c1ba7-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c1ba7-112">See Also</span></span>

- [<span data-ttu-id="c1ba7-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="c1ba7-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)