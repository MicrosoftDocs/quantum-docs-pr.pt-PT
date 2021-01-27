---
uid: Microsoft.Quantum.Synthesis.Extended
title: Função estendida
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855478"
---
# <a name="extended-function"></a><span data-ttu-id="8d791-102">Função estendida</span><span class="sxs-lookup"><span data-stu-id="8d791-102">Extended function</span></span>

<span data-ttu-id="8d791-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="8d791-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="8d791-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d791-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8d791-105">Estende um espectro por coeficientes invertidos</span><span class="sxs-lookup"><span data-stu-id="8d791-105">Extends a spectrum by inverted coefficients</span></span>

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="8d791-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8d791-106">Input</span></span>

### <a name="spectrum--int"></a><span data-ttu-id="8d791-107">espectro : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8d791-107">spectrum : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8d791-108">Coeficientes espectrais</span><span class="sxs-lookup"><span data-stu-id="8d791-108">Spectral coefficients</span></span>



## <a name="output--int"></a><span data-ttu-id="8d791-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8d791-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8d791-110">Coeficientes seguidos por cópia invertida</span><span class="sxs-lookup"><span data-stu-id="8d791-110">Coefficients followed by inverted copy</span></span>

## <a name="example"></a><span data-ttu-id="8d791-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8d791-111">Example</span></span>

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```