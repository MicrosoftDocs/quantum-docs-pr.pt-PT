---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: Operação MAJ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 356689baa6d47b7b93a393f3672991bb589f6921
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222767"
---
# <a name="maj-operation"></a><span data-ttu-id="ac972-102">Operação MAJ</span><span class="sxs-lookup"><span data-stu-id="ac972-102">MAJ operation</span></span>

<span data-ttu-id="ac972-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ac972-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ac972-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac972-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac972-105">Isto aplica a operação de maioria no local a 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="ac972-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ac972-106">Description</span><span class="sxs-lookup"><span data-stu-id="ac972-106">Description</span></span>

<span data-ttu-id="ac972-107">Se denotarmos o estado do qubit alvo como $\ket{z}$, e os estados de entrada dos qubits de entrada como $\ket{x}$ e $\ket{y}$, então esta operação executa a seguinte transformação: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}}</span><span class="sxs-lookup"><span data-stu-id="ac972-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="ac972-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="ac972-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="ac972-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ac972-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ac972-110">O primeiro qubit de entrada.</span><span class="sxs-lookup"><span data-stu-id="ac972-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="ac972-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ac972-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ac972-112">O segundo qubit de entrada.</span><span class="sxs-lookup"><span data-stu-id="ac972-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ac972-113">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ac972-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ac972-114">Um qubit no qual será aplicada a função maioritária.</span><span class="sxs-lookup"><span data-stu-id="ac972-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ac972-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac972-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

