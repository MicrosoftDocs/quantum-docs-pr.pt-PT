---
uid: Microsoft.Quantum.Canon.CY
title: Operação CY
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 291891457ff39cf7092d17aa1d900dd0d35d9cf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716362"
---
# <a name="cy-operation"></a><span data-ttu-id="d0395-102">Operação CY</span><span class="sxs-lookup"><span data-stu-id="d0395-102">CY operation</span></span>

<span data-ttu-id="d0395-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d0395-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d0395-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0395-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0395-105">Aplica o portão controlado-Y (CY) a um par de qubits.</span><span class="sxs-lookup"><span data-stu-id="d0395-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="d0395-106">$$ \start{align} 1 & 0 & 0 & \\ \\ 0 & 1 & 0 & \\ \\ 0 & 0 & 0 & -i \\ \\ 0 & 0 & i & 0\end{align}, $$ onde as linhas e colunas são organizadas como nos conceitos quânticos.</span><span class="sxs-lookup"><span data-stu-id="d0395-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="d0395-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="d0395-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="d0395-108">controlo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d0395-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d0395-109">Controlo qubit para o portão CY.</span><span class="sxs-lookup"><span data-stu-id="d0395-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d0395-110">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d0395-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d0395-111">Qubit de alvo para o portão CY.</span><span class="sxs-lookup"><span data-stu-id="d0395-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d0395-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0395-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d0395-113">Observações</span><span class="sxs-lookup"><span data-stu-id="d0395-113">Remarks</span></span>

<span data-ttu-id="d0395-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="d0395-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```