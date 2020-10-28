---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: Preparar Operação Estado DeEnangled
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 299d586f7581acdecf22da2f6bbfbb8d45f372f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722176"
---
# <a name="prepareentangledstate-operation"></a><span data-ttu-id="d42b6-102">Preparar Operação Estado DeEnangled</span><span class="sxs-lookup"><span data-stu-id="d42b6-102">PrepareEntangledState operation</span></span>

<span data-ttu-id="d42b6-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="d42b6-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="d42b6-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d42b6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d42b6-105">Em pares envolve dois registos qubit.</span><span class="sxs-lookup"><span data-stu-id="d42b6-105">Pairwise entangles two qubit registers.</span></span>

<span data-ttu-id="d42b6-106">Ou seja, tendo em conta dois registos, prepara o estado máximo emaranhado $\frac {1} {\sqrt {2} } \left(\ket {00} + \ket {11} \right)$ entre cada par de qubits nos respetivos registos, assumindo que cada registo começa no estado $\ket{0\cdots 0}$</span><span class="sxs-lookup"><span data-stu-id="d42b6-106">That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.</span></span>

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d42b6-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="d42b6-107">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="d42b6-108">esquerda : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d42b6-108">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d42b6-109">Um qubit array no estado $\ket{0\cdots 0}$</span><span class="sxs-lookup"><span data-stu-id="d42b6-109">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="d42b6-110">direita: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d42b6-110">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d42b6-111">Um qubit array no estado $\ket{0\cdots 0}$</span><span class="sxs-lookup"><span data-stu-id="d42b6-111">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="d42b6-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d42b6-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

