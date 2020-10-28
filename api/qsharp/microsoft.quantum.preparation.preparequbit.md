---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: Preparar operaçãoQubit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 5f42bf26a8f9638ea88c035a18846050c3776b45
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723005"
---
# <a name="preparequbit-operation"></a><span data-ttu-id="3a0dd-102">Preparar operaçãoQubit</span><span class="sxs-lookup"><span data-stu-id="3a0dd-102">PrepareQubit operation</span></span>

<span data-ttu-id="3a0dd-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="3a0dd-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="3a0dd-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3a0dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3a0dd-105">Prepara um qubit no estado `Zero` +1 ( ) do operador Pauli.</span><span class="sxs-lookup"><span data-stu-id="3a0dd-105">Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator.</span></span>
<span data-ttu-id="3a0dd-106">Se o operador de identidade for dado, então o qubit é preparado no estado máximo misturado.</span><span class="sxs-lookup"><span data-stu-id="3a0dd-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

<span data-ttu-id="3a0dd-107">Se o qubit estava inicialmente no estado $\ket$ {0} , esta operação prepara o qubit no estado de $+1$ de um determinado operador Pauli, ou, `PauliI` para, no estado maximamente misturado (ver <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="3a0dd-107">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="3a0dd-108">Se o qubit estava num estado diferente de $\ket {0} $, esta operação aplica os seguintes portões: $H$ para `PauliX` , $HS$ para `PauliY` , $I$ para e para `PauliZ` <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="3a0dd-108">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="3a0dd-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="3a0dd-109">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="3a0dd-110">base : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="3a0dd-110">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="3a0dd-111">Um operador da Pauli $P$.</span><span class="sxs-lookup"><span data-stu-id="3a0dd-111">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="3a0dd-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3a0dd-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3a0dd-113">Um qubit para ser preparado.</span><span class="sxs-lookup"><span data-stu-id="3a0dd-113">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3a0dd-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3a0dd-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

