---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: Aplicar operaçãoToFirstQubitA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 00dbff0b562f90653c8569589e838f11e6c938e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717401"
---
# <a name="applytofirstqubita-operation"></a><span data-ttu-id="0b6e0-102">Aplicar operaçãoToFirstQubitA</span><span class="sxs-lookup"><span data-stu-id="0b6e0-102">ApplyToFirstQubitA operation</span></span>

<span data-ttu-id="0b6e0-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0b6e0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0b6e0-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b6e0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b6e0-105">Aplica uma operação ao primeiro qubit no registo.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-105">Applies an operation to the first qubit in the register.</span></span>
<span data-ttu-id="0b6e0-106">O modificador `A` indica que a operação é adjacente.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0b6e0-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="0b6e0-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="0b6e0-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="0b6e0-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="0b6e0-109">Uma operação a ser aplicada ao primeiro qubit</span><span class="sxs-lookup"><span data-stu-id="0b6e0-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="0b6e0-110">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0b6e0-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0b6e0-111">Qubit array para o primeiro qubit de qual a operação é aplicada</span><span class="sxs-lookup"><span data-stu-id="0b6e0-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="0b6e0-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0b6e0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0b6e0-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0b6e0-113">See Also</span></span>

- [<span data-ttu-id="0b6e0-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="0b6e0-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)