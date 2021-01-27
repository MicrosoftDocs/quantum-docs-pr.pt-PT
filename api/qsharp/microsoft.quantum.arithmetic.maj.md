---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: Operação MAJ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 68236f1deeb409a01152d4b7e854202a1134314e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846552"
---
# <a name="maj-operation"></a><span data-ttu-id="fba28-102">Operação MAJ</span><span class="sxs-lookup"><span data-stu-id="fba28-102">MAJ operation</span></span>

<span data-ttu-id="fba28-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fba28-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fba28-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fba28-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fba28-105">Isto aplica a operação de maioria no local a 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="fba28-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="fba28-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="fba28-106">Description</span></span>

<span data-ttu-id="fba28-107">Se denotarmos o estado do qubit alvo como $\ket{z}$, e os estados de entrada dos qubits de entrada como $\ket{x}$ e $\ket{y}$, então esta operação executa a seguinte transformação: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}}</span><span class="sxs-lookup"><span data-stu-id="fba28-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="fba28-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="fba28-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="fba28-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fba28-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fba28-110">O primeiro qubit de entrada.</span><span class="sxs-lookup"><span data-stu-id="fba28-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="fba28-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fba28-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fba28-112">O segundo qubit de entrada.</span><span class="sxs-lookup"><span data-stu-id="fba28-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="fba28-113">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fba28-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fba28-114">Um qubit no qual será aplicada a função maioritária.</span><span class="sxs-lookup"><span data-stu-id="fba28-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fba28-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fba28-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

