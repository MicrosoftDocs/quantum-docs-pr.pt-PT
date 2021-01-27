---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: Preparar Operação Estado DeEnangled
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 9bf42131860b9fe9bd223ade32f95ec747abefe8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854373"
---
# <a name="prepareentangledstate-operation"></a><span data-ttu-id="df1be-102">Preparar Operação Estado DeEnangled</span><span class="sxs-lookup"><span data-stu-id="df1be-102">PrepareEntangledState operation</span></span>

<span data-ttu-id="df1be-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="df1be-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="df1be-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="df1be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="df1be-105">Em pares envolve dois registos qubit.</span><span class="sxs-lookup"><span data-stu-id="df1be-105">Pairwise entangles two qubit registers.</span></span>

<span data-ttu-id="df1be-106">Ou seja, tendo em conta dois registos, prepara o estado máximo emaranhado $\frac {1} {\sqrt {2} } \left(\ket {00} + \ket {11} \right)$ entre cada par de qubits nos respetivos registos, assumindo que cada registo começa no estado $\ket{0\cdots 0}$</span><span class="sxs-lookup"><span data-stu-id="df1be-106">That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.</span></span>

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="df1be-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="df1be-107">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="df1be-108">esquerda : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="df1be-108">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="df1be-109">Um qubit array no estado $\ket{0\cdots 0}$</span><span class="sxs-lookup"><span data-stu-id="df1be-109">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="df1be-110">direita: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="df1be-110">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="df1be-111">Um qubit array no estado $\ket{0\cdots 0}$</span><span class="sxs-lookup"><span data-stu-id="df1be-111">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="df1be-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="df1be-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

