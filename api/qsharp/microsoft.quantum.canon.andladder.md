---
uid: Microsoft.Quantum.Canon.AndLadder
title: E Operação ELadder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: d44c462c7a9fc9521bdecfe2ca7f607e90482baf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845229"
---
# <a name="andladder-operation"></a><span data-ttu-id="52367-102">E Operação ELadder</span><span class="sxs-lookup"><span data-stu-id="52367-102">AndLadder operation</span></span>

<span data-ttu-id="52367-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="52367-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="52367-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52367-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="52367-105">Executa uma "escada" controlada num registo de qubits-alvo.</span><span class="sxs-lookup"><span data-stu-id="52367-105">Performs a controlled "AND ladder" on a register of target qubits.</span></span>

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="52367-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="52367-106">Description</span></span>

<span data-ttu-id="52367-107">Esta operação aplica uma transformação descrita pelo seguinte mapeamento da base computacional, $$ \start{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \pontos, y \_ {n - 1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{ \_ y 1 \oplus (x \_ 1 \land x \_ 2), \dots, y \_ {n - 1} \oplus (x \_ 1 \land x \_ 2 \land \land x \_ {n - 1} }, \end{align} $$ where $\ket{x \_ 1, \dots, x \_ n}$ refere-se aos estados de base computacional de `controls` , e onde $\ket{y \_ 1, \dots, y \_ {n - 1}}$ refere-se aos estados de base computacional de `targets` .</span><span class="sxs-lookup"><span data-stu-id="52367-107">This operation applies a transformation described by the following mapping of the computational basis, $$ \begin{align} \ket{x\_1, \dots, x\_n} \ket{y\_1, \dots, y\_{n - 1}} \mapsto \ket{x\_1, \dots, x\_n} \ket{ y\_1 \oplus (x\_1 \land x\_2), \dots, y\_{n - 1} \oplus (x\_1 \land x\_2 \land \cdots \land x\_{n - 1} }, \end{align} $$ where $\ket{x\_1, \dots, x\_n}$ refers to the computational basis states of `controls`, and where $\ket{y\_1, \dots, y\_{n - 1}}$ refers to the computational basis states of `targets`.</span></span>

## <a name="input"></a><span data-ttu-id="52367-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="52367-108">Input</span></span>

### <a name="ccnot--ccnotop"></a><span data-ttu-id="52367-109">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="52367-109">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="52367-110">O portão CCNOT para usar para a construção.</span><span class="sxs-lookup"><span data-stu-id="52367-110">The CCNOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="52367-111">controlos: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="52367-111">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="52367-112">Um registo de qubits a utilizar como controlos para a escada e escada.</span><span class="sxs-lookup"><span data-stu-id="52367-112">A register of qubits to be used as controls for the and ladder.</span></span>
<span data-ttu-id="52367-113">Esta operação deixa estados de base computacional `controls` invariantes.</span><span class="sxs-lookup"><span data-stu-id="52367-113">This operation leaves computational basis states of `controls` invariant.</span></span>
<span data-ttu-id="52367-114">O comprimento `controls` deve ser de, pelo menos, 2, e deve ser igual a um mais o comprimento de `targets` .</span><span class="sxs-lookup"><span data-stu-id="52367-114">The length of `controls` must be at least 2, and must be equal to one plus the length of `targets`.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="52367-115">alvos : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="52367-115">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="52367-116">O comprimento `targets` deve ser de, pelo menos, 1 e igual ao comprimento de `controls` menos um.</span><span class="sxs-lookup"><span data-stu-id="52367-116">The length of `targets` must be at least 1 and equal to the length of `controls` minus one.</span></span>



## <a name="output--unit"></a><span data-ttu-id="52367-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="52367-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="52367-118">Observações</span><span class="sxs-lookup"><span data-stu-id="52367-118">Remarks</span></span>

- <span data-ttu-id="52367-119">Usado como parte de <xref:microsoft.quantum.canon.applymulticontrolledc> e <xref:microsoft.quantum.canon.applymulticontrolledca> .</span><span class="sxs-lookup"><span data-stu-id="52367-119">Used as a part of <xref:microsoft.quantum.canon.applymulticontrolledc> and <xref:microsoft.quantum.canon.applymulticontrolledca>.</span></span>
- <span data-ttu-id="52367-120">Para a explicação e diagrama do circuito consulte a Figura 4.10, Secção 4.3 em Nielsen & Chuang.</span><span class="sxs-lookup"><span data-stu-id="52367-120">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang.</span></span>

## <a name="references"></a><span data-ttu-id="52367-121">Referências</span><span class="sxs-lookup"><span data-stu-id="52367-121">References</span></span>

- [<span data-ttu-id="52367-122">*Michael A. Nielsen , Isaac L. Chuang,* Quantum Computation e Quantum Information</span><span class="sxs-lookup"><span data-stu-id="52367-122"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)