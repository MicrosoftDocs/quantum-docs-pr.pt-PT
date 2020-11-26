---
uid: Microsoft.Quantum.Canon.CZ
title: Operação CZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 419082dbf8f96a9fe2dfabeab77e1823cb59a8f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207212"
---
# <a name="cz-operation"></a><span data-ttu-id="f128b-102">Operação CZ</span><span class="sxs-lookup"><span data-stu-id="f128b-102">CZ operation</span></span>

<span data-ttu-id="f128b-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f128b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f128b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f128b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f128b-105">Aplica o portão controlado-Z (CZ) a um par de qubits.</span><span class="sxs-lookup"><span data-stu-id="f128b-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="f128b-106">$$ \start{align} 1 & 0 & 0 & \\ \\ 0 & 0 & 0 & \\ \\ 0 & 0 & 1 & \\ \\ 0 & 0 & 0 & -1 \end{}, $$ onde as linhas e colunas são organizadas como guia no conceito quântico.</span><span class="sxs-lookup"><span data-stu-id="f128b-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f128b-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="f128b-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="f128b-108">controlo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f128b-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f128b-109">Controlo qubit para o portão CZ.</span><span class="sxs-lookup"><span data-stu-id="f128b-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f128b-110">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f128b-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f128b-111">Qubit de alvo para o portão CZ.</span><span class="sxs-lookup"><span data-stu-id="f128b-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f128b-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f128b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f128b-113">Observações</span><span class="sxs-lookup"><span data-stu-id="f128b-113">Remarks</span></span>

<span data-ttu-id="f128b-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="f128b-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```