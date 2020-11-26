---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: Requer tipo definido pelo utilizadorCapability
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 0d9e4eb294b3ce91058c204d5dba37ea29b4ac28
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231012"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="0459d-102">Requer tipo definido pelo utilizadorCapability</span><span class="sxs-lookup"><span data-stu-id="0459d-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="0459d-103">Espaço de nome: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="0459d-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="0459d-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0459d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0459d-105">Atributo reconhecido pelo compilador usado para marcar uma chamada com as capacidades de tempo de execução que requer.</span><span class="sxs-lookup"><span data-stu-id="0459d-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="0459d-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="0459d-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="0459d-107">Nível : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="0459d-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="0459d-108">O nome do nível de capacidade de execução exigido pelo callable.</span><span class="sxs-lookup"><span data-stu-id="0459d-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="0459d-109">Razão : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="0459d-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="0459d-110">Uma descrição do porquê da chamada requer esta capacidade de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="0459d-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="0459d-111">Observações</span><span class="sxs-lookup"><span data-stu-id="0459d-111">Remarks</span></span>

<span data-ttu-id="0459d-112">Este atributo é automaticamente adicionado aos callables pelo compilador, a menos que já exista uma instância deste atributo no callable.</span><span class="sxs-lookup"><span data-stu-id="0459d-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="0459d-113">Não deve ser utilizado exceto em casos raros em que o compilador não infera corretamente a capacidade necessária.</span><span class="sxs-lookup"><span data-stu-id="0459d-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="0459d-114">Abaixo está a lista de nomes de nível de capacidade, para aumentar as capacidades ou reduzir restrições:</span><span class="sxs-lookup"><span data-stu-id="0459d-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="0459d-115">Os resultados da medição não podem ser comparados para a igualdade.</span><span class="sxs-lookup"><span data-stu-id="0459d-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="0459d-116">Os resultados da medição só podem ser comparados para a igualdade em expressões condicionais de declaração em operações.</span><span class="sxs-lookup"><span data-stu-id="0459d-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="0459d-117">O bloco de uma declaração se-if que depende de um resultado não pode conter declarações definidas para variáveis mutáveis declaradas fora do bloco, ou declarações de devolução.</span><span class="sxs-lookup"><span data-stu-id="0459d-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="0459d-118">Sem restrições de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="0459d-118">No runtime restrictions.</span></span> <span data-ttu-id="0459d-119">Qualquer programa Q# pode ser executado.</span><span class="sxs-lookup"><span data-stu-id="0459d-119">Any Q# program can be executed.</span></span>