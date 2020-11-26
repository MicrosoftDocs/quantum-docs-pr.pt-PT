---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Aplicação Operação Vídeopardade
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: 40157b6a166b09c6fee63d86e203f92069d008f1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225759"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="30972-102">Aplicação Operação Vídeopardade</span><span class="sxs-lookup"><span data-stu-id="30972-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="30972-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="30972-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="30972-104">Pacote: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="30972-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="30972-105">Computa a diferença de paridade entre um PQRS anterior... termos e o próximo PQRS... termo.</span><span class="sxs-lookup"><span data-stu-id="30972-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="30972-106">Esta diferença é calculada num qubit auxiliar.</span><span class="sxs-lookup"><span data-stu-id="30972-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="30972-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="30972-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="30972-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="30972-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="30972-109">Lista de índices para PQRS anteriores... termos.</span><span class="sxs-lookup"><span data-stu-id="30972-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="30972-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="30972-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="30972-111">Lista de índices para o próximo PQRS... termos.</span><span class="sxs-lookup"><span data-stu-id="30972-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="30972-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="30972-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="30972-113">Qubit auxiliar sobre os resultados do cálculo da paridade são armazenados.</span><span class="sxs-lookup"><span data-stu-id="30972-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="30972-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="30972-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="30972-115">Qubit agido por todos os PQRS... termos.</span><span class="sxs-lookup"><span data-stu-id="30972-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="30972-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="30972-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="30972-117">Observações</span><span class="sxs-lookup"><span data-stu-id="30972-117">Remarks</span></span>

<span data-ttu-id="30972-118">Isto pressupõe que os índices de P < Q < R < S < ... tanto para o prevPQ como para o próximoPQ.</span><span class="sxs-lookup"><span data-stu-id="30972-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>