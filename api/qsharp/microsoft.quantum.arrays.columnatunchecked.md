---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: Função ColumnAtUnchecked
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 06fce23bbf7142ee0e0b0ed3f2c0578676f2097b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221594"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="f48bf-102">Função ColumnAtUnchecked</span><span class="sxs-lookup"><span data-stu-id="f48bf-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="f48bf-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f48bf-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f48bf-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f48bf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f48bf-105">Esta função não verifica a forma da matriz</span><span class="sxs-lookup"><span data-stu-id="f48bf-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="f48bf-106">Description</span><span class="sxs-lookup"><span data-stu-id="f48bf-106">Description</span></span>

<span data-ttu-id="f48bf-107">Esta função pode ser utilizada noutras funções multidimensionais, que já verificam a matriz de entrada para uma forma retangular válida.</span><span class="sxs-lookup"><span data-stu-id="f48bf-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="f48bf-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="f48bf-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="f48bf-109">coluna : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f48bf-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="f48bf-110">matriz : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="f48bf-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="f48bf-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="f48bf-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f48bf-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="f48bf-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f48bf-113">'T</span><span class="sxs-lookup"><span data-stu-id="f48bf-113">'T</span></span>

