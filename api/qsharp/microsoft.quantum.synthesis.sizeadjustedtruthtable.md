---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: Função TamanhosajustedTruthTable
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 8d69aa119c25a0f64743fec36c00ecdef2450c44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855326"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="2e71f-102">Função TamanhosajustedTruthTable</span><span class="sxs-lookup"><span data-stu-id="2e71f-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="2e71f-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="2e71f-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="2e71f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2e71f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2e71f-105">Ajusta a tabela da verdade a partir de matriz de Booleans de acordo com o número de variáveis</span><span class="sxs-lookup"><span data-stu-id="2e71f-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="2e71f-106">Uma nova matriz é devolvida de `2^numVars` comprimento, possivelmente exigindo estender `table` o tamanho com entradas ou `false` truncar-lo a `2^numVars` elementos.</span><span class="sxs-lookup"><span data-stu-id="2e71f-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="2e71f-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="2e71f-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="2e71f-108">tabela : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="2e71f-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="2e71f-109">Tabela da verdade como conjunto de valores da verdade</span><span class="sxs-lookup"><span data-stu-id="2e71f-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="2e71f-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2e71f-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2e71f-111">Número de variáveis</span><span class="sxs-lookup"><span data-stu-id="2e71f-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="2e71f-112">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="2e71f-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="2e71f-113">Tabela de verdade ajustada de tamanho</span><span class="sxs-lookup"><span data-stu-id="2e71f-113">Size adjusted truth table</span></span>