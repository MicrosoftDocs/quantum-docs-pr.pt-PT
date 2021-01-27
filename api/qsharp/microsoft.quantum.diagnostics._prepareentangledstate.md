---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: operação _prepareEntangledState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 5a74978a536a92dafae0b532805bd8e8ae1c888e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830976"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="5b1e5-102">operação _prepareEntangledState</span><span class="sxs-lookup"><span data-stu-id="5b1e5-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="5b1e5-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5b1e5-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5b1e5-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5b1e5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5b1e5-105">Tendo em conta dois registos, prepara o estado máximo emaranhado entre cada par de qubits nos respetivos registos.</span><span class="sxs-lookup"><span data-stu-id="5b1e5-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="5b1e5-106">Todos os qubits devem começar no estado |0⟩.</span><span class="sxs-lookup"><span data-stu-id="5b1e5-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="5b1e5-107">O resultado é que os pares correspondentes de qubits de cada registo estão no $\bra{\beta_ {00} }\ket{\beta_ {00} }$.</span><span class="sxs-lookup"><span data-stu-id="5b1e5-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5b1e5-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="5b1e5-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="5b1e5-109">esquerda : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5b1e5-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5b1e5-110">Um qubit array no estado $\ket{0\cdots 0}$</span><span class="sxs-lookup"><span data-stu-id="5b1e5-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="5b1e5-111">direita: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5b1e5-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5b1e5-112">Um qubit array no estado $\ket{0\cdots 0}$</span><span class="sxs-lookup"><span data-stu-id="5b1e5-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="5b1e5-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5b1e5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

