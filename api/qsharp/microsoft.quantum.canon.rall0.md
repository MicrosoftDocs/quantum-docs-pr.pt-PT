---
uid: Microsoft.Quantum.Canon.RAll0
title: Operação RAll0
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: bd1f796209a15f290315e55b872ae3b3e508a68b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205665"
---
# <a name="rall0-operation"></a><span data-ttu-id="69c6e-102">Operação RAll0</span><span class="sxs-lookup"><span data-stu-id="69c6e-102">RAll0 operation</span></span>

<span data-ttu-id="69c6e-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="69c6e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="69c6e-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69c6e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69c6e-105">Realiza uma operação de mudança de fase.</span><span class="sxs-lookup"><span data-stu-id="69c6e-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="69c6e-106">$R=\boldone-(1-e^{i \phi})\ket{0\cdots 0\cdots 0}\bra{0\cdots 0}$.</span><span class="sxs-lookup"><span data-stu-id="69c6e-106">$R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="69c6e-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="69c6e-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="69c6e-108">fase : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="69c6e-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="69c6e-109">A fase $\phi$ aplicada ao estado $\ket{0\cdots 0}\bra{0\cdots 0}cdots 0}$.</span><span class="sxs-lookup"><span data-stu-id="69c6e-109">The phase $\phi$ applied to state $\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="69c6e-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="69c6e-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="69c6e-111">O registo cujo estado deve ser rodado por $R dólares.</span><span class="sxs-lookup"><span data-stu-id="69c6e-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="69c6e-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69c6e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="69c6e-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="69c6e-113">See Also</span></span>

- [<span data-ttu-id="69c6e-114">Microsoft.Quantum.Canon.RAll1</span><span class="sxs-lookup"><span data-stu-id="69c6e-114">Microsoft.Quantum.Canon.RAll1</span></span>](xref:Microsoft.Quantum.Canon.RAll1)