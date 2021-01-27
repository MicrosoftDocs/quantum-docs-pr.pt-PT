---
uid: Microsoft.Quantum.Canon.CY
title: Operação CY
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 862f058e630ee6d9159e0fe514ca2dd1179ea9a2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840740"
---
# <a name="cy-operation"></a><span data-ttu-id="46ab4-102">Operação CY</span><span class="sxs-lookup"><span data-stu-id="46ab4-102">CY operation</span></span>

<span data-ttu-id="46ab4-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="46ab4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="46ab4-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="46ab4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="46ab4-105">Aplica o portão controlado-Y (CY) a um par de qubits.</span><span class="sxs-lookup"><span data-stu-id="46ab4-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="46ab4-106">$$ \start{align} 1 & 0 & 0 & \\ \\ 0 & 1 & 0 & \\ \\ 0 & 0 & 0 & -i \\ \\ 0 & 0 & i & 0\end{align}, $$ onde as linhas e colunas são organizadas como nos conceitos quânticos.</span><span class="sxs-lookup"><span data-stu-id="46ab4-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="46ab4-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="46ab4-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="46ab4-108">controlo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="46ab4-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="46ab4-109">Controlo qubit para o portão CY.</span><span class="sxs-lookup"><span data-stu-id="46ab4-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="46ab4-110">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="46ab4-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="46ab4-111">Qubit de alvo para o portão CY.</span><span class="sxs-lookup"><span data-stu-id="46ab4-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="46ab4-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="46ab4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="46ab4-113">Observações</span><span class="sxs-lookup"><span data-stu-id="46ab4-113">Remarks</span></span>

<span data-ttu-id="46ab4-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="46ab4-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```