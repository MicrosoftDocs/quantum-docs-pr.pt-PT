---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: Função AllEqualityFactB
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 100aacccbfd5b45ac9f859cd89424b0ed4007f72
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713075"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="36088-102">Função AllEqualityFactB</span><span class="sxs-lookup"><span data-stu-id="36088-102">AllEqualityFactB function</span></span>

<span data-ttu-id="36088-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="36088-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="36088-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="36088-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="36088-105">Afirma que duas matrizes de valores booleanos são iguais.</span><span class="sxs-lookup"><span data-stu-id="36088-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="36088-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="36088-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="36088-107">real : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="36088-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="36088-108">A matriz que é produzida por um caso de teste de interesse.</span><span class="sxs-lookup"><span data-stu-id="36088-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="36088-109">esperado : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="36088-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="36088-110">A matriz que é esperada de um caso de teste de interesse.</span><span class="sxs-lookup"><span data-stu-id="36088-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="36088-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="36088-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="36088-112">Uma mensagem a ser impressa se as matrizes não forem iguais.</span><span class="sxs-lookup"><span data-stu-id="36088-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="36088-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="36088-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

