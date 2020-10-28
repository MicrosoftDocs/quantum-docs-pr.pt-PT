---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: Função AllEqualityFactI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 9ccd212010ae557de5ca4ab2a38d4724c5c29aa8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713072"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="a554f-102">Função AllEqualityFactI</span><span class="sxs-lookup"><span data-stu-id="a554f-102">AllEqualityFactI function</span></span>

<span data-ttu-id="a554f-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a554f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a554f-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a554f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a554f-105">Afirma que duas matrizes de valores inteiros são iguais.</span><span class="sxs-lookup"><span data-stu-id="a554f-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="a554f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a554f-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="a554f-107">real : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a554f-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a554f-108">A matriz que é produzida por um caso de teste de interesse.</span><span class="sxs-lookup"><span data-stu-id="a554f-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="a554f-109">esperado : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a554f-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a554f-110">A matriz que é esperada de um caso de teste de interesse.</span><span class="sxs-lookup"><span data-stu-id="a554f-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="a554f-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a554f-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a554f-112">Uma mensagem a ser impressa se as matrizes não forem iguais.</span><span class="sxs-lookup"><span data-stu-id="a554f-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a554f-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a554f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

