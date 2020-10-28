---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: Aplicam a operação ApplyMultiControlledCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 5662efe0dc6f665206b8773596bf885ce631413c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717961"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="a826a-102">Aplicam a operação ApplyMultiControlledCA</span><span class="sxs-lookup"><span data-stu-id="a826a-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="a826a-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a826a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a826a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a826a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a826a-105">Aplica uma versão controlada por multiplicação de uma operação controlada por singingly.</span><span class="sxs-lookup"><span data-stu-id="a826a-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="a826a-106">O modificador `CA` indica que a operação de um único qubit é controlável e adjacente.</span><span class="sxs-lookup"><span data-stu-id="a826a-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a826a-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="a826a-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit-adj"></a><span data-ttu-id="a826a-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="a826a-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a826a-109">Uma operação controlada num único qubit.</span><span class="sxs-lookup"><span data-stu-id="a826a-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="a826a-110">O primeiro qubit no argumento da operação assumido como um controlo e os restantes são assumidos como qubits alvo.</span><span class="sxs-lookup"><span data-stu-id="a826a-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="a826a-111">`ApplyMultiControlled` sempre chama `singlyControlledOp` com um argumento de comprimento pelo menos 1.</span><span class="sxs-lookup"><span data-stu-id="a826a-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="a826a-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="a826a-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="a826a-113">O portão NÃO controlado controlado para a construção.</span><span class="sxs-lookup"><span data-stu-id="a826a-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="a826a-114">controlos: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a826a-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a826a-115">Os qubits que `singlyControlledOp` devem ser controlados.</span><span class="sxs-lookup"><span data-stu-id="a826a-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="a826a-116">O comprimento `controls` deve ser de, pelo menos, 1.</span><span class="sxs-lookup"><span data-stu-id="a826a-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="a826a-117">alvos : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a826a-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a826a-118">O alvo qubits que `singlyControlledOp` atua.</span><span class="sxs-lookup"><span data-stu-id="a826a-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a826a-119">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a826a-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a826a-120">Observações</span><span class="sxs-lookup"><span data-stu-id="a826a-120">Remarks</span></span>

<span data-ttu-id="a826a-121">Esta operação utiliza apenas qubits de ancilla limpos.</span><span class="sxs-lookup"><span data-stu-id="a826a-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="a826a-122">Para a explicação e diagrama do circuito ver Figura 4.10, Secção 4.3 em Nielsen & Chuang</span><span class="sxs-lookup"><span data-stu-id="a826a-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="a826a-123">Referências</span><span class="sxs-lookup"><span data-stu-id="a826a-123">References</span></span>

- [<span data-ttu-id="a826a-124">*Michael A. Nielsen , Isaac L. Chuang,* Quantum Computation e Quantum Information</span><span class="sxs-lookup"><span data-stu-id="a826a-124"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="a826a-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a826a-125">See Also</span></span>

- [<span data-ttu-id="a826a-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="a826a-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)