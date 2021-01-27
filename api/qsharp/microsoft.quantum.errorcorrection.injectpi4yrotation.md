---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: Operação InjectPi4YRotation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 249c347c9e9729e719eda69e4e9a21847d9a46eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825949"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="da469-102">Operação InjectPi4YRotation</span><span class="sxs-lookup"><span data-stu-id="da469-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="da469-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="da469-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="da469-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="da469-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="da469-105">Roda um único qubit por π/4 sobre o eixo Y.</span><span class="sxs-lookup"><span data-stu-id="da469-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="da469-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="da469-106">Description</span></span>

<span data-ttu-id="da469-107">Executa uma rotação de π/4 sobre `Y` .</span><span class="sxs-lookup"><span data-stu-id="da469-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="da469-108">A rotação é realizada consumindo um estado mágico; ou seja, uma cópia do estado $\ \start{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} .</span><span class="sxs-lookup"><span data-stu-id="da469-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="da469-109">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="da469-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="da469-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="da469-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="da469-111">dados : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="da469-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="da469-112">Um qubit a ser rodado cerca de $Y$ por $\pi / 4$.</span><span class="sxs-lookup"><span data-stu-id="da469-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="da469-113">magia : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="da469-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="da469-114">Um qubit inicialmente no estado mágico.</span><span class="sxs-lookup"><span data-stu-id="da469-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="da469-115">Após a aplicação desta operação, `magic` é devolvido ao estado $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="da469-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="da469-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da469-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="da469-117">Observações</span><span class="sxs-lookup"><span data-stu-id="da469-117">Remarks</span></span>

<span data-ttu-id="da469-118">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="da469-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="da469-119">e</span><span class="sxs-lookup"><span data-stu-id="da469-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="da469-120">Esta operação apoia o `Adjoint` functor, caso em que o mesmo estado mágico é consumido, mas o efeito no qubit de dados é de $-\pi/4$ $Y rotação de $.</span><span class="sxs-lookup"><span data-stu-id="da469-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>