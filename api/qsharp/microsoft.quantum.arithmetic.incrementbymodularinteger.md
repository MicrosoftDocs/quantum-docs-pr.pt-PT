---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: IncrementByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: f5bacef299ab0b3627e757abdcaa798cf9b2e7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846592"
---
# <a name="incrementbymodularinteger-operation"></a><span data-ttu-id="91bd1-102">IncrementByModularInteger</span><span class="sxs-lookup"><span data-stu-id="91bd1-102">IncrementByModularInteger operation</span></span>

<span data-ttu-id="91bd1-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="91bd1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="91bd1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91bd1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91bd1-105">Executa um incremento modular de um registo qubit por uma constante de inteiro.</span><span class="sxs-lookup"><span data-stu-id="91bd1-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="91bd1-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="91bd1-106">Description</span></span>

<span data-ttu-id="91bd1-107">Vamos denotar `increment` por $a$, `modulus` por $N$ e inteiro codificado `target` por $y$.</span><span class="sxs-lookup"><span data-stu-id="91bd1-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="91bd1-108">Em seguida, a operação executa a seguinte transformação: \start{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Os inteiros são codificados em formato pouco endiano.</span><span class="sxs-lookup"><span data-stu-id="91bd1-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format.</span></span>

## <a name="input"></a><span data-ttu-id="91bd1-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="91bd1-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="91bd1-110">incremento : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91bd1-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="91bd1-111">Incremento inteiro $a$ a ser adicionado a $y$.</span><span class="sxs-lookup"><span data-stu-id="91bd1-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="91bd1-112">módulo : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91bd1-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="91bd1-113">Inteiro $N$ que mods $y + a$.</span><span class="sxs-lookup"><span data-stu-id="91bd1-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="91bd1-114">alvo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="91bd1-114">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="91bd1-115">O inteiro $y$ em `LittleEndian` formato a que `increment` $a$ é adicionado.</span><span class="sxs-lookup"><span data-stu-id="91bd1-115">Integer $y$ in `LittleEndian` format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="91bd1-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="91bd1-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="91bd1-117">Observações</span><span class="sxs-lookup"><span data-stu-id="91bd1-117">Remarks</span></span>

<span data-ttu-id="91bd1-118">Assume que o valor inicial do alvo é inferior a $N$ e que o incremento $a$ é inferior a $N$.</span><span class="sxs-lookup"><span data-stu-id="91bd1-118">Assumes that the initial value of target is less than $N$ and that the increment $a$ is less than $N$.</span></span>
<span data-ttu-id="91bd1-119">Note que <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implementa a mesma operação na `PhaseLittleEndian` base.</span><span class="sxs-lookup"><span data-stu-id="91bd1-119">Note that <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implements the same operation in the `PhaseLittleEndian` basis.</span></span>

## <a name="see-also"></a><span data-ttu-id="91bd1-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="91bd1-120">See Also</span></span>

- [<span data-ttu-id="91bd1-121">Microsoft.Quantum.Aithmetic.IncrementPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="91bd1-121">Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)