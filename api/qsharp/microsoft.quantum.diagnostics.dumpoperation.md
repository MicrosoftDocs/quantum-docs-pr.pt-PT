---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: Operação DumpOperation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: b0e07173ddbeb8a96d4a85928258b6e30deb394d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202061"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="1a757-102">Operação DumpOperation</span><span class="sxs-lookup"><span data-stu-id="1a757-102">DumpOperation operation</span></span>

<span data-ttu-id="1a757-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1a757-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1a757-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1a757-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1a757-105">Dada uma operação, apresenta diagnósticos sobre a operação que são disponibilizados pelo alvo de execução atual.</span><span class="sxs-lookup"><span data-stu-id="1a757-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="1a757-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1a757-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="1a757-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1a757-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1a757-108">O número de qubits em que a determinada operação atua.</span><span class="sxs-lookup"><span data-stu-id="1a757-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="1a757-109">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="1a757-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="1a757-110">A operação que deve ser diagnosticada.</span><span class="sxs-lookup"><span data-stu-id="1a757-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1a757-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1a757-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1a757-112">Observações</span><span class="sxs-lookup"><span data-stu-id="1a757-112">Remarks</span></span>

<span data-ttu-id="1a757-113">Chamar esta operação não tem nenhum efeito observável dentro de Q#.</span><span class="sxs-lookup"><span data-stu-id="1a757-113">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="1a757-114">Os diagnósticos exatos que são apresentados, se houver, dependem do atual objetivo de execução e do ambiente de editor.</span><span class="sxs-lookup"><span data-stu-id="1a757-114">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="1a757-115">Por exemplo, quando utilizado no simulador quântico de estado inteiro, é apresentada uma matriz unitária utilizada para `op` representar.</span><span class="sxs-lookup"><span data-stu-id="1a757-115">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="1a757-116">Note que, quando executados em simuladores que admitem uma ambiguidade de fase global (por exemplo: o simulador de estado completo), as representações devolvidas podem variar até uma fase global.</span><span class="sxs-lookup"><span data-stu-id="1a757-116">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="1a757-117">Da mesma forma, a ordenação de representações matricias de linhas e colunas pode variar com as convenções utilizadas por cada simulador que suporta esta operação.</span><span class="sxs-lookup"><span data-stu-id="1a757-117">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>