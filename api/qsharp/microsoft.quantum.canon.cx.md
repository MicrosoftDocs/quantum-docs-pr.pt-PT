---
uid: Microsoft.Quantum.Canon.CX
title: Operação CX
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 4eaecf372f3054de4886b1e42c6b4ce386a22f73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207246"
---
# <a name="cx-operation"></a><span data-ttu-id="9a95b-102">Operação CX</span><span class="sxs-lookup"><span data-stu-id="9a95b-102">CX operation</span></span>

<span data-ttu-id="9a95b-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9a95b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9a95b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a95b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a95b-105">Aplica o portão controlado X (CX) a um par de qubits.</span><span class="sxs-lookup"><span data-stu-id="9a95b-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="9a95b-106">$$ \start{align} \left(\start{matrix} 1 & 0 & 0 & 0 \\ \\ & 1 & 0 & \\ \\ 0 & 0 & 0 & \\ \\ 10 & 0 & 1 & 0\end{matrix) \end{}) \end{}) \end{}) \end{}) \end{}) \end{}) \end{}) \end{}) \end align, {}} $$ onde linhas e colunas são organizadas como no guia de conceitos quânticos.</span><span class="sxs-lookup"><span data-stu-id="9a95b-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9a95b-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="9a95b-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="9a95b-108">controlo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9a95b-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9a95b-109">Controlo do qubit para o portão CX.</span><span class="sxs-lookup"><span data-stu-id="9a95b-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9a95b-110">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9a95b-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9a95b-111">Qubit de alvo para o portão CX.</span><span class="sxs-lookup"><span data-stu-id="9a95b-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a95b-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a95b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9a95b-113">Observações</span><span class="sxs-lookup"><span data-stu-id="9a95b-113">Remarks</span></span>

<span data-ttu-id="9a95b-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="9a95b-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="9a95b-115">e:</span><span class="sxs-lookup"><span data-stu-id="9a95b-115">and to:</span></span>

```qsharp
CNOT(control, target);
```