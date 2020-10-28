---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Aplicação Operação Vídeopardade
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: bb01eb684ff1820be08a573c0ca6cfc12efeb889
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723982"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="15e74-102">Aplicação Operação Vídeopardade</span><span class="sxs-lookup"><span data-stu-id="15e74-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="15e74-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="15e74-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="15e74-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="15e74-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="15e74-105">Computa a diferença de paridade entre um PQRS anterior... termos e o próximo PQRS... termo.</span><span class="sxs-lookup"><span data-stu-id="15e74-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="15e74-106">Esta diferença é calculada num qubit auxiliar.</span><span class="sxs-lookup"><span data-stu-id="15e74-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="15e74-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="15e74-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="15e74-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="15e74-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="15e74-109">Lista de índices para PQRS anteriores... termos.</span><span class="sxs-lookup"><span data-stu-id="15e74-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="15e74-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="15e74-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="15e74-111">Lista de índices para o próximo PQRS... termos.</span><span class="sxs-lookup"><span data-stu-id="15e74-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="15e74-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="15e74-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="15e74-113">Qubit auxiliar sobre os resultados do cálculo da paridade são armazenados.</span><span class="sxs-lookup"><span data-stu-id="15e74-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="15e74-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="15e74-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="15e74-115">Qubit agido por todos os PQRS... termos.</span><span class="sxs-lookup"><span data-stu-id="15e74-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="15e74-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15e74-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="15e74-117">Observações</span><span class="sxs-lookup"><span data-stu-id="15e74-117">Remarks</span></span>

<span data-ttu-id="15e74-118">Isto pressupõe que os índices de P < Q < R < S < ... tanto para o prevPQ como para o próximoPQ.</span><span class="sxs-lookup"><span data-stu-id="15e74-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>