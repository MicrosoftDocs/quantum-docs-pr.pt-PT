---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: Função AllEqualityFactB
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 725291e8b5d12683ad580d5938dadd561831e88e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853545"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="fecd7-102">Função AllEqualityFactB</span><span class="sxs-lookup"><span data-stu-id="fecd7-102">AllEqualityFactB function</span></span>

<span data-ttu-id="fecd7-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="fecd7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="fecd7-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fecd7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fecd7-105">Afirma que duas matrizes de valores booleanos são iguais.</span><span class="sxs-lookup"><span data-stu-id="fecd7-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="fecd7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fecd7-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="fecd7-107">real : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="fecd7-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="fecd7-108">A matriz que é produzida por um caso de teste de interesse.</span><span class="sxs-lookup"><span data-stu-id="fecd7-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="fecd7-109">esperado : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="fecd7-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="fecd7-110">A matriz que é esperada de um caso de teste de interesse.</span><span class="sxs-lookup"><span data-stu-id="fecd7-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="fecd7-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="fecd7-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="fecd7-112">Uma mensagem a ser impressa se as matrizes não forem iguais.</span><span class="sxs-lookup"><span data-stu-id="fecd7-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fecd7-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fecd7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

