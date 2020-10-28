---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: AplicaçãoFermionicSWAP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 25dd91b200700d1474cf27bf1d0fa71d57f2e09b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718271"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="c2602-102">AplicaçãoFermionicSWAP</span><span class="sxs-lookup"><span data-stu-id="c2602-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="c2602-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c2602-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c2602-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c2602-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c2602-105">Aplica o Permuta Fermionic.</span><span class="sxs-lookup"><span data-stu-id="c2602-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="c2602-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="c2602-106">Description</span></span>

<span data-ttu-id="c2602-107">Isto essencialmente troca os qubits ao aplicar uma fase global de -1 se ambos os qubits forem 1s.</span><span class="sxs-lookup"><span data-stu-id="c2602-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="c2602-108">Preserva a anti-symmetrização dos orbitais.</span><span class="sxs-lookup"><span data-stu-id="c2602-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="c2602-109">Consulte  para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c2602-109">See  for more information.</span></span>

<span data-ttu-id="c2602-110">Esta operação é representada pelo operador unitário \start{align} f_{swap} \mathrel{:=} \start{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & \\ \\ 0 0 & 1 & 0 & 0 \\ \\ & 0 & 0 & -1 \\ \\ \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="c2602-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="c2602-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="c2602-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="c2602-112">Entrada</span><span class="sxs-lookup"><span data-stu-id="c2602-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="c2602-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c2602-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c2602-114">O primeiro qubit a ser trocado.</span><span class="sxs-lookup"><span data-stu-id="c2602-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="c2602-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c2602-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c2602-116">O segundo qubit a ser trocado.</span><span class="sxs-lookup"><span data-stu-id="c2602-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c2602-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c2602-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="c2602-118">Referências</span><span class="sxs-lookup"><span data-stu-id="c2602-118">References</span></span>

- [<span data-ttu-id="c2602-119">*Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan* , arXiv:1706.00023</span><span class="sxs-lookup"><span data-stu-id="c2602-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan* , arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="c2602-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c2602-120">See Also</span></span>

- [<span data-ttu-id="c2602-121">Microsoft.Quantum.Intrínseco.SWAP</span><span class="sxs-lookup"><span data-stu-id="c2602-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)