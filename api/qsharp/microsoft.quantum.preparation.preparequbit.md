---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: Preparar operaçãoQubit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  > [!WARNING]

  > PrepareQubit has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.


  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: e6a88ccf4c01b2f0a7344e3823b2748790cf9650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854326"
---
# <a name="preparequbit-operation"></a><span data-ttu-id="e37eb-102">Preparar operaçãoQubit</span><span class="sxs-lookup"><span data-stu-id="e37eb-102">PrepareQubit operation</span></span>

<span data-ttu-id="e37eb-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e37eb-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e37eb-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e37eb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="e37eb-105">PrepareQubit foi depreciado.</span><span class="sxs-lookup"><span data-stu-id="e37eb-105">PrepareQubit has been deprecated.</span></span> <span data-ttu-id="e37eb-106">Por favor, use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="e37eb-106">Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.</span></span>

<span data-ttu-id="e37eb-107">Prepara um qubit no estado `Zero` +1 ( ) do operador Pauli.</span><span class="sxs-lookup"><span data-stu-id="e37eb-107">Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator.</span></span>
<span data-ttu-id="e37eb-108">Se o operador de identidade for dado, então o qubit é preparado no estado máximo misturado.</span><span class="sxs-lookup"><span data-stu-id="e37eb-108">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

<span data-ttu-id="e37eb-109">Se o qubit estava inicialmente no estado $\ket$ {0} , esta operação prepara o qubit no estado de $+1$ de um determinado operador Pauli, ou, `PauliI` para, no estado maximamente misturado (ver <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="e37eb-109">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="e37eb-110">Se o qubit estava num estado diferente de $\ket {0} $, esta operação aplica os seguintes portões: $H$ para `PauliX` , $HS$ para `PauliY` , $I$ para e para `PauliZ` <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="e37eb-110">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e37eb-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="e37eb-111">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="e37eb-112">base : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="e37eb-112">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="e37eb-113">Um operador da Pauli $P$.</span><span class="sxs-lookup"><span data-stu-id="e37eb-113">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="e37eb-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e37eb-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e37eb-115">Um qubit para ser preparado.</span><span class="sxs-lookup"><span data-stu-id="e37eb-115">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e37eb-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e37eb-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

