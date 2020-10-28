---
uid: Microsoft.Quantum.Canon.AndLadder
title: E Operação ELadder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: 05a0e8110539742501883fea75ac368d9946164d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718486"
---
# <a name="andladder-operation"></a><span data-ttu-id="d179a-102">E Operação ELadder</span><span class="sxs-lookup"><span data-stu-id="d179a-102">AndLadder operation</span></span>

<span data-ttu-id="d179a-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d179a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d179a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d179a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d179a-105">Executa uma "escada" controlada num registo de qubits-alvo.</span><span class="sxs-lookup"><span data-stu-id="d179a-105">Performs a controlled "AND ladder" on a register of target qubits.</span></span>

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="description"></a><span data-ttu-id="d179a-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="d179a-106">Description</span></span>

<span data-ttu-id="d179a-107">Esta operação aplica uma transformação descrita pelo seguinte mapeamento da base computacional, $$ \start{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \pontos, y \_ {n - 1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{ \_ y 1 \oplus (x \_ 1 \land x \_ 2), \dots, y \_ {n - 1} \oplus (x \_ 1 \land x \_ 2 \land \land \land \land \land x \_ {n - 1} }, \end{align} $$ where $\ket{x \_ 1, \dots, x \_ n}$ refere-se aos estados de base computacional de `controls` , e onde $\ket{y \_ 1, \dots, y \_ {n - 1}}$ refere-se aos estados de base computacional de `targets` .</span><span class="sxs-lookup"><span data-stu-id="d179a-107">This operation applies a transformation described by the following mapping of the computational basis, $$ \begin{align} \ket{x\_1, \dots, x\_n} \ket{y\_1, \dots, y\_{n - 1}} \mapsto \ket{x\_1, \dots, x\_n} \ket{ y\_1 \oplus (x\_1 \land x\_2), \dots, y\_{n - 1} \oplus (x\_1 \land x\_2 \land \cdots \land x\_{n - 1} }, \end{align} $$ where $\ket{x\_1, \dots, x\_n}$ refers to the computational basis states of `controls`, and where $\ket{y\_1, \dots, y\_{n - 1}}$ refers to the computational basis states of `targets`.</span></span>

## <a name="input"></a><span data-ttu-id="d179a-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="d179a-108">Input</span></span>

### <a name="ccnot--ccnotop"></a><span data-ttu-id="d179a-109">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="d179a-109">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="d179a-110">O portão CCNOT para usar para a construção.</span><span class="sxs-lookup"><span data-stu-id="d179a-110">The CCNOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="d179a-111">controlos: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d179a-111">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d179a-112">Um registo de qubits a utilizar como controlos para a escada e escada.</span><span class="sxs-lookup"><span data-stu-id="d179a-112">A register of qubits to be used as controls for the and ladder.</span></span>
<span data-ttu-id="d179a-113">Esta operação deixa estados de base computacional `controls` invariantes.</span><span class="sxs-lookup"><span data-stu-id="d179a-113">This operation leaves computational basis states of `controls` invariant.</span></span>
<span data-ttu-id="d179a-114">O comprimento `controls` deve ser de, pelo menos, 2, e deve ser igual a um mais o comprimento de `targets` .</span><span class="sxs-lookup"><span data-stu-id="d179a-114">The length of `controls` must be at least 2, and must be equal to one plus the length of `targets`.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="d179a-115">alvos : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d179a-115">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d179a-116">O comprimento `targets` deve ser de, pelo menos, 1 e igual ao comprimento de `controls` menos um.</span><span class="sxs-lookup"><span data-stu-id="d179a-116">The length of `targets` must be at least 1 and equal to the length of `controls` minus one.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d179a-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d179a-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d179a-118">Observações</span><span class="sxs-lookup"><span data-stu-id="d179a-118">Remarks</span></span>

- <span data-ttu-id="d179a-119">Usado como parte de <xref:microsoft.quantum.canon.applymulticontrolledc> e <xref:microsoft.quantum.canon.applymulticontrolledca> .</span><span class="sxs-lookup"><span data-stu-id="d179a-119">Used as a part of <xref:microsoft.quantum.canon.applymulticontrolledc> and <xref:microsoft.quantum.canon.applymulticontrolledca>.</span></span>
- <span data-ttu-id="d179a-120">Para a explicação e diagrama do circuito consulte a Figura 4.10, Secção 4.3 em Nielsen & Chuang.</span><span class="sxs-lookup"><span data-stu-id="d179a-120">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang.</span></span>

## <a name="references"></a><span data-ttu-id="d179a-121">Referências</span><span class="sxs-lookup"><span data-stu-id="d179a-121">References</span></span>

- [<span data-ttu-id="d179a-122">*Michael A. Nielsen , Isaac L. Chuang,* Quantum Computation e Quantum Information</span><span class="sxs-lookup"><span data-stu-id="d179a-122"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)