---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: Função De Bits Arranjados
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f3bc4dff73d5ad6393294fc3770b8d36e6094fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217072"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="f45e8-102">Função De Bits Arranjados</span><span class="sxs-lookup"><span data-stu-id="f45e8-102">ArrangedQubits function</span></span>

<span data-ttu-id="f45e8-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f45e8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f45e8-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f45e8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f45e8-105">Organize o controlo, o alvo e os qubits do ajudante de acordo com um índice</span><span class="sxs-lookup"><span data-stu-id="f45e8-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="f45e8-106">Description</span><span class="sxs-lookup"><span data-stu-id="f45e8-106">Description</span></span>

<span data-ttu-id="f45e8-107">Devolve um conjunto qubit com o alvo no índice 0, e controla i no índice 2^i.</span><span class="sxs-lookup"><span data-stu-id="f45e8-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="f45e8-108">Os qubits do ajudante são inseridos em todas as outras posições da matriz.</span><span class="sxs-lookup"><span data-stu-id="f45e8-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="f45e8-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="f45e8-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="f45e8-110">controlos: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f45e8-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="f45e8-111">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f45e8-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="f45e8-112">ajudante : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f45e8-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="f45e8-113">Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f45e8-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

