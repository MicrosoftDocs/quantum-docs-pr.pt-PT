---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: Função ColumnAtUnchecked
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 4f4631bb49f769816a3df772f7b2f346c8ccfc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842865"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="c5fad-102">Função ColumnAtUnchecked</span><span class="sxs-lookup"><span data-stu-id="c5fad-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="c5fad-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c5fad-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c5fad-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5fad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5fad-105">Esta função não verifica a forma da matriz</span><span class="sxs-lookup"><span data-stu-id="c5fad-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="c5fad-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="c5fad-106">Description</span></span>

<span data-ttu-id="c5fad-107">Esta função pode ser utilizada noutras funções multidimensionais, que já verificam a matriz de entrada para uma forma retangular válida.</span><span class="sxs-lookup"><span data-stu-id="c5fad-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="c5fad-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="c5fad-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="c5fad-109">coluna : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5fad-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="c5fad-110">matriz : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="c5fad-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="c5fad-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="c5fad-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c5fad-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="c5fad-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c5fad-113">'T</span><span class="sxs-lookup"><span data-stu-id="c5fad-113">'T</span></span>

