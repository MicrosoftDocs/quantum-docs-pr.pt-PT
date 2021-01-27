---
uid: Microsoft.Quantum.Canon.RAll0
title: Operação RAll0
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: 660e6633df6750747963d41a6ff28a4fd4b02d4e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840268"
---
# <a name="rall0-operation"></a><span data-ttu-id="b1941-102">Operação RAll0</span><span class="sxs-lookup"><span data-stu-id="b1941-102">RAll0 operation</span></span>

<span data-ttu-id="b1941-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b1941-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b1941-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b1941-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b1941-105">Realiza uma operação de mudança de fase.</span><span class="sxs-lookup"><span data-stu-id="b1941-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="b1941-106">$R=\boldone-(1-e^{i \phi})\ket{0\cdots 0\cdots 0}\bra{0\cdots 0}$.</span><span class="sxs-lookup"><span data-stu-id="b1941-106">$R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b1941-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="b1941-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="b1941-108">fase : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b1941-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b1941-109">A fase $\phi$ aplicada ao estado $\ket{0\cdots 0}\bra{0\cdots 0}cdots 0}$.</span><span class="sxs-lookup"><span data-stu-id="b1941-109">The phase $\phi$ applied to state $\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="b1941-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b1941-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b1941-111">O registo cujo estado deve ser rodado por $R dólares.</span><span class="sxs-lookup"><span data-stu-id="b1941-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b1941-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1941-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b1941-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b1941-113">See Also</span></span>

- [<span data-ttu-id="b1941-114">Microsoft.Quantum.Canon.RAll1</span><span class="sxs-lookup"><span data-stu-id="b1941-114">Microsoft.Quantum.Canon.RAll1</span></span>](xref:Microsoft.Quantum.Canon.RAll1)