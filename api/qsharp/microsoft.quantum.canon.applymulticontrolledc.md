---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: AplicarOperaçãoMultiControlledC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 2d5703eed3a3b6e611ae7c993febf018fcb148b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218415"
---
# <a name="applymulticontrolledc-operation"></a><span data-ttu-id="7ab98-102">AplicarOperaçãoMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="7ab98-102">ApplyMultiControlledC operation</span></span>

<span data-ttu-id="7ab98-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7ab98-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7ab98-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7ab98-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7ab98-105">Aplica uma versão controlada por multiplicação de uma operação controlada por singingly.</span><span class="sxs-lookup"><span data-stu-id="7ab98-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="7ab98-106">O modificador `C` indica que a operação de um único qubit é controlável.</span><span class="sxs-lookup"><span data-stu-id="7ab98-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="7ab98-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="7ab98-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit"></a><span data-ttu-id="7ab98-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="7ab98-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7ab98-109">Uma operação controlada num único qubit.</span><span class="sxs-lookup"><span data-stu-id="7ab98-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="7ab98-110">O primeiro qubit no argumento da operação é assumido como um controlo e os restantes são assumidos como qubits alvo.</span><span class="sxs-lookup"><span data-stu-id="7ab98-110">The first qubit in the argument of the operation is assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="7ab98-111">`ApplyMultiControlled` sempre chama `singlyControlledOp` com um argumento de comprimento pelo menos 1.</span><span class="sxs-lookup"><span data-stu-id="7ab98-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="7ab98-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="7ab98-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="7ab98-113">O portão NÃO controlado controlado para a construção.</span><span class="sxs-lookup"><span data-stu-id="7ab98-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="7ab98-114">controlos: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7ab98-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7ab98-115">Os qubits que `singlyControlledOp` devem ser controlados.</span><span class="sxs-lookup"><span data-stu-id="7ab98-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="7ab98-116">O comprimento `controls` deve ser de, pelo menos, 1.</span><span class="sxs-lookup"><span data-stu-id="7ab98-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="7ab98-117">alvos : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7ab98-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7ab98-118">O alvo qubits que `singlyControlledOp` atua.</span><span class="sxs-lookup"><span data-stu-id="7ab98-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7ab98-119">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7ab98-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7ab98-120">Observações</span><span class="sxs-lookup"><span data-stu-id="7ab98-120">Remarks</span></span>

<span data-ttu-id="7ab98-121">Esta operação utiliza apenas qubits de ancilla limpos.</span><span class="sxs-lookup"><span data-stu-id="7ab98-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="7ab98-122">Para a explicação e diagrama do circuito ver Figura 4.10, Secção 4.3 em Nielsen & Chuang</span><span class="sxs-lookup"><span data-stu-id="7ab98-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="7ab98-123">Referências</span><span class="sxs-lookup"><span data-stu-id="7ab98-123">References</span></span>

- [<span data-ttu-id="7ab98-124">*Michael A. Nielsen , Isaac L. Chuang,* Quantum Computation e Quantum Information</span><span class="sxs-lookup"><span data-stu-id="7ab98-124"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="7ab98-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7ab98-125">See Also</span></span>

- [<span data-ttu-id="7ab98-126">Microsoft.Quantum.Canon.ApplyMultiControlledCA</span><span class="sxs-lookup"><span data-stu-id="7ab98-126">Microsoft.Quantum.Canon.ApplyMultiControlledCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)