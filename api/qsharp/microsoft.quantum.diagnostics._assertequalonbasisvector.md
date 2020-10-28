---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: operação _assertEqualOnBasisVector
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 01b6d5aede102e47df86ea70d071d81eba1ade6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713156"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="d15af-102">operação _assertEqualOnBasisVector</span><span class="sxs-lookup"><span data-stu-id="d15af-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="d15af-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d15af-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d15af-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d15af-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d15af-105">Verifica se o resultado da aplicação de duas operações `givenU` e de um estado de base é o `expectedU` mesmo.</span><span class="sxs-lookup"><span data-stu-id="d15af-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="d15af-106">O estado de base é descrito por `basis` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d15af-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="d15af-107">Consulte <xref:microsoft.quantum.extensions.fliptobasis> a função para mais detalhes sobre esta descrição.</span><span class="sxs-lookup"><span data-stu-id="d15af-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="d15af-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="d15af-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="d15af-109">base : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d15af-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d15af-110">Estado de base especificado por um ID de base de um único qubit (0 <= id <= 3) para cada um dos $n$ qubits.</span><span class="sxs-lookup"><span data-stu-id="d15af-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="d15af-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="d15af-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d15af-112">Operação a $n dólares qubits a serem verificados.</span><span class="sxs-lookup"><span data-stu-id="d15af-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="d15af-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="d15af-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="d15af-114">A operação de referência em $n$ qubits que a givenU deve ser comparada.</span><span class="sxs-lookup"><span data-stu-id="d15af-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d15af-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d15af-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

