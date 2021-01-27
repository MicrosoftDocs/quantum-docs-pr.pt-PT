---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Aplicação OperaçãoIf
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: 109a5c4748d183f199e420b4b1aef687613d220c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841876"
---
# <a name="applyif-operation"></a><span data-ttu-id="a46ff-102">Aplicação OperaçãoIf</span><span class="sxs-lookup"><span data-stu-id="a46ff-102">ApplyIf operation</span></span>

<span data-ttu-id="a46ff-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a46ff-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a46ff-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a46ff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a46ff-105">Aplica uma operação condicionada a uma parte clássica.</span><span class="sxs-lookup"><span data-stu-id="a46ff-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="a46ff-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="a46ff-106">Description</span></span>

<span data-ttu-id="a46ff-107">Dada uma operação `op` e um pouco de `bit` valor, aplica-se `op` ao se é `target` `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="a46ff-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="a46ff-108">Se, `false` nada acontecer ao `target` .</span><span class="sxs-lookup"><span data-stu-id="a46ff-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="a46ff-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="a46ff-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="a46ff-110">op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="a46ff-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a46ff-111">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="a46ff-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="a46ff-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a46ff-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a46ff-113">um booleano que controla se a operação é aplicada ou não.</span><span class="sxs-lookup"><span data-stu-id="a46ff-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="a46ff-114">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="a46ff-114">target : 'T</span></span>

<span data-ttu-id="a46ff-115">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="a46ff-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a46ff-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a46ff-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a46ff-117">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="a46ff-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a46ff-118">'T</span><span class="sxs-lookup"><span data-stu-id="a46ff-118">'T</span></span>

<span data-ttu-id="a46ff-119">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="a46ff-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="a46ff-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a46ff-120">Example</span></span>

<span data-ttu-id="a46ff-121">O seguinte prepara um registo de qubits num estado de base computacional representado por uma corda clássica dada como uma matriz de `Bool` valores:</span><span class="sxs-lookup"><span data-stu-id="a46ff-121">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="a46ff-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a46ff-122">See Also</span></span>

- [<span data-ttu-id="a46ff-123">Microsoft.Quantum.Canon.ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="a46ff-123">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="a46ff-124">Microsoft.Quantum.Canon.ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="a46ff-124">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="a46ff-125">Microsoft.Quantum.Canon.ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="a46ff-125">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)