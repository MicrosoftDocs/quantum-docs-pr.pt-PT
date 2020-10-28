---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: operação _prepareEntangledState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 384dad5905cec50b500028e1bc352a742122b299
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713131"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="42d10-102">operação _prepareEntangledState</span><span class="sxs-lookup"><span data-stu-id="42d10-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="42d10-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="42d10-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="42d10-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="42d10-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="42d10-105">Tendo em conta dois registos, prepara o estado máximo emaranhado entre cada par de qubits nos respetivos registos.</span><span class="sxs-lookup"><span data-stu-id="42d10-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="42d10-106">Todos os qubits devem começar no estado de 0⟩.</span><span class="sxs-lookup"><span data-stu-id="42d10-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="42d10-107">O resultado é que os pares correspondentes de qubits de cada registo estão no $\bra{\beta_ {00} }\ket{\beta_ {00} }$.</span><span class="sxs-lookup"><span data-stu-id="42d10-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="42d10-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="42d10-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="42d10-109">esquerda : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="42d10-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="42d10-110">Um qubit array no estado $\ket{0\cdots 0}$</span><span class="sxs-lookup"><span data-stu-id="42d10-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="42d10-111">direita: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="42d10-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="42d10-112">Um qubit array no estado $\ket{0\cdots 0}$</span><span class="sxs-lookup"><span data-stu-id="42d10-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="42d10-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42d10-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

