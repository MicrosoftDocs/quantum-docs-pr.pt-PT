---
uid: Microsoft.Quantum.Canon.GrayCode
title: Função GrayCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716166"
---
# <a name="graycode-function"></a><span data-ttu-id="c7dc2-102">Função GrayCode</span><span class="sxs-lookup"><span data-stu-id="c7dc2-102">GrayCode function</span></span>

<span data-ttu-id="c7dc2-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c7dc2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c7dc2-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7dc2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c7dc2-105">Cria sequências de código cinza</span><span class="sxs-lookup"><span data-stu-id="c7dc2-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="c7dc2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c7dc2-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="c7dc2-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c7dc2-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c7dc2-108">Número de bits</span><span class="sxs-lookup"><span data-stu-id="c7dc2-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="c7dc2-109">Saída :[(Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span><span class="sxs-lookup"><span data-stu-id="c7dc2-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="c7dc2-110">Conjunto de tuples.</span><span class="sxs-lookup"><span data-stu-id="c7dc2-110">Array of tuples.</span></span> <span data-ttu-id="c7dc2-111">Primeiro valor em tuple é valor na sequência GrayCode Segundo valor em tuple é posição para alterar o valor atual para obter o próximo.</span><span class="sxs-lookup"><span data-stu-id="c7dc2-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>