---
uid: Microsoft.Quantum.Canon.NoOp
title: Operação NoOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 35b6b62cab35f941f04b150dcca763457ddaa084
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205971"
---
# <a name="noop-operation"></a><span data-ttu-id="7a780-102">Operação NoOp</span><span class="sxs-lookup"><span data-stu-id="7a780-102">NoOp operation</span></span>

<span data-ttu-id="7a780-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7a780-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7a780-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7a780-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7a780-105">Executa a operação de identidade (no-op) num argumento.</span><span class="sxs-lookup"><span data-stu-id="7a780-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="7a780-106">Description</span><span class="sxs-lookup"><span data-stu-id="7a780-106">Description</span></span>

<span data-ttu-id="7a780-107">Esta operação tem um valor de qualquer tipo e não lhe faz nada.</span><span class="sxs-lookup"><span data-stu-id="7a780-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="7a780-108">Isto pode ser útil sempre que se espera uma entrada de um tipo de operação, mas não devem ser tomadas medidas.</span><span class="sxs-lookup"><span data-stu-id="7a780-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="7a780-109">Por exemplo, se uma síndrome de correção de erros específica indicar que não ocorreu nenhum erro, `NoOp<Qubit[]>` pode ser o procedimento correto de recuperação.</span><span class="sxs-lookup"><span data-stu-id="7a780-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="7a780-110">Da mesma forma, se uma operação espera um procedimento de preparação do estado como entrada, `NoOp<Qubit[]>` pode ser usado para preparar o estado $\ket{0 \cdots 0}$.</span><span class="sxs-lookup"><span data-stu-id="7a780-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="7a780-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="7a780-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="7a780-112">entrada : 'T</span><span class="sxs-lookup"><span data-stu-id="7a780-112">input : 'T</span></span>

<span data-ttu-id="7a780-113">Um valor a ser ignorado.</span><span class="sxs-lookup"><span data-stu-id="7a780-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7a780-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a780-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7a780-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="7a780-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7a780-116">'T</span><span class="sxs-lookup"><span data-stu-id="7a780-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="7a780-117">Observações</span><span class="sxs-lookup"><span data-stu-id="7a780-117">Remarks</span></span>

<span data-ttu-id="7a780-118">Em quase todos os casos, o parâmetro do tipo `NoOp` para deve ser especificado explicitamente.</span><span class="sxs-lookup"><span data-stu-id="7a780-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="7a780-119">Por exemplo, `NoOp<Qubit>` é idêntico a <xref:microsoft.quantum.intrinsic.i> .</span><span class="sxs-lookup"><span data-stu-id="7a780-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a780-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7a780-120">See Also</span></span>

- [<span data-ttu-id="7a780-121">Microsoft.Quantum.Intrínseco.I</span><span class="sxs-lookup"><span data-stu-id="7a780-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)