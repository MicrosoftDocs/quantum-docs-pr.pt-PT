---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: Preparar operação Do Estado dePauliEigen
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: b24852bb3a455a9fe04b3535156d0c3dfb1a7d12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193697"
---
# <a name="preparepaulieigenstate-operation"></a><span data-ttu-id="28ab6-102">Preparar operação Do Estado dePauliEigen</span><span class="sxs-lookup"><span data-stu-id="28ab6-102">PreparePauliEigenstate operation</span></span>

<span data-ttu-id="28ab6-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="28ab6-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="28ab6-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28ab6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28ab6-105">Prepara um qubit no eigenstate positivo de um determinado operador Pauli.</span><span class="sxs-lookup"><span data-stu-id="28ab6-105">Prepares a qubit in the positive eigenstate of a given Pauli operator.</span></span>
<span data-ttu-id="28ab6-106">Se o operador de identidade for dado, então o qubit é preparado no estado máximo misturado.</span><span class="sxs-lookup"><span data-stu-id="28ab6-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="28ab6-107">Description</span><span class="sxs-lookup"><span data-stu-id="28ab6-107">Description</span></span>

<span data-ttu-id="28ab6-108">Se o qubit estava inicialmente no estado $\ket$ {0} , esta operação prepara o qubit no estado de $+1$ de um determinado operador Pauli, ou, `PauliI` para, no estado maximamente misturado (ver <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="28ab6-108">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="28ab6-109">Se o qubit estava num estado diferente de $\ket {0} $, esta operação aplica os seguintes portões: $H$ para `PauliX` , $HS$ para `PauliY` , $I$ para e para `PauliZ` <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="28ab6-109">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

## <a name="input"></a><span data-ttu-id="28ab6-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="28ab6-110">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="28ab6-111">base : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="28ab6-111">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="28ab6-112">Um operador da Pauli $P$.</span><span class="sxs-lookup"><span data-stu-id="28ab6-112">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="28ab6-113">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="28ab6-113">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="28ab6-114">Um qubit para ser preparado.</span><span class="sxs-lookup"><span data-stu-id="28ab6-114">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="28ab6-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28ab6-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

