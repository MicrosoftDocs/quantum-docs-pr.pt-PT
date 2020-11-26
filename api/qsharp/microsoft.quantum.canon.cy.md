---
uid: Microsoft.Quantum.Canon.CY
title: Operação CY
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 4a1a533421dd9205e973d5e8237d67b20bc4886d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216579"
---
# <a name="cy-operation"></a><span data-ttu-id="331e7-102">Operação CY</span><span class="sxs-lookup"><span data-stu-id="331e7-102">CY operation</span></span>

<span data-ttu-id="331e7-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="331e7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="331e7-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="331e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="331e7-105">Aplica o portão controlado-Y (CY) a um par de qubits.</span><span class="sxs-lookup"><span data-stu-id="331e7-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="331e7-106">$$ \start{align} 1 & 0 & 0 & \\ \\ 0 & 1 & 0 & \\ \\ 0 & 0 & 0 & -i \\ \\ 0 & 0 & i & 0\end{align}, $$ onde as linhas e colunas são organizadas como nos conceitos quânticos.</span><span class="sxs-lookup"><span data-stu-id="331e7-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="331e7-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="331e7-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="331e7-108">controlo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="331e7-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="331e7-109">Controlo qubit para o portão CY.</span><span class="sxs-lookup"><span data-stu-id="331e7-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="331e7-110">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="331e7-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="331e7-111">Qubit de alvo para o portão CY.</span><span class="sxs-lookup"><span data-stu-id="331e7-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="331e7-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="331e7-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="331e7-113">Observações</span><span class="sxs-lookup"><span data-stu-id="331e7-113">Remarks</span></span>

<span data-ttu-id="331e7-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="331e7-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```