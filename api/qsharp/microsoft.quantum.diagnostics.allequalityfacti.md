---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: Função AllEqualityFactI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 92b57f49407d558e5f8d0365c168b7890f1f4981
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223889"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="22f15-102">Função AllEqualityFactI</span><span class="sxs-lookup"><span data-stu-id="22f15-102">AllEqualityFactI function</span></span>

<span data-ttu-id="22f15-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="22f15-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="22f15-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="22f15-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="22f15-105">Afirma que duas matrizes de valores inteiros são iguais.</span><span class="sxs-lookup"><span data-stu-id="22f15-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="22f15-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="22f15-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="22f15-107">real : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="22f15-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="22f15-108">A matriz que é produzida por um caso de teste de interesse.</span><span class="sxs-lookup"><span data-stu-id="22f15-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="22f15-109">esperado : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="22f15-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="22f15-110">A matriz que é esperada de um caso de teste de interesse.</span><span class="sxs-lookup"><span data-stu-id="22f15-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="22f15-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="22f15-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="22f15-112">Uma mensagem a ser impressa se as matrizes não forem iguais.</span><span class="sxs-lookup"><span data-stu-id="22f15-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="22f15-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="22f15-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

