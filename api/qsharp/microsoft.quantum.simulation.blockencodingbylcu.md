---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: Função BlockEncodingByLCU
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 1d7890e96513817c127ef768f49c0b915ea22fa1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858165"
---
# <a name="blockencodingbylcu-function"></a><span data-ttu-id="50a6a-102">Função BlockEncodingByLCU</span><span class="sxs-lookup"><span data-stu-id="50a6a-102">BlockEncodingByLCU function</span></span>

<span data-ttu-id="50a6a-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="50a6a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="50a6a-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="50a6a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="50a6a-105">Codifica um operador de interesse em `BlockEncoding` um .</span><span class="sxs-lookup"><span data-stu-id="50a6a-105">Encodes an operator of interest into a `BlockEncoding`.</span></span>

<span data-ttu-id="50a6a-106">Isto constrói um `BlockEncoding` $U unitário=P\cdot V\cdot P^\dagger$ que codifica algum operador $H=\sum_{j}|\alpha_j| U_j de juros que é uma combinação linear de unitários.</span><span class="sxs-lookup"><span data-stu-id="50a6a-106">This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="50a6a-107">Tipicamente, $P$ é um unitário de preparação de estado tal que $P\ket {0} \_ a=\sum_j\sqrt{\alpha_j/ \| \vec\alpha \| \_ 2}\ket{j} \_ a$, e $V=sum_{j}ket{j}\bra{j} \_ a\otimes U_j$.</span><span class="sxs-lookup"><span data-stu-id="50a6a-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="50a6a-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="50a6a-108">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="50a6a-109">estatalPreparação : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="50a6a-109">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="50a6a-110">Um $P$ unitário que prepara algum estado-alvo.</span><span class="sxs-lookup"><span data-stu-id="50a6a-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="50a6a-111">seletor : ('T'S) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="50a6a-111">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="50a6a-112">Um $V$ unitário que codifica as unidades componentes de $H$.</span><span class="sxs-lookup"><span data-stu-id="50a6a-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--ts--unit--is-adj--ctl"></a><span data-ttu-id="50a6a-113">Saída : ('T'S) = [> Unidade](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="50a6a-113">Output : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="50a6a-114">Um $U$ unitário agindo conjuntamente em registos `a` e `s` que codifica $H$, e satisfaz $U^\dagger = U$.</span><span class="sxs-lookup"><span data-stu-id="50a6a-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U^\dagger = U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="50a6a-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="50a6a-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="50a6a-116">'T</span><span class="sxs-lookup"><span data-stu-id="50a6a-116">'T</span></span>


### <a name="s"></a><span data-ttu-id="50a6a-117">'S</span><span class="sxs-lookup"><span data-stu-id="50a6a-117">'S</span></span>



## <a name="remarks"></a><span data-ttu-id="50a6a-118">Observações</span><span class="sxs-lookup"><span data-stu-id="50a6a-118">Remarks</span></span>

<span data-ttu-id="50a6a-119">Esta `BlockEncoding` implementação confere-lhe as propriedades de um `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="50a6a-119">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="50a6a-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="50a6a-120">See Also</span></span>

- [<span data-ttu-id="50a6a-121">Microsoft.Quantum.Simulation.BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="50a6a-121">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="50a6a-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="50a6a-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)