---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: Aplicar a operação FirstQubitC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: a36d20e03ebed82435d1d4136f4ce777eb468926
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850706"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="f5fab-102">Aplicar a operação FirstQubitC</span><span class="sxs-lookup"><span data-stu-id="f5fab-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="f5fab-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f5fab-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f5fab-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f5fab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f5fab-105">Aplica operação op ao primeiro qubit no registo.</span><span class="sxs-lookup"><span data-stu-id="f5fab-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="f5fab-106">O modificador `C` indica que a operação é controlável.</span><span class="sxs-lookup"><span data-stu-id="f5fab-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="f5fab-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="f5fab-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="f5fab-108">op [](xref:microsoft.quantum.lang-ref.qubit) : => [Qubit Unit](xref:microsoft.quantum.lang-ref.unit) is Ctl</span><span class="sxs-lookup"><span data-stu-id="f5fab-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f5fab-109">Uma operação a ser aplicada ao primeiro qubit</span><span class="sxs-lookup"><span data-stu-id="f5fab-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="f5fab-110">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f5fab-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f5fab-111">Qubit array para o primeiro qubit de qual a operação é aplicada</span><span class="sxs-lookup"><span data-stu-id="f5fab-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="f5fab-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f5fab-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="f5fab-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f5fab-113">See Also</span></span>

- [<span data-ttu-id="f5fab-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="f5fab-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)