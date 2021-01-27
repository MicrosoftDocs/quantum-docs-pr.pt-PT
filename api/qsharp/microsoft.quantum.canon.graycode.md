---
uid: Microsoft.Quantum.Canon.GrayCode
title: Função GrayCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840503"
---
# <a name="graycode-function"></a><span data-ttu-id="e7e55-102">Função GrayCode</span><span class="sxs-lookup"><span data-stu-id="e7e55-102">GrayCode function</span></span>

<span data-ttu-id="e7e55-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e7e55-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e7e55-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7e55-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7e55-105">Cria sequências de código cinza</span><span class="sxs-lookup"><span data-stu-id="e7e55-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="e7e55-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e7e55-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="e7e55-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e7e55-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e7e55-108">Número de bits</span><span class="sxs-lookup"><span data-stu-id="e7e55-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="e7e55-109">Saída :[(Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span><span class="sxs-lookup"><span data-stu-id="e7e55-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="e7e55-110">Conjunto de tuples.</span><span class="sxs-lookup"><span data-stu-id="e7e55-110">Array of tuples.</span></span> <span data-ttu-id="e7e55-111">Primeiro valor em tuple é valor na sequência GrayCode Segundo valor em tuple é posição para alterar o valor atual para obter o próximo.</span><span class="sxs-lookup"><span data-stu-id="e7e55-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>

## <a name="example"></a><span data-ttu-id="e7e55-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e7e55-112">Example</span></span>

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```