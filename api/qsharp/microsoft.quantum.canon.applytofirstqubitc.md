---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: Aplicar a operação FirstQubitC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e2c137ad4a8252731acf94d6f2343f8fd386b8e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717412"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="3dd72-102">Aplicar a operação FirstQubitC</span><span class="sxs-lookup"><span data-stu-id="3dd72-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="3dd72-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3dd72-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3dd72-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3dd72-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3dd72-105">Aplica operação op ao primeiro qubit no registo.</span><span class="sxs-lookup"><span data-stu-id="3dd72-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="3dd72-106">O modificador `C` indica que a operação é controlável.</span><span class="sxs-lookup"><span data-stu-id="3dd72-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3dd72-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="3dd72-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="3dd72-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="3dd72-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="3dd72-109">Uma operação a ser aplicada ao primeiro qubit</span><span class="sxs-lookup"><span data-stu-id="3dd72-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="3dd72-110">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3dd72-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3dd72-111">Qubit array para o primeiro qubit de qual a operação é aplicada</span><span class="sxs-lookup"><span data-stu-id="3dd72-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="3dd72-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3dd72-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3dd72-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3dd72-113">See Also</span></span>

- [<span data-ttu-id="3dd72-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="3dd72-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)